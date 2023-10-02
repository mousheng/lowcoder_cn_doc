# 如何访问宿主机 APIDB

---

* [https://majiang.co/docs/visit-host-api-or-db](https://majiang.co/docs/visit-host-api-or-db)
* 使用 Docker 镜像在本地服务器部署码匠后，您可能需要码匠访问部署在同一台服务器（宿主机）的 API/DB 数据源。码匠镜像默认使用[桥接 (Bridge) 模式](https://docs.docker.com/network/bridge/)，因此无法通过 `127.0.0.1`​/`localhost`​ 访问宿主机相关服务（只能请求到镜像内部网络）。本文以 MySQL 为例，介绍在不同系统环境下如何访问宿主机上的 API/DB。
* 2023-10-02 18:12:38

---

如何访问宿主机 API/DB

使用 Docker 镜像在本地服务器部署码匠后，您可能需要码匠访问部署在同一台服务器（宿主机）的 API/DB 数据源。码匠镜像默认使用 [桥接 (Bridge) 模式](https://docs.docker.com/network/bridge/)，因此无法通过 `127.0.0.1`​/`localhost`​ 访问宿主机相关服务（只能请求到镜像内部网络）。本文以 MySQL 为例，介绍在不同系统环境下如何访问宿主机上的 API/DB。

## 准备

假设宿主机上已有 MySQL 服务，端口为 12345，确认本地访问 MySQL 服务无误：

**       **![localhost mysql](assets/localhost-mysql-20231002181238-cw1zx3c.jpg "localhost mysql")[           ](https://majiang.co/static/f52a57aff082da63e4d4cb87b4784042/fcff9/localhost-mysql.jpg)

## Linux

1. 在宿主机终端中输入 `ifconfig docker0`​，确认 Docker 虚拟网桥 IP 配置：

**       **![linux ifconfig docker0](assets/linux-ifconfig-docker0-20231002181238-9gzvcoe.jpg "linux ifconfig docker0")[           ](https://majiang.co/static/98fcda0e5be6a1953faaf58b50f11e15/8faea/linux-ifconfig-docker0.jpg)

Docker 服务启动时，系统会自动创建一个 docker0 的设备（默认 IP 地址为 `172.17.0.1`​），docker 服务可以通过该 IP 与宿主机进行通信。

2. 使用上图红框中的 IP 地址（当前例子为 `172.17.0.1`​，具体根据您终端显示值而定），在码匠中配置 MySQL 数据源，如下所示：

**       **![linux host setting](assets/linux-host-setting-20231002181238-sj9uixb.jpg "linux host setting")[           ](https://majiang.co/static/f780f9b522481eac721f69cae2e0ecd2/5c1ad/linux-host-setting.jpg)

> #### ⚠️ 注意
>
> 部分系统（如 Ubuntu）可能因为防火墙原因访问失败，此时需要：
>
> 1. 配置防火墙允许 docker0 访问，终端中输入：
>
> ```bash
> iptables -A INPUT -p tcp -i docker0 --dport 3306 -j ACCEPT
> ```
>
> 2. 保存防火墙配置，终端中输入：
>
> ```bash
> iptables-save > /etc/iptables.up.rules
> ```

## Windows/Mac

Docker 在 Windows 和 macOS 平台下并没有 docker0 虚拟网桥，此时可以使用这个特殊的 DNS 名称来解析宿主机 IP：

```text
host.docker.internal
```

码匠中配置 MySQL 数据源如下所示：

**       **![windows mac host setting](assets/windows-mac-host-setting-20231002181238-xv16c2z.jpg "windows mac host setting")[           ](https://majiang.co/static/747d1fbacfaadf2324503a832fbdb506/9e23d/windows-mac-host-setting.jpg)
