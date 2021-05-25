# Prepare for SQL Server backup

You can use Hybrid Backup Recovery \(HBR\) to back up on-premises SQL Server databases. This topic describes how to prepare before you perform a backup.

## Background information

Before you use HBR to back up on-premises SQL Server databases, take note of the following information:

-   Make sure that .NET Framework 4.5 or later is installed.
-   HBR supports the following SQL Server versions: SQL Server 2008 R2, SQL Server 2012, SQL Server 2014, SQL Server 2016, and SQL Server 2017. For more information, see [Limits](/intl.en-US/Product Introduction/Limits.md).
-   You can also back up SQL Server databases that are hosted on Elastic Compute Service \(ECS\). For more information, see [Back up SQL Server databases that are hosted on ECS]().
-   SQL Server files cannot be stored on file systems for which the compression feature is enabled. For more information about the limits of SQL Server installation, see [File Locations for Default and Named Instances of SQL Server](https://docs.microsoft.com/en-us/sql/sql-server/install/file-locations-for-default-and-named-instances-of-sql-server?view=sql-server-2017).

## \(Recommended\) Prepare an AccessKey pair for a RAM user

Resource Access Management \(RAM\) is a service provided by Alibaba Cloud. It allows you to create and manage multiple identities under an Alibaba Cloud account and then grant diverse permissions to a single identity or a group of identities. In this way, you can authorize different identities to access different Alibaba Cloud resources.

An AccessKey pair is required when you activate a backup client. The AccessKey pair is an identity credential. If an AccessKey pair of your Alibaba Cloud account is used, all cloud resources that belong to the account are exposed to risks. Therefore, we recommend that you use an AccessKey pair of a RAM user to activate backup clients. Before you back up data, make sure that a RAM user is created and an AccessKey pair is created for the RAM user. For more information, see [Create a RAM user](/intl.en-US/RAM User Management/Basic operations/Create a RAM user.md) and [Create an AccessKey pair for a RAM user](/intl.en-US/Security Settings/AccessKey pairs/Create an AccessKey pair for a RAM user.md).

## Step 1: Register an SQL Server instance

Before you back up SQL Server databases, you must register an SQL Server instance. After the SQL Server instance is registered, you can download and install a backup client on each node of the SQL Server instance. The backup client is used to back up and restore data. To register an SQL Server instance, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the navigation bar at the top of the page, select the region where you want to store the backup data.

3.  In the left-side navigation pane, choose **Backup** \> **On-Premises Backup**. On the On-Premises Backup page, click **SQL Server**.

4.  In the upper-right corner of the SQL Server Instances tab, click **Register SQL Server Instance**.

5.  Go to the Register SQL Server Instance pane, perform the following steps to register an SQL Server instance:

    -   Configure the SQL Server instance.
        1.  In the Configure Instance step, set the following parameters.

            |Parameters|Description|
            |:---------|:----------|
            |Backup Vault|The name of the backup vault. A backup vault is an HBR repository that is used to restore backup data in the cloud. You can use a single vault to store backup data that is received from multiple backup clients. Backup vaults reside in different regions. You can select or create a backup vault only in the current region.             -   If you have created backup vaults, click **Select Vault**, and select a backup vault from the **Vault Name** drop-down list.
            -   If no backup vault is available, click **Create Vault** and specify the **Vault Name** field to create a backup vault. The name must be 1 to 64 bytes in length. |
            |Server Name|The server name and instance name of the SQL Server in the format of `<Server name>\<Instance name>`.            -   If the Server has one single SQL Server instance, set the Server Name parameter to a host name. In this case, the instance name is not required. For example, you can enter mylocalhost in the field.
            -   If the Server has multiple SQL Server instances, set the Server Name parameter to a host name. The instance name is required. For example, you can enter mylocalhost\\MSSQLSERVER in the field.
**Note:** The host name must be the same as the computer name that appears under the "Computer name, domain, and workgroup settings" section of the control panel. |
            |Authentication|The authentication method that is used to connect to the SQL Server instance.             -   If you select Windows Authentication, enter the name of a Windows user in the Windows Username field. The username is used to log on to the Windows system where the SQL Server instance resides.
            -   If you select SQL Server Authentication, specify the name of an SQL Server database user in the Database Account field. The username is used to log on to the SQL Server instance. |
            |Password|The password of the user.|

        2.  Click **Next**.
    -   Add a backup client.
        1.  In the Add Client step, set the following parameters.

            |Parameters|Description|
            |----------|-----------|
            |Backup Client|            -   **Create Client**: Select this option if you have not installed or activated backup clients on the server from which you want to back up data.
            -   **Select Client**: Select this option if you have installed and activated one or more backup clients on the server. Then, select a backup client that has been activated. |
            |Client Name|The name of the backup client. The name must be 1 to 64 bytes in length.|
            |Software Platform|The operating system that is running on the server from which you want to back up data. Valid values:             -   Window 32-bit
            -   Window 64-bit |
            |Network Type|            -   **VPC**: Select this option if the server from which you want to back up data resides in a VPC and the VPC is in the same region as the backup vault.
            -   **Classic Network**: Select this option if no VPCs are available. |
            |Use HTTPS|Specifies whether to use HTTPS to transmit encrypted data. If HTTPS is used, the performance of data transmission is compromised. If you modify the setting of this switch, the modification takes effect on the next backup or restoration job.|

        2.  Click **Create**. The **Download Client** button appears.
    -   Download and install the backup client.
        1.  Click **Download Client**.
        2.  Save the downloaded installation package of the backup client.
        3.  Log on to the server on which SQL Server is installed and install the client. Select an installation directory and install the client as prompted.

            **Note:** Make sure that enough space is available in the installation directory because both operational logs and an executable file are saved in this directory.

    -   Activate the backup client.
        1.  After the client is installed, you must activate the client. In the Register SQL Server Instance pane of the HBR console, click **Next**. In the Activate Client step, set the following parameters.

            |Parameter|Description|
            |:--------|:----------|
            |Client IP Address|The IP address of the server or virtual machine \(VM\) where the backup client is installed. **Note:** The IP address must be accessible to your browser in use. |
            |AccessKey Id|The AccessKey ID and AccessKey secret for the RAM user to access HBR. For more information, see [Create an AccessKey pair for a RAM user](/intl.en-US/FAQ/Common issues/Create an AccessKey for a RAM user.md).|
            |AccessKey Secret|
            |Client Password|The password of the backup client. The password must be at least six characters in length.|

        2.  Click **Activate Client**.
            -   After the backup client is installed and activated, you can view the installation status of the client on the node of the SQL Server instance. To delete the backup client from the node, find the client in the HBR console and click **Delete** in the Actions column.
            -   After the SQL Server instance is registered, you can view the information and status of the SQL Server instance on the SQL Server Instances tab of the **On-Premises Backup** page. To modify the connection settings of the SQL Server instance, find the SQL Server instance and choose **More** \> **Modify Instance** in the Actions column.

## Step 2: Add a client to a new node

If a node is added to the SQL Server cluster after the SQL Server instance is registered, you can add a backup client to the new node. To add a backup client, perform the following steps:

**Note:** You can add only one backup client to each SQL Server instance.

1.  On the SQL Server Instances tab, find the SQL Server instance. Click the instance ID, or choose More \> **View Details** in the Actions column.

2.  On the SQL Server Instances page, click the **Backup Client** tab. In the upper-right corner, click **Add Client**.

3.  In the Add Client pane, set the parameters and click **Create**. The **Download Client** button then appears. For more information about the required parameters, see the table in [Add a client](#table_pi5_94t_4mu).

4.  If you do not download the installation package of a backup client to the node, copy the installation package to the node and install the client.

5.  Log on to the HBR console and find the client. Choose More \> **Activate Client** in the Actions column. Set the parameters in the pane that appears. For more information about the parameters, see the table in [Activate the client](#table_pi5_94t_4mu).

6.  Click **Activate Client** to activate the client on the new node.


## Step 3: Create a database group

Before you back up data, you must group databases by backup plan. To create a database group, perform the following steps:

**Note:** If you want to separately back up a database, create an exclusive group for the database.

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **On-Premises Server Backup**. On the On-Premises Server Backup page, click **SQL Server**.

3.  Click the **Database Groups** tab. In the upper-right corner of the Database Groups tab, click **Create Group** .

4.  In the Create Group pane, set the Group Name and Description parameters. Then, select one or more databases and add these databases to the group.

5.  Click **OK**.


## \(Recommended\) Limit the memory usage of an SQL Server instance

By default, SQL Server instances consume as much system memory as possible. This may affect backup. Therefore, we recommend that you perform the following steps to limit the memory usage of an SQL Server instance:

1.  Start SQL Server Management Studio and connect to the SQL Server instance.

2.  Right-click the instance name and select **Properties**.

3.  In the dialog box that appears, click Memory in the left-side navigation pane. On the Memory tab, set **Maximum server memory**.

    **Note:** We recommend that you reserve at least 2 GB of memory for backup and other related services in the system. For example, if the system memory is 16 GB, you can set the Maximum server memory parameter to 14 GB.


