# 注册MySQL

使用混合云备份服务（HBR）来备份ECS实例中部署的MySQL数据库前，您需要在HBR控制台注册数据库实例。

已完成准备工作。更多信息，请参见[准备工作](/cn.zh-CN/ECS备份教程/ECS数据库备份/MySQL备份/准备工作.md)。

-   注册MySQL实例需要配置MySQL连接信息，实例注册完成后混合云备份服务会在MySQL的节点上安装ECS备份客户端。
-   MySQL实例注册后，您可以查看MySQL实例中节点的备份客户端安装状态，确保需要备份的节点已经成功安装了ECS备份客户端。然后结合业务场景升级、卸载或删除ECS备份客户端。

## 注册数据库实例

1.  登录[混合云备份管理控制台](https://hbr.console.aliyun.com)。

2.  在左侧导航栏，选择**备份** \> **ECS数据库备份**。

3.  在ECS数据库备份页面，单击**MySQL**。

4.  在页面上方，选择要备份的ECS实例所在的地域。

5.  在页面右上角，单击**注册数据库实例**。

6.  在**选择数据库实例**页签，系统会自动加载该地域的所有数据库资源。选择目标数据库。单击**下一步**。

7.  在**配置认证信息**页签，按照以下说明配置所需信息，单击**确定**。

    |参数|说明|
    |:-|:-|
    |数据库用户名|管理数据库实例的用户名。|
    |密码|管理数据库实例的用户密码。|

    实例注册完成后，在数据库实例页签，可以查看实例的注册信息及状态。


[预检MySQL](/cn.zh-CN/ECS备份教程/ECS数据库备份/MySQL备份/预检MySQL.md)

