brew install watchman
brew install flow
sudo npm install -g react-native-cli
sudo npm install -g gulp

setup sinopia
publish three projects:
1. clone https://github.com/facebook/relay/issues/26#issuecomment-164826631 里提到的 repo
2. setup 好本地 sinopia, 然后就三个包 publish 到 sinopia （注意需要修改 react-native/package.json 里的 version 为 0.17.10）
3. 修改 src/native/node_modules/react-native/packager/transformer.js 里的 
  `const extraPlugins = ['external-helpers-2'];`
  为 `const extraPlugins = ['external-helpers-2', require('../../../../../build/babelRelayPlugin')];`
  
```
$ npm install -g react-native-cli
$ cd ./src/native & npm i 
$ react-native start # ios
$ react-native run-android
```

# FAQ

 - How to deal with "gulp native" problem during publish relay?
    - checkout to master and "npm install", then checkout back, will be fine.