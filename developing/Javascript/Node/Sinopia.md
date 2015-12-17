# Command

```
sudo npm install -g react-native-cli
```

```
sinopia
```

```
npm set registry http://localhost:4873/
```

rollback(npm config set registry "http://registry.npmjs.org")

```
npm set ca null
```

```
npm adduser --registry http://127.0.0.1:4873
```
ouyexie 6521Wxxxi ouyexie@gmail.com

cd into dir which has a package.json

```
npm install / npm install --production (optional)
```

```
npm publish --registry=http://127.0.0.1:4873/
```

# Fqa

 - npm ERR! publish fail Cannot publish over existing version.
     - npm unpublish --force --registry=http://127.0.0.1:4873/

# Reference

 - https://github.com/rlidwka/sinopia
 - http://stackoverflow.com/questions/22636885/howto-publish-private-projects-to-sinopia-npm-adduser-for-private-registry-fail