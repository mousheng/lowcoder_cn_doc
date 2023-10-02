# 连接 PolarDB

---

* [https://majiang.co/docs/database/polardb](https://majiang.co/docs/database/polardb)
* 码匠已经实现了与 PolarDB 数据库的连接，支持对 PolarDB 数据进行增、删、改、查， 同时还支持将数据绑定至各种组件，并通过简单的代码实现数据的可视化和计算等操作，能让您快速、高效地搭建应用和内部系统。
* 2023-10-02 17:30:09

---

连接 PolarDB

​![](assets/1-20231002173010-m0tu9z3.png)​

[PolarDB](https://www.aliyun.com/product/polardb) 是阿里云自主研发的新一代关系型云原生数据库，它基于分布式存储和计算技术，能够提供高性能、高可用和强一致性的数据存储和管理服务。相比于传统的关系型数据库，PolarDB 采用了多副本存储、多副本数据同步、数据分片等技术，能够支持海量数据存储和处理，并且具有更高的可扩展性和可用性。

码匠目前支持了 PolarDB 的 **MySQL** 引擎。通过与 PolarDB 数据源连接，可对 PolarDB 数据进行增、删、改、查。 同时还支持将数据绑定至各种组件，并通过简单的代码实现数据的可视化和计算等操作，能让您快速、高效地搭建应用和内部系统。

## 准备

正式开始前，您需要获取 PolarDB 数据库的连接配置，并参考[IP 白名单](https://majiang.co/docs/ip-allowlist)文档将码匠的 IP 地址添加到数据库网络的**白名单**中（按需配置）。

## 新建数据源

在[码匠主页](https://cloud.majiang.co/apps)左下角，点击**数据源**进入当前企业的数据源管理界面，然后点击右上角 **+ 新建数据源** > ​**PolarDB**​，填写您的 PolarDB 数据库的配置信息。点击​**测试连接**​，提示**连接成功**后再点击**保存**按钮，该 PolarDB 数据源即新建完成，并且保存至企业的数据源列表中。

​![](assets/2-20231002173010-70xmn2k.png)​

## 创建查询

在应用编辑页面，点击**新建**创建查询，选择您的 PolarDB 数据源，然后编写 SQL 查询语句。码匠中支持 **SQL 模式**和 **GUI模式**​，让您能够更加灵活便捷地操作数据。关于在码匠中使用 SQL 的详细教程，可参阅文档[使用 SQL](https://majiang.co/docs/using-sql)。

​![](assets/3-20231002173009-e9dxky1.png)​

编写完成后，点击**运行**可查看查询的执行结果。如果将运行结果与码匠中[组件](https://majiang.co/docs/component-guides)的数据字段绑定，就能使数据可视化。

​![](assets/4-20231002173010-7d4hbs7.png)​
