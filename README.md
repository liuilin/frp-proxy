# frp 内网穿透
### 修改配置
修改 frpc.ini 配置文件
```text
[common]
server_addr = 110.42.134.191
server_port = 7000
authentication_method = token
authenticate_heartbeats = true
authenticate_new_work_conns = true
token = GDL1NGrpdykE6rGu

[web]
type = https
local_port = 8080
custom_domains = pay.rxjava.top

plugin = https2http
plugin_local_addr = 127.0.0.1:8083

# HTTPS 证书相关的配置
plugin_crt_path = ./server.crt
plugin_key_path = ./server.key
plugin_host_header_rewrite = 127.0.0.1
plugin_header_X-From-Where = frp
```
在 frp_0.37.1_windows_amd64 目录下通过 ./frpc -c ./frpc.ini 启动客户端，浏览器访问上面配置的域名 pay.rxjava.top，就会代理到本地 127.0.0.1:8083
> 可以自定义域名以及本地端口号