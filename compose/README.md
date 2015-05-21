# 服务编排

使用compose进行服务编排.

## hostname domain name

在compose中有`domainname`的选项,而docker run是没有这个参数的, 文档中关于该参数的行为描述并不清楚, 从源代码的注释中可以了解到行为如下:

1. 同时设置了hostname和domainname, 这时compose会将其分别传递给docker client的api
2. 只设置了hostname, 此时如果hostname里面有`.`则会讲其第一个`.`之前的部分作为hostname,之后作为domainname传给docker client的api
3. 没有设置hostname,设置了domainname, ** 不会有任何效果 **

因此, 如果我们想使容器的hostname是id,而添加一个domainname在其之后, 我们需要在compose的hostname设置中写上`.domain.name`,注意最开始的`.`

另外虽然docker client的api支持domainname, 但是 docker run并不支持, 直接在cli中设置domainname也要如上所述