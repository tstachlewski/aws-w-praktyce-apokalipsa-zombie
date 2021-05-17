Aktualizacja plików źródłowych
```
cd ~/environment/zombie-application
rm -r *
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-4/frontend.zip .
unzip frontend.zip 
rm -r frontend.zip
```

Dodanie zmian do repozytorium kodu
```
git add -A
git commit -m "new changes"
git push
```
