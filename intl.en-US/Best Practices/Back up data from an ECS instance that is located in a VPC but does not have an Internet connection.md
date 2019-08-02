# Back up data from an ECS instance that is located in a VPC but does not have an Internet connection {#task440 .task}

For ECS instances that are located in the China \(Beijing\), China \(Shanghai\), China \(Hangzhou\), or China \(Shenzhen\) region, you can use [ECS backup clients](../../../../intl.en-US/Back up ECS/Back up files in ECS/Overview.md) to back up data. For regions that do not support ECS backup clients, you can create a NAT gateway to access the Hybrid Backup Recovery \(HBR\) console and [install on-premises backup clients](../../../../intl.en-US/Back up ECS/Back up files in ECS/Prerequisites.md) to back up data. You can use this solution when multiple ECS instances are located in the same VPC but do not have have any Internet connection. When you configure an on-premises backup client in the HBR console, you can select a network type based on the information of an ECS instance. This topic describes how to create a NAT gateway.

1.  Log on to the ECS console and view the details of the ECS instance where data needs to be backed up.
2.  In the Configuration Information section, you can view the VPC that hosts the ECS instance.
3.  Log on to the NAT Gateway console, and click **Create NAT Gateway**.
4.  Select a region, VPC ID, and specification based on the information of the ECS instance. The default billing cycle is one day. Purchase and activate NAT Gateway.
5.  After the service is activated, you can log on to the NAT Gateway console and configure the NAT gateway.
6.  Select the new NAT gateway, and choose **More** \> **Bind EIP**.
7.  Select an elastic IP address \(EIP\) and vSwitch, and click OK to bind the EIP. 

    **Note:** If no EIP is available, you need to first apply for an EIP.

8.  A default SNAT table is created. You can view the related information.
9.  After a NAT gateway is created, you can select VPC as the network type when you back up data from the ECS instance.

