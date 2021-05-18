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

Instalacja i konfiguracja Amplify CLI
```
npm install -g @aws-amplify/cli
amplify configure

```

Utworzenie nowego projektu Amplify
```
amplify init
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
