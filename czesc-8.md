Kod funkcji Lambda
```
import json
import os
import boto3
import urllib.request
import uuid
from datetime import datetime

rekognition = boto3.client('rekognition')
s3 = boto3.client('s3')
ddb = boto3.resource('dynamodb', region_name='eu-west-1')

def lambda_handler(event, context):

    records = event["Records"]

    for record in records:

        if (record["eventName"] == "INSERT"):
            message = record["dynamodb"]["NewImage"]["message"]["S"];

            if message.startswith("DETECT"):
                link = message[7:]
                name = link[link.rfind("/")+1:]
                urllib.request.urlretrieve(link, '/tmp/' + name)
                s3.upload_file('/tmp/' + name, os.environ["BUCKET"], name)


                rekognition_response = rekognition.detect_faces(Image={'S3Object': {'Bucket': os.environ["BUCKET"], 'Name': name}}, Attributes=['ALL'])
                faces = rekognition_response["FaceDetails"];

                angryConfidence = 0;

                for face in faces:
                    emotions = face["Emotions"]
                    for emotion in emotions:
                        if emotion["Type"] == "ANGRY":
                            confidence = emotion["Confidence"]
                            if ( confidence > angryConfidence):
                                angryConfidence = confidence;

                if (angryConfidence > 50):
                    message = "ZOMBIE DETECTED!!! ( " + name + " )"
                else:
                    message = "No Zombie! ( " + name + " )"

                ts = (int)(datetime.now().timestamp())

                table = ddb.Table('messages')
                table.put_item(
                    Item={
                        'timestamp': (str)(ts),
                        'date' : datetime.utcfromtimestamp(ts).strftime('%Y-%m-%d %H:%M:%S'),
                        'message': message,
                        'user':"SYSTEM"
                    });

    return {
        'statusCode': 200,
        'body': "OK"
    }

```
