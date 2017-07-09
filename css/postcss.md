# POSTCSS总结

```
webpack install postcss

```

POST包括语法和插件

* [http://browserl.ist/](http://browserl.ist/)
* [https://autoprefixer.github.io/](https://autoprefixer.github.io/)

我们可以通过上面的浏览器输入对应的规则来看postcss编译过后的样式是否支持某些浏览器

同时[https://github.com/babel/babel-preset-env](https://github.com/babel/babel-preset-env) 也是使用此插件来兼浏览器

新建一个browser.rc如果你安装了该插件将自动按照你所你的配置查找该配置

# webpack配置postcss

```
npm install postcss-sass --save-dev
npm install postcss-loader --save-dev
npm install precss --save-dev
```



前处理器和后代处理器的区别

指定支持的浏览器版本

Autoprefixer使用Browserlist来确定哪些浏览器版本将得到支持。默认情况下根据需要提供前缀的支持：

\*\*&gt; 1%\*\*: 全球有超过1%的人使用的浏览器

last 2 versions: 根据CanIUse.com追踪的最后两个版本的所有浏览器

Firefox ESR: 最新的Firefox版本

Opera 12.1: Opera 12.1版本

著作权归作者所有。

商业转载请联系作者获得授权,非商业转载请注明出处。

原文: [http://www.w3cplus.com/PostCSS/using-postcss-for-cross-browser-compatibility.html](http://www.w3cplus.com/PostCSS/using-postcss-for-cross-browser-compatibility.html) © w3cplus.com



720yun h5doo

