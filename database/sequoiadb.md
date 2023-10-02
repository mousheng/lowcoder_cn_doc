# 连接 SequoiaDB

![](../assets/1-20231002173018-7fvkvk5.png)​

[SequoiaDB](https://www.sequoiadb.com/cn/) 是一款分布式 NoSQL 数据库管理系统，由中软国际自主研发。它支持多种数据模型，包括关系型、文档型、键值型等，能够灵活地满足不同场景下的数据管理需求。SequoiaDB 采用分布式架构，支持自动水平扩展，能够处理海量数据的存储和查询。它还提供了高可靠性的容错机制和实时备份功能，确保数据安全可靠。此外，SequoiaDB 还提供了全面的管理工具和 API 接口，使得数据库的配置、监控和管理变得更加便捷和高效。

目前Lowcoder已经实现了与 SequoiaDB 数据源的连接，支持对 SequoiaDB 数据进行增、删、改、查， 同时还支持将数据绑定至各种组件，并通过简单的代码实现数据的可视化和计算等操作，能让您快速、高效地搭建应用和内部系统。

## 准备

正式开始前，您需要获取 SequoiaDB 数据库的连接配置，并参考[IP 白名单](https://majiang.co/docs/ip-allowlist)文档将Lowcoder的 IP 地址添加到数据库网络的**白名单**中（按需配置）。

## 新建数据源

在[Lowcoder主页](https://cloud.majiang.co/apps)左下角，点击**数据源**进入当前企业的数据源管理界面，然后点击右上角 **+ 新建数据源** > ​**SequoiaDB**​，填写您的 SequoiaDB 数据库的配置信息。点击​**测试连接**​，提示**连接成功**后再点击**保存**按钮，该 SequoiaDB 数据源即新建完成，并且保存至企业的数据源列表中。

![](../assets/2-20231002173018-akzeanc.png)​

## 创建查询

在应用编辑页面，点击**新建**创建查询，选择您的 SequoiaDB 数据源，然后编写 SQL 查询语句。Lowcoder中支持 **SQL 模式**和 **GUI模式**​，让您能够更加灵活便捷地操作数据。关于在Lowcoder中使用 SQL 的详细教程，可参阅文档[使用 SQL](https://majiang.co/docs/using-sql)。

![](../assets/3-20231002173018-mpuajv4.png)​

编写完成后，点击**运行**可查看查询的执行结果。如果将运行结果与Lowcoder中[组件](https://majiang.co/docs/component-guides)的数据字段绑定，就能使数据可视化。

![](../assets/4-20231002173018-glsz8wm.png)​
