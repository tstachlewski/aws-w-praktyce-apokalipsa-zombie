Zaktualizowanie pliku źródłowego kontenera dockerowego.
```
cd ~/environment/message-microservice
rm README.md

aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-7/backend/app.py .

```

Pobranie zawartości nowej lambdy NewUser
```
cd ~/environment/

aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-7/backend/NewUser.py .
```
