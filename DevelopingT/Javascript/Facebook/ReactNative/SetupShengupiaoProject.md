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

```
sudo gem install cocoapods 
cd ios
pod install
npm start
```
# FAQ

 - How to deal with "gulp native" problem during publish relay?
    - checkout to master and "npm install", then checkout back, will be fine.
 - file cannot found (RCTWechat.h)
    - 2. 链接库文件到你的项目中
      
      参考 https://facebook.github.io/react-native/docs/linking-libraries-ios.html#content
      
      a. 给RCTWeChat添加头文件搜索路径：$(SRCROOT)/../../react-native/React，并选择recursive。
      
      b. 因为需要在 AppDelegate.m 文件中导入 RCTWeChat.h，所以需要在你的项目中添加一个头文件搜索路径： $(SRCROOT)/.      ./node_modules/react-native-wechat-ios/RCTWeChat，并选择recursive。
 - need semicolon after class defination
    - downgrade react-native's babel-core dependencies from 6.4
          "babel-core": "6.3.21",
          "babylon": "6.3.25",
    - https://github.com/feross/standard/issues/372
 - Jan 19 11:45:26 Ouyes-MacBook-Pro 神股票-DEBUG[24304]: Argument 0 (NSNumber) of RCTUIManager.updateView must not be null
   Jan 19 11:45:26 Ouyes-MacBook-Pro 神股票-DEBUG[24304]: Argument 0 (<null>) of RCTUIManager.updateView could not be processed. Aborting method call.
    - did you forget modify file transformer.js? also restart the debug server!