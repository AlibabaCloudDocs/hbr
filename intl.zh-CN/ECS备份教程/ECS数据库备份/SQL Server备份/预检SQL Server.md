# 预检SQL Server

使用混合云备份服务（HBR）备份ECS实例中部署的SQL Server数据库前，您可以通过预检功能提前发现不适合备份的场景，避免发生备份失败等异常问题。

已完成注册SQL Server。更多信息，请参见[注册SQL Server](/intl.zh-CN/ECS备份教程/ECS数据库备份/SQL Server备份/注册SQL Server.md)。

## 操作步骤

1.  登录[混合云备份管理控制台](https://hbr.console.aliyun.com)。

2.  在左侧导航栏，选择**备份** \> **ECS数据库备份**。

3.  在ECS数据库备份页面，单击**SQL Server**。

4.  在页面上方，选择要备份的ECS实例所在的地域。

5.  在数据库实例页签，找到目标SQL Server实例，在其右侧的**操作**列表，单击**预检**。

6.  在**预检**页面，单击**开始检查**。

    您可以单击**查看上次预检结果**，查看上一次备份预检的结果。包含如下检查项：

    |检查项|说明|
    |---|--|
    |OSS连接性检查|检查SQL Server实例和所在地域OSS的VPC网络连通性。 若不通过，则无法执行备份和恢复操作。|
    |管控网络连接性检查|检查实例至管控网络的连通性。若不通过，所有针对此数据库实例的操作均无法执行。|
    |恢复模式检查|检查数据库的恢复模式。若不通过，则界面提示的数据库无法进行增量或日志备份。**说明：**

    -   由于SQL Server存在限制，检查提示不通过的数据库只支持简单恢复模式，无法进行日志备份。
    -   master数据库只支持全量备份。若配置为增量备份和日志备份，HBR默认会转换为全量备份。
    -   您可以参考SQL Server产品文档，修改恢复模式。更多信息，请参见[查看或更改数据库的恢复模式 \(SQL Server\)](https://docs.microsoft.com/zh-cn/sql/relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server?view=sql-server-ver15)。 |
    |SQL Server数据库状态检查|检查SQL Server实例是否在线。若不通过，则界面提示的数据库无法进行备份和恢复操作。|

    等待约1分钟，显示如下，则表示预检完成。

    ![sqlserver](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3208725161/p247037.png)

    当存在异常的检查项时，请根据界面提示确认对应数据库是否影响备份和恢复操作。

    -   若无影响，则预检完成。
    -   若有影响，请参考检查项说明定位处理。

[备份SQL Server](/intl.zh-CN/ECS备份教程/ECS数据库备份/SQL Server备份/备份SQL Server.md)

