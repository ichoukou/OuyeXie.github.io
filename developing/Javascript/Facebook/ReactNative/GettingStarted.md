 - [setup a project](http://vczero.github.io/react_native/第1篇hello%20react-native.html)
 - [setup environment](http://www.liaohuqiu.net/cn/posts/react-native-1/)
 - [release (not detailed)](http://jingyan.baidu.com/article/154b4631724ad328ca8f4109.html)
     - jsCodeLocation is in file AppDelegate.m
 - [react native 中文](http://reactnative.cn/docs/tutorial.html#content)
 - [深入浅出 React Native：使用 JavaScript 构建原生应用](http://www.cocoachina.com/ios/20150408/11513.html)
 
 - Device
     - [iOS 真机调试](http://my.oschina.net/imot/blog/512808)
     - [使用Xcode 7 beta免费真机调试iOS应用程序](http://ju.outofmemory.cn/entry/182050)
     - *[Xcode 真机调试教程](http://segmentfault.com/a/1190000000775168)
     
# FAQ

 - what is "react-native start"?
     - [React Native实战（一）：配置和起步](http://www.csdn.net/article/2015-09-24/2825787-react-native)
     - 不管是 iOS 还是 Android，在开发调试阶段，都需要在 Mac 上启动一个 HTTP 服务，称为“Debug Server”，默认运行在 8081 端口，APP 通 Debug Server 加载 js。
 - AppRegistry
     - 将这一行加在文件末尾, React.AppRegistry.registerComponent('PropertyFinderApp', function() { return PropertyFinderApp });
       AppRegistry 定义了App的入口，并提供了根组件。