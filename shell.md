# shell工具提高开发效率

资源

* [https://github.com/alebcay/awesome-shell](https://github.com/alebcay/awesome-shell)
* [http://www.cnblogs.com/kaituorensheng/p/3980334.html](http://www.cnblogs.com/kaituorensheng/p/3980334.html)
* [https://github.com/alebcay/awesome-shell](https://github.com/alebcay/awesome-shell)
* [https://github.com/robbyrussell/oh-my-zsh/wiki](https://github.com/robbyrussell/oh-my-zsh/wiki)

监控命令执行，reload shell

```
npm install -g watch
watch command 
example 
watch ./deploy.sh
change ./deploy.sh update /deploy.sh

监控其他文件变化
nodemon --exec 'sh' deploy.sh
nodemon --watch --exec 'sh' deploy.sh


nodemon 也可监控node脚本的变化
nodemon lib/cli.js
```

https://github.com/mattallty/Caporal.js

https://github.com/visionmedia/debug

https://github.com/FormidableLabs/nodejs-dashboard

https://github.com/donnemartin/dev-setup

