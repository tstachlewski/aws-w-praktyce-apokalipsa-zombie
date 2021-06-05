Pobranie zawartości nowej lambdy NewUser
```
cd ~/environment/

aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-7/backend/NewUser.py .
```

Zaktualizowanie pliku źródłowego kontenera dockerowego.
```
cd ~/environment/message-microservice

aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-7/backend/app.py .

```
