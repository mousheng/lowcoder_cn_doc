# 连接 Redis

---

* [https://majiang.co/docs/database/redis](https://majiang.co/docs/database/redis)
* 连接 Redis
* 2023-10-02 17:29:31

---

连接 Redis

## 准备

首先您要获取到 Redis 数据库的连接配置，然后参考[IP 白名单](https://majiang.co/docs/ip-allowlist)文档将码匠的 IP 地址添加到数据库网络的白名单中（按需配置）。

## 新建数据源

**新建数据源** -> ​**Redis**​，连接方式有两种：

* URI 连接

​![](assets/redis-1-20231002172931-y6lq0yn.png)​

* 常规连接

​![](assets/redis-2-20231002172931-j3r2v52.png)​

填写完成数据源配置信息​**-&gt;测试连接**​，连接成功后，选择​**保存**​，该 Redis 数据源即新建完成，并且保存到了您的数据源列表中。

## 创建查询

创建查询 `query1`​，选择您的 Redis 数据源，然后设置其方法、命令等，即可点击​**运行**​。

​![](assets/redis-3-20231002172931-hxdfzdp.png)​

* [准备](https://majiang.co/docs/database/redis#%E5%87%86%E5%A4%87)
* [新建数据源](https://majiang.co/docs/database/redis#%E6%96%B0%E5%BB%BA%E6%95%B0%E6%8D%AE%E6%BA%90)
* [创建查询](https://majiang.co/docs/database/redis#%E5%88%9B%E5%BB%BA%E6%9F%A5%E8%AF%A2)
