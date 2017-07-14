# 将本地代码发布到远程服务器

免密登陆

权限的修改

![](/assets/SSH.png)root默认是不可以不输入密码的。

```
chmod 700 id.rsa
#安装ssh-copy-id
ssh-copyid -i id.rs root@ip  -f

```

1.能过rsync命令

```bash
#!/usr/bin/env bash
rsync -vzcrSLhp --exclude="deploy.sh" ./ code-run.com:/var/www/site
```

2.通过scp命令

```
scp -rp docs/* code-run.com:tmp
```

3.通过git的方式

[https://serversforhackers.com/c/automating-deployment-from-github](https://serversforhackers.com/c/automating-deployment-from-github)

[https://www.digitalocean.com/community/tutorials/building-for-production-web-applications-deploying](https://www.digitalocean.com/community/tutorials/building-for-production-web-applications-deploying)

[https://css-tricks.com/deployment/](https://css-tricks.com/deployment/)

[https://wikitech.wikimedia.org/wiki/How\_to\_deploy\_code](https://wikitech.wikimedia.org/wiki/How_to_deploy_code)

[https://www.zhihu.com/question/33312099](https://www.zhihu.com/question/33312099)

[https://documentation.codeship.com/basic/continuous-deployment/deployment-with-ftp-sftp-scp/](https://documentation.codeship.com/basic/continuous-deployment/deployment-with-ftp-sftp-scp/)

[https://wohugb.gitbooks.io/pm2/content/deployment/getting\_started\_with\_deployment.html](https://wohugb.gitbooks.io/pm2/content/deployment/getting_started_with_deployment.html)

[http://blog.chinaunix.net/uid-26284395-id-2949145.html](http://blog.chinaunix.net/uid-26284395-id-2949145.html)

[https://github.com/beautifulcode/ssh-copy-id-for-OSX](https://github.com/beautifulcode/ssh-copy-id-for-OSX)

pm2 deploy setting.config production —force 会执行post-deploy

pm2 deploy setting.config production setup 则不会执行post-deploy 但会执行 post-setup

deploy --config deploy.conf production

deploy stagn setup 初始化

deploy stagin 部署到服务器执行shell脚本做一些构建的功能

node 7 以上unbutun 缺少一些动态库

[https://my.oschina.net/u/1540325/blog/639884](https://my.oschina.net/u/1540325/blog/639884)

