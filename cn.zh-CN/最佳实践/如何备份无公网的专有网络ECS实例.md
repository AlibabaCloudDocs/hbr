# 如何备份无公网的专有网络ECS实例 {#task440 .task}

北京、上海、杭州、深圳地域中的ECS实例可以直接使用[ECS备份功能](../../../../intl.zh-CN/ECS备份教程/文件备份/概述.md)进行备份。对于不支持ECS备份功能的地域，当多台ECS实例在同一个VPC网络中，且无公网时，可以通过搭建NAT网关来访问混合云备份控制台并[安装本地备份客户端](../../../../intl.zh-CN/ECS备份教程/文件备份/准备工作.md)。在混合云备份控制台配置本地备份客户端时，您可以根据ECS实例类型选择备份时使用的网络类型。本文主要为您介绍如何搭建NAT网关。

1.   登录云服务器ECS控制台界面，查看ECS实例详情。 ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40362/156471512421586_zh-CN.png)

  
2.   在配置信息栏中查看专有网络VPC。 ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40362/156471512421587_zh-CN.png)

  
3.   登录NAT网关控制台界面，单击**创建NAT网关**。 ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40362/156471512521588_zh-CN.png)

  
4.   根据ECS的信息选择地域、VPC ID、规格,计费周期默认为按天。然后购买并开通NAT网关。 ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40362/156471512521589_zh-CN.png)

  
5.   开通成功后，进入NAT网关控制台，配置NAT网关。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40362/156471512521590_zh-CN.png)

  
6.   选择创建的NAT网关，单击**更多操作** \> **绑定弹性公网IP**。 ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40362/156471512521591_zh-CN.png)

  
7.   选择弹性公网IP和交换机，单击确定即可绑定。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40362/156471512621592_zh-CN.png)

  

    **说明：** 若没有弹性公网IP，可先进行申请。

8.   系统会自动创建一个默认的SNAT表,可查看相关信息。 ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40362/156471512621593_zh-CN.png)

  
9.  NAT网关创建完成后，即可在备份ECS时选择VPC网络。 

