# vps-vpn

## 安装并配置 v2ray

1. cn2 VPS 一台；
2. 安装并配置 v2ray， 目前使用 vmess 类型连接；

## 开启服务器 BBR

1. `$sudo vim /etc/sysctl.conf`;
2. `net.core.default_qdisc=fq
net.ipv4.tcp_congestion_control=bbr`;

- 注：内核大于4.9.
