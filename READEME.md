# frp ������͸
### �޸�����
�޸� frpc.ini �����ļ�
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

# HTTPS ֤����ص�����
plugin_crt_path = ./server.crt
plugin_key_path = ./server.key
plugin_host_header_rewrite = 127.0.0.1
plugin_header_X-From-Where = frp
```
�� frp_0.37.1_windows_amd64 Ŀ¼��ͨ�� ./frpc -c ./frpc.ini �����ͻ��ˣ�����������������õ����� pay.rxjava.top���ͻ�������� 127.0.0.1:8083
> �����Զ��������Լ����ض˿ں�