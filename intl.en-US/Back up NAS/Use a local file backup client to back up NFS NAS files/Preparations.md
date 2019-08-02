# Preparations {#concept_xcs_2hc_ggb .concept}

You can use HBR to back up NFS NAS files in a local IDC and restore them when necessary. This topic describes the preparations that you need to make before backing up data.

**Note:** 

-   For more information about how to back up NFS NAS files in an ECS instance, see [Back up NAS files](intl.en-US/Back up NAS/Use an ECS file backup client to back up NFS NAS files/Back up NAS files.md#).
-   To achieve the optimal backup speed, we recommend that you run an HBR backup client on a host that uses a 64-bit CPU with at least two cores and has more than 8 GB memory available.
-   The size of data that can be backed up varies depending on available memory resources. For example, with 4 GB memory available, you can back up a maximum number of one million files with a total size of 8 TB.

## RAM user and AccessKey {#section_rth_lhc_ggb .section}

Resource Access Management \(RAM\) is an Alibaba Cloud service that helps you manage user identities and access to your cloud resources. You can create and manage multiple RAM users within a single Alibaba Cloud account. You can grant different permissions to each RAM user, so that RAM users have different access permissions on Alibaba Cloud resources.

An AccessKey is required when you activate a backup client. As any leak of an Alibaba Cloud account's AccessKey will expose cloud resources to security risks, we recommend that you use the AccessKey of a RAM user to perform the activation. Before performing a backup job, ensure that you have [Created a RAM user](../../../../intl.en-US/User Guide/RAM users/Create a RAM user.md#) and [Created an access key for a RAM user](../../../../intl.en-US/User Guide/Security settings/Access keys/Create an access key for a RAM user.md#).

## Add a mount point {#section_yj7_spb_6n8 .section}

In the [NAS console](https://nas.console.aliyun.com), add a mount point for the created NFS NAS file system. For more information, see [Create a mount point](../../../../intl.en-US/Console User Guide/Manage mount points.md#section_6xi_a3u_zkq).

After adding the mount point, click **Manage** next to the file system in the Action column. On the File System Details page that appears, check the mount point path.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/776269/156473853754144_en-US.jpg)

## Mount an NFS NAS file system {#section_ehz_nou_clx .section}

The procedure is as follows:

1.  Run the sudo yum install nfs-utils command to install the NFS client. The CentOS operating system is used in this example. For more information about how to install the NFS client in another Linux operating system, see [Step 1: Install an NFS client](../../../../intl.en-US/Console User Guide/Mount a file system/Mount an NFS file system.md#section_kvj_d02_szj).
2.  After installing the NFS client, mount the NFS file system. For more information, see [Mount an NFS file system in Linux](../../../../intl.en-US/Console User Guide/Mount a file system/Mount an NFS file system.md#).

## Add a client {#section_cnq_phc_ggb .section}

**Note:** 

-   The host that runs the client must have access to the Internet. For ECS instances, you can use the EIP or NAT to access the Internet.
-   Only a small number of control commands are sent during the Internet access, which incurs few traffic fees.

You can use a file client to back up and restore data. Before that, you need to download the file client to a local IDC. You can download the file client in the HBR console. The procedure is as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

    **Note:** If the server or virtual machine runs on a Linux operating system without a GUI installed, you need to use an intermediate host with a GUI as an agent to log on to the HBR console.

2.  At the top of the HBR console, select the region where you want to store backup data.

    **Note:** 

    -   If you use a VPC, the selected region must be the same as the region of the VPC where the data to be backed up resides to ensure a fast backup.
    -   Select a nearby region for better backup performance.
    -   Select a remote region for disaster recovery.
3.  In the left-side navigation pane, choose **On-Premises Backup** \> **File Client**.
4.  On the File Client page, click **Create Client** in the upper-right corner.
5.  In the Create Client dialog box that appears, set the parameters.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/790379/156473853754157_en-US.jpg)

    The following table describes the parameters.

    |Parameter|Description|
    |:--------|:----------|
    |Backup Vault Name|Specify the backup vault. A backup vault is a repository used by HBR to store backup data on the cloud. You can back up data from multiple clients to the same vault.     -   If you have created backup vaults:

Click Select Vault and select a vault from the drop-down list.

    -   If you have not created any backup vaults:

Click **Create Vault**, and then set **Backup Vault Name** and **Vault Description**. The vault name must not exceed 64 bytes in length.

 |
    |Client Name|The name of the client. The client name must not exceed 64 bytes in length.|
    |Software Platform|The operating system of the host where the data to be backed up resides. Valid values:     -   Linux 32-bit
    -   Linux 64-bit
 |
    |Network Type|     -   Public Network: Select this option when VPCs are inapplicable.
    -   Virtual Private Cloud \(VPC\): Select this option when the host resides in a VPC and is in the same region as the backup vault.
 |

6.  Click **Create** and then **Download Client**.

    **Note:** After installing the client by using the client installation package, you can use the client to connect to HBR. You can also go to the File Client page and choose More \> Download Client in the Actions column to download the client installation package at any time.


## Install and activate the client {#section_g3t_wvd_qfb .section}

After the client installation package is downloaded, install and activate the client. The procedure is as follows:

1.  Run the tar -xzvf hbr-install-xxx-linux-amd64.tar.gz command to decompress the downloaded client installation package to a specific directory. Then, run the `./setup` command to enable HBR.

    **Note:** Make sure that the disk where the installation directory resides has available space because running logs and execution files are stored in this directory.

2.  After the client is installed, activate it. Log on to the HBR console. In the Create Client dialog box, click **Next** and then set the parameters as instructed in the following table.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/790379/156473853854159_en-US.jpg)

    |Parameter|Description|
    |:--------|:----------|
    |Client IP Address|The IP address of the file client that your current host can access. It can be a private or public IP address. For example, you can enter 127.0.0.1 \(default\), 12.34.56.78:8011, or http://87.65.43.21:8443. **Note:** The IP address must be reachable from your current browser.

 |
    |AccessKey Id|The AccessKey ID of the RAM user. Obtain the AccessKey ID and AccessKey Secret of the RAM user for which HBR is activated.|
    |AccessKey Secret|The AccessKey Secret of the RAM user. Obtain the AccessKey ID and AccessKey Secret of the RAM user for which HBR is activated. .|
    |Create Client Password|The logon password of the client. The password must be at least six characters in length.|
    |Confirm Password|The confirm password, which must be the same as the password entered above.|

3.  Click **Activate Client**. The file client operation page automatically appears in the browser. Then, you can use the file client to back up data.

    **Note:** If the file client fails to be activated, you can [reactivate the client](../../../../intl.en-US/FAQ/On-premises backup FAQ/Reactivate a file client.md).


