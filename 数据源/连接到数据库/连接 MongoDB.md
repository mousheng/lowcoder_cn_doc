# 连接 MongoDB

---

* [https://majiang.co/docs/database/mongodb](https://majiang.co/docs/database/mongodb)
* 连接 MongoDB
* 2023-10-02 17:28:47

---

连接 MongoDB

## 准备

首先您要获取到 MongoDB 数据库的连接配置，然后参考[IP 白名单](https://majiang.co/docs/ip-allowlist)文档将码匠的 IP 地址添加到数据库网络的白名单中（按需配置）。

## 新建数据源

**新建数据源** -> ​**MongoDB**​，连接方式不同，需填写的配置信息不同。示例如下：

* URI 连接

​![](assets/mongodb-1-20231002172847-bjy2h3z.png)​

* 常规连接

​![](assets/mongodb-2-20231002172847-7d11q1d.png)​

填写完成数据源配置信息​**-&gt;测试连接**​，连接成功后，选择​**保存**​，该 MongoDB 数据源即新建完成，并且保存到了您的数据源列表中。

## 创建查询

创建查询 `query1`​，选择您的 MongoDB 数据源，然后对查询的内容进行设置，设置完成后，即可点击​**运行**​。

下方案例展示了使用 MongoDB 查询查询 `goods`​ 集合下的所有文档。

​![](assets/mongodb-3-20231002172847-zyk4pgx.png)​

* [准备](https://majiang.co/docs/database/mongodb#%E5%87%86%E5%A4%87)
* [新建数据源](https://majiang.co/docs/database/mongodb#%E6%96%B0%E5%BB%BA%E6%95%B0%E6%8D%AE%E6%BA%90)
* [创建查询](https://majiang.co/docs/database/mongodb#%E5%88%9B%E5%BB%BA%E6%9F%A5%E8%AF%A2)
