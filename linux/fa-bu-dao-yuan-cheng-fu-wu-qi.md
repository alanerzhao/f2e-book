# 将本地代码发布到远程服务器

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

https://serversforhackers.com/c/automating-deployment-from-github

