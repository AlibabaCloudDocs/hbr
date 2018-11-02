# 阿里云ECS在VPC网络下备份 {#task440 .task}

本文介绍如何为ECS搭建NAT网关来进行VPC网络备份。当多台ECS在同一个VPC网络中，且无公网时，可以通过搭建NAT网关来使用VPC网络进行备份。

搭建NAT网关

1.   登录云服务器ECS控制台界面，查看ECS实例详情。 ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40362/154115283921586_zh-CN.png)

  
2.   在配置信息栏中查看专有网络VPC。 ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40362/154115283921587_zh-CN.png)

  
3.   登录NAT网关控制台界面，单击**创建NAT网关**。 ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40362/154115283921588_zh-CN.png)

  
4.   根据ECS的信息选择地域、VPC ID、规格,计费周期默认为按天。然后购买并开通NAT网关。 ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40362/154115283921589_zh-CN.png)

  
5.   开通成功后，进入NAT网关控制台，配置NAT网关。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40362/154115283921590_zh-CN.png)

  
6.   选择创建的NAT网关，单击**更多操作** \> **绑定弹性公网IP**。 ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40362/154115284021591_zh-CN.png)

  
7.   选择弹性公网IP和交换机，单击确定即可绑定。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40362/154115284021592_zh-CN.png)

  

    **说明：** 若没有弹性公网IP，可先进行申请。

8.   系统会自动创建一个默认的SNAT表,可查看相关信息。 ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40362/154115284021593_zh-CN.png)

  
9.   NAT网关创建完成后，即可在备份ECS时选择VPC网络。 

