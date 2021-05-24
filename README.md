# Clash config for Clubhouse

Clubhouse 代理规则，适用于 Clash。两条规则需同时添加搭配使用

- `Clubhouse-PROXY.list` 解决软件无法使用问题

- `Clubhouse_DIRECT.list` 解决进入进入没有声音问题

# 使用

`Clubhouse-PROXY` 表示域名/IP 需要通过代理连接。对应 Clash 的配置文件 `yaml` 里需要定义一个类似于：

```
- name: "Clubhouse-PROXY"
 type : select
 proxies: 
  - "PROXY"
  - "shadowsocks"
  - "v2ray"
  - ...
```

的名为 `Clubhouse-PROXY` 的代理模式，然后 `Clubhouse-PROXY.list` 中 `# > Clubhouse-PROXY` 下定义的域名/IP 就会都走代理了。

类似的，Clash 的配置文件 `yaml` 里再定义一个类似于 `Clubhouse-DIRECT` 一个直连模式：

```
- name: "Clubhouse-DIRECT"
 type : select
 proxies: 
  - "DIRECT"
```

然后 `Clubhouse-DIRECT.list` 中 `# > Clubhouse-DIRECT` 下定义的域名/IP 就会都直连了。


两个配合起来，Clubhouse 应该就可以正常使用了。
