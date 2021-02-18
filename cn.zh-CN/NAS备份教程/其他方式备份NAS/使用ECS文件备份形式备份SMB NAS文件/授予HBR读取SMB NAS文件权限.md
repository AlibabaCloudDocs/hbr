# 授予HBR读取SMB NAS文件权限

在基于AD（Active Directory）权限控制的SMB类型NAS文件系统中，由于混合云备份服务（HBR）没有读取SMB类型NAS文件的权限，导致HBR无法进行备份，此时您需要通过授予HBR读取SMB类型NAS文件权限来完成备份。本文介绍Windows ECS授予HBR读取SMB类型NAS文件权限的操作方法。

-   基于AD权限控制的SMB类型NAS文件系统中，HBR备份SMB类型NAS文件时，因为没有权限读取这些文件而无法进行备份。对于这种情况，建议用户在挂载SMB类型NAS文件系统的Windows ECS上，通过Window服务来授予阿里云混合云备份服务（Aliyun Hybrid Backup Service）访问该文件系统的权限。
-   本文提供的解决方法需要安装一个ECS文件备份客户端。文件备份软件使用费详情，请参见[混合云备份详细价格信息](https://cn.aliyun.com/price/detail/hbr)。

## 步骤1：安装ECS文件备份客户端

安装ECS文件备份客户端。具体操作，请参见[创建ECS文件备份客户端](t789612.dita#concept_977495/section_wj8_7oh_c66)。

## 步骤2：授予HBR客户端权限

请按照如下步骤授予HBR客户端读取文件权限。

1.  连接ECS实例。具体操作，请参见[连接ECS实例](/cn.zh-CN/实例/连接实例/连接方式概述.md)。

2.  使用组合键`Win+R`，打开**运行**工具，之后输入`services.msc`，单击**确定**。

    ![service.msc](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3263682161/p241015.png)

3.  在服务中找到Aliyun Hybrid Backup Service。单击右键选择**属性**。

    ![属性](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3263682161/p241006.png)

4.  在对话框中，选择**登录**页签。

5.  选中**此账号**，通过浏览方式输入对该NAS文件系统有完全访问权限的账号和密码。单击**确定**。

    ![input](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3263682161/p241008.png)

6.  重启Aliyun Hybrid Backup Service服务。

    ![restart](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3263682161/p241016.png)


## 步骤3：创建备份计划

创建备份计划。具体操作，请参见[创建备份计划](t789612.dita#concept_977495/section_kmh_tmi_ee4)。

