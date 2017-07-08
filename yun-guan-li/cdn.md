CDN \( Content Delivery Network，内容分发网络 \) 服务是遍布全球的内容分发网络。内容分发网络是一种通过部署在互联网上的高度分布式的加速平台，代替了传统以

`Web Server`

为中心的数据传输模式，可直接响应最终用户（ 也即客户端 ）的 Web 内容请求。通过内容分发网络，可将网站的静态资源，如图片、JavaScript 、CSS、网页等内容发布到最接近最终用户（ 客户端 ）的网络边缘 ，配合精准智能调度和边缘缓存，使得最终用户都能够快速安全可靠的访问到网站资源，以确保最终用户得到最快的页面加载时间和最佳的性能。与此同时，可大幅降低源站压力。

![](/assets/cdn.png)

![](/assets/cnd3.png)

**客户端**

客户端通过 DNS 解析可以快速接入到又拍云 CDN 网络，CDN 智能调度系统可以响应一个离用户最近的 CDN 边缘节点 IP 给客户端，客户端可以达到就近访问的目的。

**CDN 网络**

又拍云 CDN 网络由边缘节点集群、中心节点集群、智能调度系统等模块和基础设施组成。节点集群除了具备高性能的缓存设备，还具备四层和七层的负载均衡功能。

**企业源站**

企业源站可以是企业自建的源站或者托管在第三方存储的静态资源，CDN 网络作为反向代理会根据客户端的请求回源站请求资源文件并将数据资源进行缓存。

**管理控制台**

用户可通过又拍云管理控制台、API 的方式，管理托管在又拍云 CDN 网络上的资源及服务，通过更多的统计数据展示，使得 CDN 服务更加方便、快捷。
