# Nginx配置优化

> 服务器对前端的性能也会起到一些至关重要的作用，比如开启gzip压缩，开启静态资源缓存等。  
> 开启 gzip 和缓存能大大减少带宽的消耗

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

