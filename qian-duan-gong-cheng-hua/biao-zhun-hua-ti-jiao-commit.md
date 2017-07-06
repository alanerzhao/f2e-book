# Commitizen

* 标准化commit日志
* 标准化change-log日志
* PR之前执行验证

在我们开发写代码时，经常对commit关注不够密切，此时代来的影响就是时间一长，或者重要的fetcher没有打对应的tags或者commit，几天以后你就不知道自己写的是什么了，为了解决这一问题开源社区有一个工具供我们使用，大家现在用的vue的源码库也在使用此工具进行提交。

```
npm install -g commitizen 现在执行git cz触发钩子
```

![](/assets/git commit)

```
commitizen init cz-conventional-changelog --save-dev --save-exact --force
"scripts": {
    "commit": "git-cz"
  }
```

利用[**standard-versio**](https://github.com/conventional-changelog/standard-version)生在changelog替换原生的nodeversion

```
npm i --save-dev standard-version
{
  "scripts": {
    "release": "standard-version"
  }
}
Now you can use npm run release in place of npm version.
```

利用pre-commit提交之前执行一些钩子

但是还是不能保证在 Pull Request 之前解决所有的校验问题。

```
{
  "name": "437464d0899504fb6b7b",
  "version": "0.0.0",
  "description": "ERROR: No README.md file found!",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: I SHOULD FAIL LOLOLOLOLOL \" && exit 1",
    "foo": "echo \"fooo\" && exit 0",
    "bar": "echo \"bar\" && exit 0"
  },
  "pre-commit": [
    "foo",
    "bar",
    "test"
  ]
}
```



