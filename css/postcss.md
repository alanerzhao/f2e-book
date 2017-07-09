# POSTCSS总结

* 它的名字。PostCSS 既能在预处理器将源代码编译成 CSS 之前也能在其之后对文件执行操作。
* PostCSS 能替代你的预处理器。现在有很多插件实现了一些设计，如变量、 嵌套、mixins 以及 extends

* pre-processor（预处理器）
* post-processor（后处理器）

# webpack配置postcss



```
webpack install postcss
```

POST包括语法和插件

* [http://browserl.ist/](http://browserl.ist/)
* [https://autoprefixer.github.io/](https://autoprefixer.github.io/)
* [http://cssnext.io/setup/](http://cssnext.io/setup/)

我们可以通过上面的浏览器输入对应的规则来看postcss编译过后的样式是否支持某些浏览器

同时[https://github.com/babel/babel-preset-env](https://github.com/babel/babel-preset-env) 也是使用此插件来兼浏览器

新建一个browser.rc如果你安装了该插件将自动按照你所你的配置查找该配置

```
npm install postcss-sass --save-dev
npm install postcss-loader --save-dev
npm install precss --save-dev
#为了先方便测试可以先安装下人cli来测试用
npm install -g postcss-cli
postcss src/*.scss
postcss -c postcss.config.js src/test.css -o compile.css
配置css-next http://cssnext.io/setup/
npm install postcss-cssnext

npm uninstall --save-dev postcss-cssnext 卸载开发依赖中的包
npm uninstall --save postcss-cssnext 卸载依赖中的包
cssnext包含了Autoprefixer插件
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

简单来说，预处理器（ pre-processor ）是你把一些长得很像 CSS 但不是 CSS 的东西丢给它，处理过后会给你编译过后的CSS，

而 CSS 再经过后处理器 （ post-processor ），透过一些规则帮它加上一些东西，最后产出完整的CSS文件！

