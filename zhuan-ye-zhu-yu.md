### 什么是 Source Maps？ {#source_maps}

源映射是一种基于 JSON 的映射格式，可以在缩小的文件与其源之间建立关系。如果您为生产而构建，缩小和合并 JavaScript 文件时，还会生成包含原始文件相关信息的源映射。

## 什么是预处理器？ {#_1}

预处理器可以获取任意的源文件，并将其转换成浏览器可以识别的内容。

输出为 CSS 时，可以使用预处理器添加以下功能（如果不使用预处理器，则不会存在这些功能）：CSS 变量、嵌套，等等。这个类别中显著的例子是[Sass](http://sass-lang.com/)、[Less](http://lesscss.org/)和[Stylus](https://learnboost.github.io/stylus/)。

输出为 JavaScript 时，它们可以从完全不同的语言转换（编译），或者将超集或新语言标准转换（转译）为当前的标准。这个类别中显著的例子是[CoffeeScript](http://coffeescript.org/)和 ES6（通过[Babel](https://babeljs.io/)）。

## 什么是构建流程？ {#_1}

构建流程是一组针对项目文件运行的任务，主要是在开发期间编译和测试代码，以及用于创建网站开发版本。构建流程不应是一组在开发工作流结束时运行的任务。

实现构建流程最热门的工具是[Gulp](http://gulpjs.com/)和[Grunt](http://gruntjs.com/)，二者都是命令行工具。

如果您对这两款工具都没有使用经验，请使用 Gulp，我们在[Web Starter Kit](https://developers.google.com/web/tools/starter-kit/)中就是使用它，因此建议您也使用它。

很多工具都具有 GUI，而且可能更容易掌握，但不是很灵活。

