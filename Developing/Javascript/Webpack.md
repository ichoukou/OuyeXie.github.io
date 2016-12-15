 - [Beginner’s guide to Webpack](https://medium.com/@dabit3/beginner-s-guide-to-webpack-b1f1a3638460#.kjds8nbl2)

 - [Webpack 入门指迷](http://segmentfault.com/a/1190000002551952)
 - [CONFIGURATION](http://webpack.github.io/docs/configuration.html)
 - [code spliting](http://www.tuicool.com/articles/j6RjyqM)
    - [Support async React Router components #12](https://github.com/relay-tools/react-router-relay/issues/12)
    - [require-ensure-shim](https://github.com/hpherzog/require-ensure-shim)
 - [借助Code Splitting 提升单页面应用性能](http://www.tuicool.com/articles/3EbmAb)
 
 - [Compile an npm module into a single file, without dependencies](http://stackoverflow.com/questions/22710887/compile-an-npm-module-into-a-single-file-without-dependencies)
 
 - [How to prevent moment.js from loading locales with webpack?](http://stackoverflow.com/questions/25384360/how-to-prevent-moment-js-from-loading-locales-with-webpack)
    - http://webpack.github.io/docs/context.html
<pre>
plugins: [
    new webpack.ContextReplacementPlugin(/moment[\/\\]locale$/, /^\.\/zh-cn$/)
  ]
<pre>