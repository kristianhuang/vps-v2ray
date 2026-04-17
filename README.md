# vps-vpn

## 安装并配置 v2ray

1. cn2 VPS 一台；
2. 安装并配置 v2ray， 目前使用 vmess 类型连接；

### vmess 服务端配置

`
// /usr/local/etc/v2ray/config.json
{
  "inbounds": [
    {
      "port": 11223, // 对外端口
      "protocol": "vmess",
      "settings": {
        "clients": [
          {
            "id": "81498305-0be0-4923-a270-df4e490a086b", // 自定义 id，客户端配置与此处一致
            "alterId": 64, // shadowrocket 连接此处填 0
          }
        ]
      }
    }
  ],
  "outbounds": [
    {
      "protocol": "freedom",
      "settings": {}
    }
  ]
}
`
## 开启服务器 BBR

1. `$sudo vim /etc/sysctl.conf`;
2. `net.core.default_qdisc=fq
net.ipv4.tcp_congestion_control=bbr`;

- 注：内核大于4.9.
