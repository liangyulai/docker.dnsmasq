Docker 下搭建 DNS 服务器 dnsmasq

# 选择 andyshinn/dnsmasq 的 docker 镜像
## docker pull andyshinn/dnsmasq:2.76

# DNS 服务默认是用的53端口
## netstat -lnp|grep 53

# 
## 

# 
## docker run -d -p 53:53/tcp -p 53:53/udp --cap-add=NET_ADMIN --name dns-server andyshinn/dnsmasq:2.76



# 修改本机 DNS 服务器地址


# 通过dig命令查看 dig www.google.com
