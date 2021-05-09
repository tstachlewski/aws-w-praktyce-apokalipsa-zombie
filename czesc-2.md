
Przykładowy skrypt "User Data" (dla "Amazon Linux 2"):

```
#!/bin/bash
sudo yum update -y
sudo yum install php httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
sudo su

cat <<EOF> /var/www/html/index.html
<html>
	<body>
    <br/><br/><br/>
    <div style="text-align:center;">
      <img src="https://awspoland.s3-eu-west-1.amazonaws.com/cloud.png" align="middle">
      <h1> Cloudy page!!!</h1>
    </div>
	</body>
</html>
EOF
```


Pierwsze kroki z AWS CLI:

```
aws ec2 describe-instances

aws ec2 describe-instances --query "Reservations[*].Instances[*].InstanceId"

aws ec2 describe-instances --query "Reservations[*].Instances[*].InstanceId" --output table
```
Dokumentacja: https://docs.aws.amazon.com/cli/latest/reference/index.html#cli-aws


Weryfikacja "kim" jestesmy
```
aws sts get-caller-identity --query Arn
```
