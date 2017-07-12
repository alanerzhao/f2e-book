---
styles:
  website: styles/website.css
  ebook: styles/ebook.css
  pdf: styles/pdf.css
  mobi: styles/mobi.css
  epub: styles/epub.css
---

# Nginx配置优化

> 服务器对前端的性能也会起到一些至关重要的作用，比如开启gzip压缩，开启静态资源缓存等。  
> 开启 gzip 和缓存能大大减少带宽的消耗
>
> Gzip 压缩通常可以减少 70% 的响应大小，对某些文件更可能高达 90%，比 Deflate 更高效。主流 Web 服务器都有相应模块，而且绝大多数浏览器支持 gzip 解码。所以，应该对 HTML、CSS、JS、XML、JSON 等文本类型的内容启用压缩

### 配置示例：

```bash
    #Compression Settings
    gzip             on;
    #gzip 压缩级别，1-10，数字越大压缩的越好，也越占用CPU时间，后面会有详细说明
    #gzip_comp_level  2;
    # 启用gzip压缩的最小文件，小于设置值的文件将不会压缩
    #gzip_min_length  1000;
    #gzip_proxied     expired no-cache no-store private auth;
    #进行压缩的文件类型。javascript有多种形式。其中的值可以在 mime.types 文件中找到
    gzip_types       text/plain application/javascript text/xml text/css application/xml;
    # 是否在http header中添加Vary: Accept-Encoding，建议开启
    gzip_vary on;
    #end gzip
```

对于同一个web app项目开启前的请求资源对比![](/assets/import.png)Gzip后![](/assets/import2.png)

# 缓存服务器

![](/assets/cache.png)

就像cdn一样，第一次请求源服务器，后面则请求了缓存服务器，CDN原理估然如此，就近原则返回给用户数据

* [https://www.mnot.net/cache\_docs/\#BROWSER](https://www.mnot.net/cache_docs/#BROWSER)
* [http://www.jianshu.com/p/625c2b15dad5](http://www.jianshu.com/p/625c2b15dad5)
* [https://segmentfault.com/a/1190000006689795](https://segmentfault.com/a/1190000006689795)

```
# Note that these are defined outside of the server block,
# altho they don't necessarily need to be
proxy_cache_path /tmp/nginx levels=1:2 keys_zone=my_zone:10m inactive=60m;
proxy_cache_key "$scheme$request_method$host$request_uri";

server {
    # Note that it's listening on port 80
    listen 80 default_server;

    index index.html index.htm;
    root /Users/baozi/learn/doc/slate/build;
    #root /Users/baozi/learn/yueqi/dist;

    server_name localhost;

    charset utf-8;

    location / {
        proxy_cache my_zone;
        add_header X-Proxy-Cache $upstream_cache_status; //值为HIT，MISS 或 BYPASS 状态码

        # include proxy_params;
        proxy_pass http://127.0.0.1:9000; //源服务器
    }
}
```

我们利用http命令行工具进行测试

![](/assets/http-test-cache.png)

查看http cache的文件

[chrome://cache/](chrome://cache/)

