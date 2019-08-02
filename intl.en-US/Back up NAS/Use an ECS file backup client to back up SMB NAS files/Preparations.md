# Preparations {#concept_960946 .concept}

You can use HBR to back up SMB NAS files and restore them when necessary. This topic describes the preparations that you need to make before backing up data.

## Authorize roles {#section_veb_n4z_vto .section}

When using Hybrid Backup Recovery \(HBR\) to back up files from ECS instances, you must authorize two roles: AliyunHBRDefaultRole and AliyunECSAccessingHBRRole. After the authorization, HBR and ECS are accessible by each other. Proceed as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  Choose **ECS Backup** \> **ECS File Backup**.
3.  Authorization pages appear one by one, which require you to confirm the authorization of these roles.

## Install Cloud Assistant {#section_b2l_3bs_uis .section}

An ECS backup client must work with Cloud Assistant. By default, Cloud Assistant clients are installed on ECS instances that are created after December 1, 2017. To back up ECS instances that you bought before December 1, 2017, you must [install the Cloud Assistant client](../../../../../intl.en-US/Deployment & Maintenance/Cloud assistant/Configure the cloud assistant client.md).

## Add a mount point {#section_i53_b4b_geh .section}

In the [NAS console](https://nas.console.aliyun.com), add a VPC-type mount point for the created SMB NAS file system. For more information about how to add a VPC-type mount point, see [Create a mount point](../../../../../intl.en-US/Console User Guide/Manage mount points.md#section_6xi_a3u_zkq).

After adding the mount point, click **Manage** next to the file system in the Action column. On the File System Details page that appears, check the mount point path.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/776269/156473476154144_en-US.jpg)

## Create an ECS instance {#section_dzp_oip_ssf .section}

Create an ECS instance in the VPC where the mount point for the NAS file system resides. For more information, see [Create an instance by using the wizard](../../../../../intl.en-US/Instances/Create an instance/Create an instance by using the wizard.md#).

**Note:** We recommend that you create an ECS instance in Windows 2012. In Windows 2016, you must run Alibaba Cloud HBR as the administrator due to operating system permission control.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/776269/156473476154148_en-US.jpg)

