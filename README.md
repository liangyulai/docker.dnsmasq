Docker 下搭建 DNS 服务器 dnsmasq

# 选择 andyshinn/dnsmasq 的 docker 镜像

## docker pull andyshinn/dnsmasq:2.76

# DNS 服务默认是用的53端口

## netstat -lnp|grep 53

# Clone : https://github.com/liangyulai/docker.dnsmasq.git
```

└─[$] <git:(master)> tree
.
├── etc
│   ├── dnsmasq.conf
│   ├── hosts
│   │   ├── dnsmasqhosts
│   │   └── hosts
│   └── resolv.dnsmasq
└── README.md
```

2 directories, 5 files

## docker run -d -p 53:53/tcp -p 53:53/udp --cap-add=NET_ADMIN --name dns-server -v $pwd/etc/dnsmasq.conf:/etc/dnsmasq.conf -v $pwd/etc/resolv.dnsmasq:/etc/resolv.dnsmasq -v $pwd/etc/hosts:/etc/hosts andyshinn/dnsmasq:2.76
## docker run -d -p 53:53/tcp -p 53:53/udp --cap-add=NET_ADMIN --name dns-server -v ~/workspace/github/docker.dnsmasq/etc/dnsmasq.conf:/etc/dnsmasq.conf -v ~/workspace/github/docker.dnsmasq/etc/resolv.dnsmasq:/etc/resolv.dnsmasq -v ~/workspace/github/docker.dnsmasq/etc/local-hosts:/etc/local-hosts andyshinn/dnsmasq:2.76


# 修改本机 DNS 服务器地址


# 通过dig命令查看 dig www.google.com
