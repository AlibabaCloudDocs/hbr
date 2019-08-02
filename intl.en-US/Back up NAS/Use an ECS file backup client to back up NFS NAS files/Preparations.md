# Preparations {#concept_960606 .concept}

You can use HBR to back up NFS NAS files and restore them when necessary. This topic describes the preparations that you need to make before backing up data.

## Authorize roles {#section_yxn_q0w_idg .section}

When using Hybrid Backup Recovery \(HBR\) to back up files from ECS instances, you must authorize two roles: AliyunHBRDefaultRole and AliyunECSAccessingHBRRole. After the authorization, HBR and ECS are accessible by each other. Proceed as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  Choose **ECS Backup** \> **ECS File Backup**.
3.  Authorization pages appear one by one, which require you to confirm the authorization of these roles.

## Install Cloud Assistant {#section_kg5_v9q_7yn .section}

An ECS backup client must work with Cloud Assistant. By default, Cloud Assistant clients are installed on ECS instances that are created after December 1, 2017. To back up ECS instances that you bought before December 1, 2017, you must [install the Cloud Assistant client](../../../../../intl.en-US/Deployment & Maintenance/Cloud assistant/Configure the cloud assistant client.md).

## Add a mount point {#section_cn8_ke7_s55 .section}

In the [NAS console](https://nas.console.aliyun.com), add a VPC-type mount point for the created NFS NAS file system. For more information about how to add a VPC-type mount point, see [Create a mount point](../../../../../intl.en-US/Console User Guide/Manage mount points.md#section_6xi_a3u_zkq).

After adding the mount point, click **Manage** next to the file system in the Action column. On the File System Details page that appears, check the mount point path.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/776269/156473508754144_en-US.jpg)

## Create an ECS instance {#section_j39_3f9_zqi .section}

Create an ECS instance in the VPC where the mount point for the NAS file system resides. The CentOS operating system is used in this example. For more information, see [Create an instance by using the wizard](../../../../../intl.en-US/Instances/Create an instance/Create an instance by using the wizard.md#).

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/776269/156473508754148_en-US.jpg)

## Mount the NFS NAS file system to the ECS instance {#section_q1j_jug_9iu .section}

The procedure is as follows:

1.  Run the sudo yum install nfs-utils command to install the NFS client. The CentOS operating system is used in this example. For more information about how to install the NFS client in another Linux operating system, see [Step 1: Install an NFS client](../../../../../intl.en-US/Console User Guide/Mount a file system/Mount an NFS file system.md#section_kvj_d02_szj).
2.  After installing the NFS client, mount the NFS file system. For more information, see [Mount an NFS file system in Linux](../../../../../intl.en-US/Console User Guide/Mount a file system/Mount an NFS file system.md#).

