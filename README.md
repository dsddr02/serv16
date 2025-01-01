
```
curl -s https://raw.githubusercontent.com/dsddr02/serv/refs/heads/main/sb_serv00_socks.sh -o sb00.sh && bash sb00.sh  
```
![主菜单截图](https://pan.811520.xyz/2024-10/1729677354-image.webp)

- 也可以支持老王的无交互安装
例如（注意大小写）：  
`VMESS_PORT=tcp端口 HY2_PORT=udp端口 SOCKS_PORT=udp端口 SOCKS_USER=abc123 SOCKS_PASS=abc456 bash <(curl -Ls https://raw.githubusercontent.com/yutian81/serv00-ct8-ssh/main/vps_sb00_alive/sb00-sk5.sh)`

- 其他变量也可一并写入，例如（注意大小写）：  
`UUID=123456 NEZHA_SERVER=nz.abcd.com NEZHA_PORT=5555 NEZHA_KEY=123ABC ARGO_DOMAIN=2go.admin.com ARGO_AUTH=abc123`（如果是json格式的密钥，需要用英文 `'abcabc'` 单引号包裹）

- sev00四合一无交互全变量一键脚本示例：
```bash
VMESS_PORT=tcp端口 HY2_PORT=udp端口 SOCKS_PORT=udp端口 SOCKS_USER=abc123 SOCKS_PASS=abc456 UUID=123456 NEZHA_SERVER=nz.abcd.com NEZHA_PORT=5555 NEZHA_KEY=123ABC ARGO_DOMAIN=2go.admin.com ARGO_AUTH=abc123 bash <(curl -Ls https://raw.githubusercontent.com/yutian81/serv00-ct8-ssh/main/vps_sb00_alive/sb00-sk5.sh)
```

***已修复 argo 密钥为 token 格式时无法重启的问题，现在 json 和 token 都可以重启***

可以通过F大的API获取json：https://fscarmen.cloudflare.now.cc, 获取方式请看F大的教程：

[获取json教程](https://github.com/fscarmen/ArgoX?tab=readme-ov-file#argo-json-%E7%9A%84%E8%8E%B7%E5%8F%96); [获取token教程](https://github.com/fscarmen/ArgoX?tab=readme-ov-file#argo-token-%E7%9A%84%E8%8E%B7%E5%8F%96)

----

## VPS版一键无交互脚本 5in1：vless+reality|vmess+argo|hy2|tuic|socks5
```
vless_port=34766 bash <(curl -Ls https://raw.githubusercontent.com/yutian81/serv00-ct8-ssh/main/vps_sb5in1.sh)
```

### 测试socks5是否通畅：运行以下命令，若正确返回服务器ip则节点通畅
```
curl ip.sb --socks5 用户名:密码@localhost:端口
```
----


```json
[
  {"username": "cmliusss", "password": "7HEt(xeRxttdvgB^nCU6", "panel": "panel4.serv00.com", "ssh": "s4.serv00.com"},
  {"username": "cmliussss2018", "password": "4))@cRP%HtN8AryHlh^#", "panel": "panel7.serv00.com", "ssh": "s7.serv00.com"},
  {"username": "4r885wvl", "password": "%Mg^dDMo6yIY$dZmxWNy", "panel": "panel.ct8.pl", "ssh": "s1.ct8.pl"}
]
```

#### CF worker 方式保活
- [天诚博文教程](https://linux.do/t/topic/181957)
- [天诚相关代码](https://github.com/yutian81/serv00-ct8-ssh/tree/main/cf-sb00-alive)

#### vps远程登录ssh方式保活
- [老王相关代码及本人修改的多服务器批量保活代码](https://github.com/yutian81/serv00-ct8-ssh/tree/main/vps_sb00_alive)

----


## 手动重置服务器，逐行执行
```
pkill -kill -u $(whoami)
chmod -R 755 ~/*
chmod -R 755 ~/.*
rm -rf ~/.*
rm -rf ~/*
```
