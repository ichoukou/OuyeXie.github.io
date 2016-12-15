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

```
npm set registry http://123.56.89.3:4873/
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
 - run as service
    - https://github.com/rlidwka/sinopia/blob/master/SERVER.md

# Reference

 - https://github.com/rlidwka/sinopia
 - http://stackoverflow.com/questions/22636885/howto-publish-private-projects-to-sinopia-npm-adduser-for-private-registry-fail
 - [Sinopia | 从零开始搭建npm仓库](http://www.wtoutiao.com/p/1f0pl01.html)