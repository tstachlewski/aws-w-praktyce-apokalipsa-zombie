Nowy import:
```
import Firehose from 'aws-sdk/clients/firehose';
```



Nowy wycinek skryptu:
```
const firehose = new Firehose({
  credentials: Auth.essentialCredentials(credentials),
  region: "eu-west-1"
});

var statsParams = {
  DeliveryStreamName: 'zombie-stats',
  Record: {
    Data: "{\"user\": \"" + this.state.user + "\", \"time\":\"" + new Date() + "\", \"page\":\"" + "Home" + "\"}\\n"
  }
};

firehose.putRecord(statsParams, function(err, data) {
  if (err) console.log(err, err.stack);
  else     console.log(data);          
});
```

Commit od repozytorium
```
git add -A
git commit -m "new changes"
git push
```
