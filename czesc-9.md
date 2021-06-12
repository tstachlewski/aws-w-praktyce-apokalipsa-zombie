Zastąp wartość 'opacity' w pliku App.js
```
opacity: 0.9,
```



Aktualizacja plików strony
```
cd ~/environment/zombie-application

aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-9/frontend/Home.js src/Home.js
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-9/frontend/Home.css src/Home.css
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-9/frontend/index.html public/index.html
```

Commit od repozytorium
```
git add -A
git commit -m "new changes"
git push
```
