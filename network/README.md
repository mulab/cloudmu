# 网络

不同容器间网络的通信是一个问题

这里的文章简单的介绍了现有的一些解决方案: http://dockone.io/article/372

另外在dockerone.com 微信群技术分享活动中, 来自芒果TV平台部的彭哲夫分享了芒果TV的网络方案 http://mp.weixin.qq.com/s?__biz=MzA5OTAyNzQ2OA==&mid=204588870&idx=1&sn=4197210e9ca01ab0ecd77ea135e7f1bf&scene=2&from=timeline&isappinstalled=0#rd

总体来说, 目前的网络方案有:

- weave: 一个老牌解决方案
- flannel: 来自coreos的解决方案
- pipework: 同样是一个老牌解决方案, 但是据说不好
- libnetwork: 目前还没有可用版本

目前对于我们的use case, 三台host over public network, 本来就要使用vpn来使三台机器组成一个内网, 因此我们可以通过vpn的push route来让为客户端添加路由.

具体可参见https://github.com/mulab/intro/wiki/VPN%E6%8C%87%E5%8D%97