Nazwy funkcji lambda:
```
getActiveUsers
activeUserPing
```

Aktualizacja kodu źródłowego funkcji lambd
```
cd ~/environment/zombie-application

aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-6/backend/getActiveUsers-function/index.js amplify/backend/function/getActiveUsers/src/index.js
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-6/backend/activeUserPing-function/index.js amplify/backend/function/activeUserPing/src/index.js
```

Instalacja AWS SDK
```
npm install aws-sdk
```

Aktualizacja plików strony
```
cd ~/environment/zombie-application

aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-6/frontend/manifest.json public/manifest.json
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-6/frontend/Home.js src/Home.js
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-6/frontend/App.js src/App.js
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-6/frontend/App.css src/App.css
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-6/frontend/index.js src/index.js
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-6/frontend/index.css src/index.css
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-6/frontend/Messages.js src/Messages.js
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-6/frontend/Messages.css src/Messages.css
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-6/frontend/Users.js src/Users.js
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-6/frontend/Users.css src/Users.css

```

Commit od repozytorium
```
git add -A
git commit -m "new changes"
git push
```
