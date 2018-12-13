# 安装ECS客户端失败，错误提示“客户端启动失败” {#concept_dnq_3fs_bgb .concept}

## 问题现象 {#section_f3z_l1l_5fb .section}

安装ECS客户端，状态显示安装失败。查看失败原因，提示“客户端启动失败”。

## 问题排查 {#section_n5q_q3s_bgb .section}

[远程连接ECS实例](../../../../intl.zh-CN/用户指南/连接实例/连接实例概述.md)，检查该ECS实例是否安装360等杀毒软件。运行杀毒软件会导致ECS备份客户端安装失败。

## 解决方法 {#section_ksp_qgs_bgb .section}

您可以先在ECS实例中卸载ECS备份客户端，停止杀毒软件，然后重新安装ECS客户端。具体操作如下：

1.  [在ECS实例中卸载ECS备份客户端](intl.zh-CN/常见问题/如何登录ECS实例卸载HBR客户端.md)。
2.  停止杀毒软件。
3.  登录[混合云备份管理控制台](https://hbr.console.aliyun.com)。
4.  在左侧导航栏，选择**云端备份** \> **ECS客户端**。
5.  找到客户端安装失败的ECS实例。在该实例相应的操作列表中，选择**操作** \> **重新安装**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/78562/154466700334050_zh-CN.png)


