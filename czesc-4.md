Aktualizacja plików źródłowych
```
cd ~/environment/zombie-application

rm README.md
rm public/logo512.png
rm public/logo192.png
rm public/favicon.ico
rm public/index.html
rm src/App.css
rm src/App.js
rm src/App.test.js
rm src/index.css
rm src/index.js
rm src/logo.svg
rm src/reportWebVitals.js
rm src/setupTests.js

aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-4/frontend/src/App.css src/App.css
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-4/frontend/src/App.js src/App.js
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-4/frontend/src/Home.js src/Home.js
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-4/frontend/src/index.css src/index.css
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-4/frontend/src/index.js src/index.js
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-4/frontend/src/Messages.js src/Messages.js
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-4/frontend/src/Users.js src/Users.js
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-4/frontend/public/favicon.ico public/favicon.ico
aws s3 cp s3://masterclazz-zombie-apocalypse-content/czesc-4/frontend/public/index.html public/index.html

npm install --save react-router-dom
npm install @material-ui/core
npm install react-bootstrap bootstrap@4.6.0
```

Dodanie zmian do repozytorium kodu
```
git add -A
git commit -m "new changes"
git push
```

Instalacja i konfiguracja Amplify CLI
```
npm install -g @aws-amplify/cli
amplify configure

```

Utworzenie nowego projektu Amplify
```
amplify init
```

Dodanie zmian do repozytorium kodu
```
git add -A
git commit -m "new changes"
git push
```

Dodanie elementu Amplify Hosting
```
amplify add hosting
```

Instalacja bibliotek Amplify dla react-a
```
npm install aws-amplify @aws-amplify/ui-react
```

Utwórz plik src/index.js i dodaj następuję trzy linie poniżej ostatniego importowanego elementu
```
import Amplify from "aws-amplify";
import awsExports from "./aws-exports";
Amplify.configure(awsExports);
```

Zaimportuj elementy uwierzytelniający w pliku src/App.js
```
import { withAuthenticator } from '@aws-amplify/ui-react'
```

Wykorzystaj funkcjonalność 'wrappera' aby otoczyć główny element aplikacji (src/App.js) wraperem uwierzytelniającym.
```
export default withAuthenticator(withStyles(styles)(App))
```

Dodanie przycisku wylogowania
```
import { withAuthenticator, AmplifySignOut } from '@aws-amplify/ui-react'
...
<AmplifySignOut />
```

Zmodyfikuj plik App.css
```
#signoutbutton {
  --amplify-primary-color: #343a40;
  float: right;
  padding-top: 10px;
  padding-right: 10px;
}
```

Dodaj przycisk w pliku App.js
```
<div id="signoutbutton"><AmplifySignOut/></div>
```
