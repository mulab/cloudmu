# cloudmu
A docker-based cloud platform plan.


## Steps

### Consul

创建consul, 可以使用 [mulab/consul](https://github.com/mulab/consul)的`docker-compose.yml`, 并且添加相应的ns record到域名中, 例如域名是lab.mu, 则需要添加 service.lab.mu, node.lab.mu的ns record到consul主机, 并且将consul容器的53/udp bind到host.

这样可能并不安全(暴露内部服务的ip和域名的关系), 但可以减少vpn客户端配置时的不方便.

相关wiki [mulab/intro/wiki/Consul-指南](https://github.com/mulab/intro/wiki/Consul-%E6%8C%87%E5%8D%97)