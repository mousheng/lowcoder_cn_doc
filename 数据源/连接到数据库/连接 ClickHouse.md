# 连接 ClickHouse

---

* [https://majiang.co/docs/database/clickhouse](https://majiang.co/docs/database/clickhouse)
* 连接 ClickHouse
* 2023-10-02 17:29:48

---

连接 ClickHouse

## 准备

首先您要获取到 ClickHouse 数据库的连接配置，然后参考[IP 白名单](https://majiang.co/docs/ip-allowlist)文档将码匠的 IP 地址添加到数据库网络的白名单中（按需配置）。

## 新建数据源

**新建数据源** -> ​**ClickHouse**​，填写数据源配置信息 -> ​**测试连接**​，连接成功后，选择​**保存**​，该 ClickHouse 数据源即新建完成，并且保存到了您的数据源列表中。

​![](assets/1-20231002172949-ciot8vb.png)​

## 创建查询

点击**新建**创建查询，选择您的 ClickHouse 数据源，然后编写查询，完成后即可点击​**运行**​。

​![](assets/2-20231002172949-5krrpuk.png)​

* [准备](https://majiang.co/docs/database/clickhouse#%E5%87%86%E5%A4%87)
* [新建数据源](https://majiang.co/docs/database/clickhouse#%E6%96%B0%E5%BB%BA%E6%95%B0%E6%8D%AE%E6%BA%90)
* [创建查询](https://majiang.co/docs/database/clickhouse#%E5%88%9B%E5%BB%BA%E6%9F%A5%E8%AF%A2)
