# Prerequisites {#concept_xcs_2hc_ggb .concept}

You can use Hybrid Backup Recovery \(HBR\) to back up files and folders from servers or virtual machines in local data centers and restore these files as required. The following prerequisites are required before you back up data.

**Note:** 

-   For more information, see [Back up files from an ECS instance](../../../../intl.en-US/Back up ECS/Back up files in ECS/Overview.md).
-   To achieve the best backup performance, we recommend that the configurations of a host where a backup client is running meet the following requirements. The host uses a 64-bit CPU with more than two cores and more than 8 GB of available memory.
-   The size of data that a host can back up is determined by available memory resources. For a host with 4 GB of available memory, the maximum number of files that you can back up on the host is one million and the total size of data is 8 TB.

## RAM users and AccessKeys {#section_rth_lhc_ggb .section}

Resource Access Management \(RAM\) enables you to manage user access to Alibaba Cloud resources. You can create and manage multiple RAM users with a single Alibaba Cloud account. You can grant different permissions for each RAM user. This allows each RAM user to have different access permissions on Alibaba Cloud resources.

An AccessKey is required when you activate a backup client. As any leak of an Alibaba Cloud account's AccessKey will expose cloud resources to security risks, we recommend that you use the AccessKey of a RAM user to perform the activation. Before performing a backup job, ensure that you have created a RAM user account and save the AccessKey of the RAM user account.

## Create a client {#section_cnq_phc_ggb .section}

You can use a file client to perform a backup or restore job. However, you must download a file client to a host that is located in a local data center. You can download a file client in the HBR console. Proceed as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

    **Note:** You must log on to the HBR console on an intermediate host with a desktop environment to download a file client. You need to perform this operation if a server or virtual machine where a Linux system is running but without a desktop environment.

2.  At the top of the HBR console, select a region where you need to store backups.

    **Note:** 

    -   If a VPC is used, the region you select must be the same as the region of the VPC where data to be backed up is located.
    -   For optimal backup performance, you must select a region that is in close proximity to the location where data to be backed up is located.
    -   For disaster recovery, you must select a different region for the location where data to be backed up is located. We recommend that you select a distant region to reduce the risk of data loss during a disaster.
3.  In the left-side navigation pane, choose **On-Premises Backup** \> **File Client**.
4.  In the upper-right corner of the page, click **Create Client**.
5.  In the Create Client dialog box, configure the required settings and click **Create**. Settings are described in the following table.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83047/156472015254114_en-US.jpg)

    |Name|Description|
    |:---|:----------|
    |Backup Vault Name|A backup vault is an HBR cloud backup warehouse used to store backup data on the cloud. Backup data from multiple clients can be stored in the same vault.     -   One or more backup vaults available

You can select a backup vault on the drop-down list.

    -   No backup vault available

Click **Create Vault**. Enter the **Backup Vault Name** and **Vault Description** to create a new backup vault. The vault name must be a maximum of 64 characters in length.

 |
    |Client Name|The name of the backup client. The client name must be a maximum of 64 characters in length.|
    |Software Platform|The operating system that is running on the host from which you need to back up data. Valid values:     -   Windows 32-bit
    -   Windows 64-bit
    -   Linux 32-bit
    -   Linux 64-bit
 |
    |Network Type|     -   Virtual Private Cloud \(VPC\): Select this option when the host to be backed up is located in a VPC and in the same region where the backup vault is located.
    -   Public Network: Select this option when VPCs are not applicable.
 |

6.  Click **Create** and then click **Download Client**.

    **Note:** You can install a client to connect a host to HBR. You can also go to the File Client page and download a client at any time.


## Install and activate a client {#section_g3t_wvd_qfb .section}

After you download a file client, you need to install and activate the client. Proceed as follows:

1.  Install a client from an installation package and select an installation folder.

    **Note:** As operation logs and executable files are all stored in the installation folder, you must ensure that the installation folder contains sufficient available space.

    -   If you install a client on Windows, run an installation package, select an installation folder, and follow the instructions to complete the installation.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83047/156472015254107_en-US.png)

    -   If you install a client on Linux, extract an installation package to a folder and run the `./setup` command to install the client.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83047/156472015354108_en-US.png)

2.  After a client is installed, you need to activate the client. Go to the HBR console, in the Create Client dialog box, click **Next** and configure the required settings as described in the following table to activate the client.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83047/156472015354109_en-US.png)

    **Note:** We recommend that you download and install a client before activating the client.

    |Name|Description|
    |:---|:----------|
    |Client IP Address|The IP address of the file client, which must be accessible by the host. The IP address is either an internal IP address or a public IP address. For example, 127.0.0.1 \(default\), 12.34.56.78:8011, and http://87.65.43.21:8443. **Note:** The IP address must be accessible by a browser.

 |
    |AccessKey ID|Download the AccessKey ID and AccessKey Secret of the Alibaba Cloud account where the HBR service is activated.|
    |AccessKey Secret|Download the AccessKey ID and AccessKey Secret of the Alibaba Cloud account where the HBR service is activated.|
    |Create Client Password|Set the logon password of the client. The password must be a minimum of six characters in length.|

3.  Click **Activate Client** to open a web page. You can use this web page to manage the file client. You can use a file client to back up data.

    **Note:** If you fail to activate a client, you can [reactivate the client](../../../../intl.en-US/FAQ/On-premises backup FAQ/Reactivate a file client.md).


## \(Optional\) Create a backup plan and backup policy {#section_ljr_vhc_ggb .section}

Before you perform a backup job, we recommend that you schedule the backup time and interval of the backup job based on your business needs.

-   If no regular backup plan exists, you can skip this step.
-   If you have a regular backup plan, you can perform the following steps to create a backup policy and specify the first backup time and backup interval.

 **Procedure** 

1.  Open a browser and enter `http://localhost:8011` in the address bar and enter the password to log on to an HBR file client.

    **Note:** 

    -   If you perform a backup operation on an intermediate host, you must change `localhost` to the IP address of the server or virtual machine from which you need to back up data.
    -   Port 8011 is the default port that you can use to logon to a file client. If port 8011 on the server or virtual machine is occupied by another application, you can [specify another port number for the file client](../../../../intl.en-US/FAQ/On-premises backup FAQ/How can I change the number of the logon port for a file client?.md).
2.  In the left-side navigation pane, select **Backup Policies**.
3.  On the Backup Polices page, click **Create Policy**.
4.  In the Create Policydialog box, enter the Name, configure the required settings as described in the following table, and click **Submit**.

    |Name|Description|
    |:---|:----------|
    |Name|The name of the policy.|
    |Frequency|Unit:     -   Hour. Valid values: 1 to 23.
    -   Day. Valid values: 1 to 6.
    -   Week. Valid values: 1 to 4.
 |
    |Backup Time|The first backup time. The first backup is a full backup.|
    |Retention|     -   Unit: day, month, and year.
    -   Maximum retention period: 3650 days \(10 years\).
 |


## Subsequent operations {#section_bjj_3pn_mgb .section}

[Back up files from locate data centers](intl.en-US/Back up on-premises severs/Back up files for on-premises severs/Backup files.md)

