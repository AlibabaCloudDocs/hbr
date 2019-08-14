# Prerequisites {#concept_is4_25b_wfb .concept}

Hybrid Backup Recovery \(HBR\) allows you to backup data from workflow-based data sources. Supported data sources include SAP HANA, SQL Server, Oracle, MySQL, MongoDB, and Hyper-V. The following prerequisites are required before you perform a backup job.

## RAM users and AccessKeys {#section_z4n_bhk_5fb .section}

Resource Access Management \(RAM\) enables you to manage user access to Alibaba Cloud resources. You can create and manage multiple RAM users with a single Alibaba Cloud account. You can grant different permissions for each RAM user. This allows each RAM user to have different permissions to access Alibaba Cloud resources.

An AccessKey is required when you activate a backup client. As any leak of an Alibaba Cloud account's AccessKey will expose cloud resources to security risks, we recommend that you use the AccessKey of a RAM user to perform the activation. Before performing a backup job, ensure that you have [Created a RAM user](../../../../intl.en-US/User Guide/RAM users/Create a RAM user.md#) and [Created an access key for a RAM user](../../../../intl.en-US/User Guide/Security settings/Access keys/Create an access key for a RAM user.md#).

## Download a client {#section_hkk_sds_5fb .section}

You can use HBR backup clients to perform backup and restore jobs. You can perform the following steps to download a backup client to a server or virtual machine to be backed up.

1.  In the left-side navigation pane, choose **On-Premises Backup** \> **File Client**.
2.  In the upper-right corner, click **Create Client**.
3.  In the Create Client dialog box, configure the required settings and click **Create**. Settings are described in the following table.

    |Name|Description|
    |:---|:----------|
    |Backup Vault Name|A backup vault is an HBR cloud warehouse used to store backup data on the cloud. Backup data from multiple clients can be stored in the same vault.     -   One or more backup vaults available

You can select a backup vault on the drop-down list.

    -   No backup vault available

Click **Create Vault**. Enter the **Backup Vault Name** and **Vault Description** to create a new backup vault. The vault name must be a maximum of 64 characters in length.

 |
    |Client Name|The name of the backup client. The client name must be a maximum of 64 characters in length.|
    |Software Platform|The operating system that is running on a host from which you need to back up data. Valid values:     -   Windows 32-bit
    -   Windows 64-bit
    -   Linux 32-bit
    -   Linux 64-bit
 |
    |Network Type|     -   Virtual Private Cloud \(VPC\): Select this option when the host to be backed up is located in a VPC and in the same region where the backup vault is located.
    -   Public Network: Select this option when VPCs are not applicable.
 |

4.  Click **Download Client**.

    **Note:** You can install a client to connect a host to Hybrid Backup Recovery \(HBR\). You can also go to the File Client page and download a client at any time.


## Install and activate a client {#section_g3t_wvd_qfb .section}

After downloading a client and certificate to a server or virtual machine from which you need to back up data, you need to install the client. Proceed as follows:

1.  Install a client from an installation package and select an installation folder.

    **Note:** As operation logs and an executable file are all stored in the installation folder, you must ensure that enough space is available.

    -   If you install a client on Windows, run an installation package, select an installation folder, and follow the instructions to complete the installation.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83047/156576384354107_en-US.png)

    -   If you install a client on Linux, extract an installation package to a folder and run the `./setup` command to install the client.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83047/156576384454108_en-US.png)

2.  After a client is installed, you need to activate the client. Go to the HBR console. In the Create Client dialog box, click **Next**, and configure the required settings as described in the following table to activate the client.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83047/156576384454109_en-US.png)

    **Note:** We recommend that you download and install a client before activating the client.

    |Name|Description|
    |:---|:----------|
    |Client IP address|The IP address of the file client. The host you are working with must be able to access the IP address of the file client. The IP address is either an internal IP address or public IP address. For example, 127.0.0.1 \(default\), 12.34.56.78:8011, and http://87.65.43.21:8443. **Note:** The IP address must be accessible by a browser.

 |
    |AccessKey ID|Download the AccessKey ID and AccessKey Secret of the Alibaba Cloud account where the HBR service is activated.|
    |AccessKey Secret|Download the AccessKey ID and AccessKey Secret of the Alibaba Cloud account where the HBR service is activated.|
    |Create Client Password|Set the logon password of the client. The password must be a minimum of six characters in length.|

3.  Click **Activate Client** to open a web page. You can use this web page to manage the file client. You can use a file client to back up data.

If you fail to activate a client, you can use one of the following methods to reactivate the client:

-   **Reactivate a client in the console**

    Go to the File Client page, and click **Activate Client** in the Actions column of a failed client to reactivate the client.

-   **Reactivate a client on a web page**

    Go to the File Client page and click **Download Certificate** in the Actions column. Open a browser and enter `http://localhost:8011` in the address bar to open the Initialize Register page. Configure the required settings as described in the following table and click **Register** to activate the client.

    |Name|Description|
    |:---|:----------|
    |Upload Certificate|You can upload the token you have downloaded from the console. The token is used as a certificate. The validity period of each certificate is two days. You must download a new certificate to register a client when the certificate in use expires.|
    |AccessKey ID and AccessKey Secret|Download the AccessKey ID and AccessKey Secret of the Alibaba Cloud account where the HBR service is activated.|
    |Network Type|     -   Virtual Private Cloud \(VPC\): Select this option when the host to be backed up is located in a VPC and in the same region where the backup vault is located.
    -   Classic Network: Select this option when VPCs are not applicable.
 |
    |Password|Set the logon password of the client. The password must be a maximum of six characters in length.|
    |Encrypt AccessKey|If you use the password to encrypt the AccessKey, you must enter the password after each restart.|

    If you perform a backup operation on an intermediate host, you must change `localhost` to the IP address of the server or virtual machine from which you back up data.

    Port 8011 is the default port that you can use to logon to a file client. If port 8011 on the server or virtual machine is occupied by another application, you can [specify another port number for the file client](../../../../intl.en-US/FAQ/On-premises backup FAQ/How can I change the number of the logon port for a file client?.md).


## \(Optional\) Create a backup plan and backup policy {#section_acl_xzb_wfb .section}

Before you perform a backup job, we recommend that you schedule the backup time and interval of the backup job based on your business requirements.

-   If no regular backup plan exists, you can skip this step.
-   If you have a regular backup plan, you can perform the following steps to create a backup policy and specify the first backup time and backup interval.

Proceed as follows:

1.  Open a browser and enter `http://localhost:8011` in the address bar and enter the password to log on to an HBR file client.

    **Note:** 

    -   If you perform a backup operation on an intermediate host, you must change `localhost` to the IP address of the server or virtual machine from which you need to back up data.
    -   Port 8011 is the default port that you can use to logon to a file client. If port 8011 on the server or virtual machine is occupied by another application, you can [specify another port number for the file client](../../../../intl.en-US/FAQ/On-premises backup FAQ/How can I change the number of the logon port for a file client?.md).
2.  In the left-side navigation pane, select **Backup Policies**.
3.  On the Backup Polices page, click **Create Policy**.
4.  In the Create Policy dialog box, enter the Name, configure the required settings as described in the following table, and click **Submit**.

    |Name|Description|
    |:---|:----------|
    |Name|The name of the backup policy.|
    |Frequency|Unit:     -   Hour. Valid values: 1 to 23.
    -   Day. Valid values: 1 to 6.
    -   Week. Valid values: 1 to 4.
 |
    |Backup Time|The first backup time. The first backup is a full backup.|
    |Retention|     -   Unit: day, month, and year.
    -   Maximum retention period: 3650 days \(10 years\).
 |


**Note:** 

If you need to delete or modify a backup policy, locate the required backup policy, click **Delete** or **Edit** next to the backup policy. After a backup policy is deleted, you cannot run the backup job to which the backup policy applies. The backups that correspond to the backup job are also deleted.

## More operations {#section_vcm_ht4_mgb .section}

[Back up data from SAP HANA](intl.en-US/Back up on-premises severs/Workflow-based backup/Back up SAP HANA.md)

[Back up data from SQL Server](intl.en-US/Back up on-premises severs/Workflow-based backup/Back up SQL Server.md)

[Back up data from MySQL](intl.en-US/Back up on-premises severs/Workflow-based backup/Back up MySQL.md)

[Back up data from MongoDB](intl.en-US/Back up on-premises severs/Workflow-based backup/Back up data from MongoDB.md)

