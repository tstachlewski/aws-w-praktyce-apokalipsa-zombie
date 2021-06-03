Rozszerzenie wielkości przestrzeni dyskowej
```
lsblk
sudo growpart /dev/xvda 1
sudo xfs_growfs -d /
```

Pobranie pliku mikrousługi kontenerowej
```
cd ~/environment/
rm README.md

aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-5/backend/message-microservice.zip .

unzip message-microservice.zip
rm message-microservice.zip

```

Trust policy dla roli
```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Service": "tasks.apprunner.amazonaws.com"
      },
      "Action": "sts:AssumeRole"
    }
  ]
}
```

Aktualizacja plików storny
```
cd ~/environment/zombie-application

aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-4/frontend/src/Messages.js src/Messages.js
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-4/frontend/src/Messages.css src/Messages.css

git add -A
git commit -m "new changes"
git push
```
