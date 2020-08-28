---
title: MobaXterm 远程连接虚拟机很慢
date: 2019-09-03 15:43:21
tags:
---

原因： **<font color="red">ssh的服务端在连接时会自动检测dns环境是否一致导致的。</font>**

解决方法：

修改ssh服务配置文件

```
vi /etc/ssh/sshd_config
```

查找UseDNS关键字

```
/UseDNS
```

将 UseDNS yes 改成 UseDNS no（注意要将UseDNS前面的#号去掉，不然没用）

保存退出后重启 ssh 服务

```
systemctl restart sshd
```
