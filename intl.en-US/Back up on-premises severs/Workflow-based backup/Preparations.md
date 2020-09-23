# Preparations

Hybrid Backup Recovery \(HBR\) allows you to back up databases based on workflows. You can use HBR to back up SAP HANA, SQL Server, MySQL, MongoDB, and other databases. This topic describes the preparations that you must make before backup.

## \(Recommended\) Prepare an AccessKey pair for a RAM user

Resource Access Management \(RAM\) is a service provided by Alibaba Cloud. It allows you to create and manage multiple identities under an Alibaba Cloud account and then grant diverse permissions to a single identity or a group of identities. In this way, you can authorize different identities to access different Alibaba Cloud resources.

An AccessKey pair is required when you activate a backup client. The AccessKey pair is an identity credential. If an AccessKey pair of your Alibaba Cloud account is used, all cloud resources that belong to the account are exposed to risks. Therefore, we recommend that you use an AccessKey pair of a RAM user to activate backup clients. Before you back up data, make sure that a RAM user is created and an AccessKey pair is created for the RAM user. For more information, see [Create a RAM user](/intl.en-US/RAM User Management/Create a RAM user.md) and [Create an AccessKey pair for a RAM user](/intl.en-US/Security Settings/AccessKey pairs/Create an AccessKey pair for a RAM user.md).

## Step 1: Create a backup client

Before you back up and restore files for an on-premises server or VM, you must install a backup client on the on-premises server or VM. To create a backup client in the HBR console and download the installation package of the client, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

    If your server or VM runs a Linux operating system that does not provide a graphical user interface \(GUI\), use an intermediate host that provides a GUI as an agent to log on to the HBR console.

2.  In the left-side navigation pane, choose **Backup** \> **On-Premises Server Backup** \> **File**.

3.  In the top navigation bar, select the region where you want to store backup data.

    **Note:**

    -   If you use a virtual private cloud \(VPC\), select the region of the VPC. This guarantees a high backup speed.
    -   If you do not use a VPC and you need to achieve optimal backup performance, select a region that is close to the location of the data that you want to back up.
    -   If you do not use a VPC and you need to implement disaster recovery, select a region that is distant from the location of the data that you want to back up.
4.  In the upper-right corner of the On-Premises Backup page, click **Add Client**.

5.  In the Add Client pane, set the parameters.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8021549951/p54112.jpg)

    The following table describes the parameters.

    |Parameter|Description|
    |:--------|:----------|
    |Backup Vault|The backup vault where you want to store the backup data. A backup vault is a repository that HBR uses to store backup data. You can use a single vault to store backup data that is received from multiple backup clients. Backup vaults reside in different regions. You can select or create only a backup vault in the current region.     -   If you have created backup vaults, click **Select Vault**, and select a backup vault from the **Vault Name** drop-down list.
    -   If you have not created backup vaults, click **Create Vault** and specify the **Vault Name** field. The name must be 1 to 64 characters in length. |
    |Backup Client|The backup client that you want to add. You can select an activated client or create a client.|
    |Client Name|The name of the backup client. The name must be 1 to 64 characters in length.|
    |Software Platform|The operating system that is running on the server or VM from which you want to back up data. Valid values:     -   Windows 32-bit
    -   Windows 64-bit
    -   Linux 32-bit
    -   Linux 64-bit |
    |Network Type|    -   **Virtual Private Cloud \(VPC\)**: Select this option if the server or VM from which you want to back up data resides in a VPC and the VPC is in the same region as the backup vault.
    -   **Internet**: Select this option if no VPCs are available. |
    |Use HTTPS|Specifies whether to use HTTPS for encrypted data transmission. Note that HTTPS compromises the performance of data transmission. Data that is stored in the backup vault is encrypted, regardless of the setting of this switch. If you modify the setting of this parameter, the modification takes effect on the next restore job.|

6.  Click **Create**. Then, click **Download Client**.

    **Note:** The backup client is used to connect your server or VM to HBR. You can also download the client from the client list.


## Step 2: Install and activate the backup client

After you download the installation package of a backup client for files to a server or VM, perform the following steps to install and activate the client:

1.  Select an installation directory, decompress the installation package, and then install the backup client.

    **Note:** Make sure that enough space is available in the installation directory because both operational logs and an executable file are saved in the installation directory.

    -   If your server or VM runs Windows, run the executable file that is decompressed from the installation package, select an installation directory, and then follow the instructions to install the backup client.
    -   If your server or VM runs Linux, decompress the installation package to a specified directory and run the `./setup` command to install the backup client.

        ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9021549951/p35152.png)

2.  Activate the backup client. Go to the HBR console. In the Add Client pane, click **Next**. In the Activate Client step, set the following parameters.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9021549951/p60931.jpg)

    **Note:** Make sure that the backup client is installed before you activate the client.

    |Parameter|Required|Description|
    |:--------|--------|:----------|
    |Client IP Address|Yes|The IP address of the backup client that your current host can access. You can specify an internal IP address or an Internet IP address. For example, the IP address can be 127.0.0.1 \(default\), 12.34.56.78:8011, or 87.65.43.21:8443. **Note:** The IP address must be reachable from your browser in use. |
    |AccessKey Id|Yes|The AccessKey ID and AccessKey secret of the RAM user that is used to access HBR. For more information, see [Create an AccessKey for a RAM user](/intl.en-US/FAQ/Common issues/Create an AccessKey for a RAM user.md).|
    |AccessKey Secret|Yes|
    |Client Password|Yes|The password that is used to log on to the backup client. The password must be at least six characters in length.|
    |Data Network Proxy|No|The information of the proxy server that is used to transmit backup data. Specify this parameter if a proxy server is used. **Note:** You can configure a data network proxy only for a backup client whose version is 1.11.11 or later. |
    |Control Network Type|No|The type of the network that is used to call the HBR API.|
    |Control Network Proxy|No|The information of the proxy server that is used to call the HBR API.|
    |Message Network Type|No|The type of the network that is used to send messages from HBR to the backup client.|

3.  Click **Activate Client**. The page of the backup client for files appears. You can then use the backup client to back up data.

    If the activation of a backup client fails, you can use the following methods to reactivate the client:

    -   Reactivate a client in the console

        Go to the HBR console. On the On-Premises Backup page, select File. Find the backup client for files and choose More \> **Activate Client** in the Actions column to reactivate the client.

    -   Reactivate a client in a browser

        1.  Go to the HBR console. On the On-Premises Backup page, select File. Find the backup client for files and choose More \> **Download Certificate** in the Actions column.
        2.  Open a browser and enter `http://localhost:8011` in the address bar.
        3.  On the **Register** page, set the following parameters and click **Register**.

            |Parameter|Required|Description|
            |:--------|--------|:----------|
            |Certificate File|Yes|The certificate that you downloaded.|
            |Access Key ID|Yes|The AccessKey ID and AccessKey secret of the RAM user that is used to access HBR. For more information, see [Create an AccessKey for a RAM user](/intl.en-US/FAQ/Common issues/Create an AccessKey for a RAM user.md).|
            |Access Key Secret|Yes|
            |Backup Data Network|No|The type of the proxy server that is used to transmit backup data. You can select **Public Network** or **Alibaba Intranet**.|
            |Control Network Proxy|No|The information of the proxy server that is used to call the HBR API. The information consists of the username, password, IP address, and listening port number of the proxy server. If identity authentication is not required, you can leave the username and password unspecified. |
            |Data Network Proxy|No|The information of the proxy server that is used to transmit backup data. Specify this parameter if a proxy server is used. The information consists of the username, password, IP address, and listening port number of the proxy server. If identity authentication is not required, you can leave the username and password unspecified. |
            |Control Network Type|No|The type of the network that is used to call the HBR API.|
            |Message Channel Network Type|Yes|The type of the network that is used to send messages from HBR to the backup client.|

        If you are using an intermediate host, replace `localhost` with the IP address of the server or VM from which you want to back up data.

        Port 8011 is the default port that you can use to log on to a backup client for files. If port 8011 on the server or virtual machine is occupied by another application, specify another port number for the backup client. For more information, see [How can I change the number of the logon port for a file backup client?](/intl.en-US/FAQ/On-premises backup FAQ/How can I change the number of the logon port for a file client?.md)


## What to do next

[Back up SAP HANA databases](/intl.en-US/Back up on-premises severs/Workflow-based backup/Back up SAP HANA databases.md)

[Back up SQL Server databases](/intl.en-US/Back up on-premises severs/Workflow-based backup/Back up SQL Server databases.md)

[Back up MySQL databases](/intl.en-US/Back up on-premises severs/Workflow-based backup/Back up MySQL databases.md)

[Back up MongoDB databases](/intl.en-US/Back up on-premises severs/Workflow-based backup/Back up MongoDB databases.md)

