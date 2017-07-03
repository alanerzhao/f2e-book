# Nginx配置优化

服务器对前端的性能也会起到一些至关重要的作用，比如开启gzip压缩，开启静态资源缓存等。

资源：

```bash
    #Compression Settings
    gzip             on;
    #gzip_comp_level  2;
    #gzip_min_length  1000;
    #gzip_proxied     expired no-cache no-store private auth;
    gzip_types       text/plain application/javascript text/xml text/css application/xml;
    #end gzip
```

对于同一个web app项目开启前的请求资源对比![](/assets/import.png)Gzip后

![](/assets/import2.png)

