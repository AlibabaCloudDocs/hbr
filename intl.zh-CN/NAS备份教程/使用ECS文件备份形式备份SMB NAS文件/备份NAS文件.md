# 备份NAS文件 {#concept_977495 .concept}

您可以使用混合云备份服务（HBR）备份ECS实例中的NAS文件，并可以在文件丢失或受损时进行恢复。本文为您介绍如何备份ECS实例中的NAS文件。

## 前提条件 {#section_60b_01k_fr6 .section}

您已经完成了[准备工作](intl.zh-CN/NAS备份教程/使用ECS文件备份形式备份NFS NAS文件/准备工作.md#)。

## 步骤一：创建ECS文件备份客户端 {#section_wj8_7oh_c66 .section}

请按照如下步骤创建ECS文件备份客户端：

1.  登录[混合云备份管理控制台](https://hbr.console.aliyun.com)。
2.  在左侧导航栏，选择**ECS备份** \> **ECS文件备份**。
3.  在页面上方选择需要备份的ECS实例所在的地域。
4.  在ECS文件备份页面，单击**添加ECS示例**。
5.  在添加ECS实例页面，选择已有的备份仓库或单击**新建仓库**，然后选择[准备工作](intl.zh-CN/NAS备份教程/使用ECS文件备份形式备份SMB NAS文件/准备工作.md#)中创建的ECS实例。
6.  单击**创建**，几分钟后即可看到ECS实例页签下显示ECS实例已激活。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/789612/156466416850683_zh-CN.jpg)


## 步骤二：创建备份计划 {#section_kmh_tmi_ee4 .section}

创建ECS文件备份客户端后，按照如下步骤创建备份计划：

1.  在已添加的ECS实例右侧，单击操作栏下的**备份**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/789612/156466416850684_zh-CN.jpg)

2.  在创建备份计划页面，按照以下说明配置参数，然后单击**创建**。

    各项参数说明如下：

    **说明：** NAS不支持使用VSS（Volume Shadow\(Copy\)Service）。

    |参数|说明|
    |--|--|
    |备份计划名称|为该备份计划命名。可不填，默认名字随机分配。|
    |备份路径|填写NAS挂载点路径。|
    |备份起始时间|选择备份开始执行的时间。时间精确到秒。|
    |备份执行间隔|选择增量备份的频率。时间单位：小时、天、周。|
    |备份保留时间|选择保留该备份的时间。时间单位：天、周、月、年。|
    |是否使用流量控制|流量控制可以帮助您在业务高峰期，控制备份文件目录的流量，以免影响正常业务。 **说明：** 如果选择**使用**，您需要根据业务情况，选择限流时间段，输入限流时间段内备份可使用的最大流量，然后单击**添加**。

 |


## 步骤三：执行备份任务 {#section_iyc_8rj_4jg .section}

创建备份计划完成后，您可以在备份计划和任务页签中查看已创建的备份计划。此时，将按照设定的备份计划进行NAS备份，您还可以选择**立即执行**备份计划。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/789612/156466416850690_zh-CN.jpg)

随后，您可以在备份计划和任务页签中查看该备份任务的进度。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/789612/156466416850692_zh-CN.png)

