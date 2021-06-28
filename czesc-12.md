Import plików
```
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-12/data . --recursive
```

Eksport plików
```
aws s3 cp . s3://REPLACEME --recursive
```

Import/Eksport z/do S3
```
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-12/data s3://TWOJ_BUCKET --recursive
```
