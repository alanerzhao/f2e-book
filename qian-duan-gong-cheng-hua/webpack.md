# webpack

* 分析打包过程
* 分析类库与应用逻辑代码分离
* 打包类库，构建一个打包vue单组件的工具

[https://doc.webpack-china.org/guides/development-vagrant/](https://doc.webpack-china.org/guides/development-vagrant/)

[https://github.com/fouber/blog](https://github.com/fouber/blog)

[https://www.javascripting.com/search?q=css](https://www.javascripting.com/search?q=css)

## 打包 vs. 加载

注意_加载_和_打包_模块之间的一些关键区别很重要。可以在[JSPM](http://jspm.io/)引擎下找到像[SystemJS](https://github.com/systemjs/systemjs)的工具，用于在浏览器通过运行时\(runtime\)来加载和转译模块。这和 webpack 有着显著不同，在加载到浏览器之前，模块就已经被转译（通过 "loaders"）并打包在一起。

每种方法都有其利弊。运行时\(runtime\)加载和转译模块，为大型网站增加了大量开销，并且应用程序会由许多模块组成。因此，SystemJS 对于需要少量模块的小型项目更有意义。但是，随着[HTTP/2](https://http2.github.io/)改善文件从服务器到客户端的传输速度，这可能会发生一些变化。请注意，HTTP/2 不会修改_转译_模块的任何内容，在客户端下载完成后，还是需要很长时间去进行转译。

加入manifest

![](/assets/manifest.png)

```
 plugins: [
            new webpack.optimize.CommonsChunkPlugin({
                name: 'vendor',
                minChunks: function (module) {
                   // this assumes your vendor imports exist in the node_modules directory
                   return module.context && module.context.indexOf('node_modules') !== -1;
                }
            }),
            //CommonChunksPlugin will now extract all the common modules from vendor and main bundles
            new webpack.optimize.CommonsChunkPlugin({
                name: 'manifest' //But since there are no more common modules between them we end up with just the runtime code included in the manifest file
            })
        ]
    };
    脑子要活可以配置多个
```

优化打包libary代码

```
module.exports = {
    ...
    externals: {
        "lodash": {
            commonjs: "lodash",
            commonjs2: "lodash",
            amd: "lodash",
            root: "_"
        }
    }
    ...
};
```

![](/assets/vue.png)

但是在打包vue组件的时候将支出现大量的重复代码



