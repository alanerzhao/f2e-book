为什么要用图片作请求



数据收集脚本（ga.js）被请求后会被执行，这个脚本一般要做如下几件事：

（1）通过浏览器内置javascript对象收集信息，如页面title（通过document.title）、referrer（上一跳url，通过document.referrer）、用户显示器分辨率（通过windows.screen）、cookie信息（通过document.cookie）等等一些信息。

（2）解析\_gaq收集配置信息。这里面可能会包括用户自定义的事件跟踪、业务数据（如电子商务网站的商品编号等）等。

（3）将上面两步收集的数据按预定义格式解析并拼接。

（4）请求一个后端脚本，将信息放在http request参数中携带给后端脚本。

这里唯一的问题是步骤4，javascript请求后端脚本常用的方法是ajax，但是ajax是不能跨域请求的。这里ga.js在被统计网站的域内执行，而后端脚本在另外的域（GA的后端统计脚本是http://www.google-analytics.com/\_\_utm.gif），ajax行不通。一种通用的方法是js脚本创建一个Image对象，将Image对象的src属性指向后端脚本并携带参数，此时即实现了跨域请求后端。这也是后端脚本为什么通常伪装成gif文件的原因。通过http抓包可以看到ga.js对\_\_utm.gif的请求：

