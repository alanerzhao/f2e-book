# webpack

* 分析打包过程
* 分析类库与应用逻辑代码分离
* 打包类库，构建一个打包vue单组件的工具

[https://doc.webpack-china.org/guides/development-vagrant/](https://doc.webpack-china.org/guides/development-vagrant/)

[https://github.com/fouber/blog](https://github.com/fouber/blog)

[https://www.javascripting.com/search?q=css](https://www.javascripting.com/search?q=css)

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



