Babel使用非常小的助手来执行常见的功能`_extend`。默认情况下，这将被添加到需要它的每个文件。这种复制有时是不必要的，特别是当您的应用程序分布在多个文件上时。

这是`transform-runtime`插件的地方：所有的帮助者都将引用模块，`babel-runtime`以避免在编译的输出中重复。运行时将被编译到你的构建中。

  
多个模块中会存在多个babel打包好的模块，所以用了babel-runtime相当于抽离了共用组件，在代码执行前一下引入即可

webpack是做模块化的。而babel是做语法层面和兼容层面的东西



Babel其实是一个Js代码编译工具，用来将es6的语法编译成浏览器可执行的es5代码。通过插件的方式支持最新的语法。简单的理解就是babel封装了新的es6语法糖

  


通过使用

babel-preset-env 自动编译当前项目中的语法或者自定义

[https://github.com/babel/babel-preset-env/blob/master/data/plugins.json](https://github.com/babel/babel-preset-env/blob/master/data/plugins.json)

它不会包括stage-x插件。env将支持我们认为最新版本的Javascript的所有插件（通过匹配我们所做的

[babel-preset-latest](http://babeljs.io/docs/plugins/preset-latest/)

）

  


由于Babel只能转换语法（如箭头函数），您可以使用babel-polyfill来支持新的全局变量，例如Promise或新的本机方法，如String.padStart（left-pad）。它使用核心js和再生器。查看我们的babel-polyfill文档了解更多信息



