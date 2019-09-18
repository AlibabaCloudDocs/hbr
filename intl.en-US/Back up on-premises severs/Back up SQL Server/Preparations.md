# Preparations {#concept_188638 .concept}

You can use Hybrid Backup Recovery \(HBR\) to back up SQL Server databases deployed in a local data center. This topic describes the preparations before the backup.

**Note:** 

If you need to back up SQL Server databases deployed on Elastic Compute Service \(ECS\) instances, see [Back up SQL Server](../../../../intl.en-US/Back up ECS/Back up SQL Server databases in ECS/Overview.md#).

Database files of SQL Server cannot be installed on a file system that enables compression. For more information about database installation restrictions, see [File Locations for Default and Named Instances of SQL Server](https://docs.microsoft.com/en-us/sql/sql-server/install/file-locations-for-default-and-named-instances-of-sql-server?view=sql-server-2017).

## Create a RAM user and obtain the AccessKey {#section_3vx_3li_lx3 .section}

Resource Access Management \(RAM\) is an Alibaba Cloud service that helps you manage user identities and access to your cloud resources. You can create and manage multiple RAM users with a single Alibaba Cloud account. You can grant different permissions for each RAM user. This allows each RAM user to have different permissions to Alibaba Cloud resources.

The AccessKey information is required to activate a file backup client. The disclosure of the AccessKey of the Alibaba Cloud account threatens the security of all your resources. We strongly recommend that you use the AccessKey of a RAM user to activate a file backup client. Before backing up SQL Server databases, make sure that you have [created a RAM user](../../../../intl.en-US/Best Practices/User permissions.md) and obtained the AccessKey of the RAM user.

## Register an SQL Server instance {#section_faj_l60_4a3 .section}

After an SQL Server instance is registered, HBR can download and install file backup clients on nodes of the SQL Server instance. You can use the file backup clients to run backup and restore jobs. The procedure for registering an SQL Server instance is as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  At the top of the page, select the region where you want to store the backup data.
3.  In the left-side navigation pane, choose **On-Premises Backup** \> **SQL Server Backup**.
4.  In the upper-right corner of the SQL Server Backup page, click **Register SQL Server Instance**.
5.  In the Register SQL Server Instance dialog box that appears, set the parameters as required.
    1.  Configure an instance
        1.  Set the parameters for configuring an instance, as described in the following table.

            |Parameter|Description|
            |:--------|:----------|
            |Backup Vault Name|The name of the backup vault. A backup vault is a cloud warehouse used by HBR to store backup data on the cloud. Backup data from multiple clients can be stored in the same vault.             -   If one or more backup vaults are available:

Select a backup vault from the drop-down list.

            -   If no backup vault is available:

Click **Create Vault**. Set **Backup Vault Name** and **Vault Description** to create a backup vault. The vault name can be a maximum of 64 characters in length.

 |
            |Server Name|The server name of the SQL Server instance.|
            |Authentication|The authentication method of the SQL Server instance.|
            |Windows Login|If you select Windows Login as the authentication method, you must set Windows Login Name for connecting to SQL Server.|
            |SQL Server Login|If you select SQL Server Login as the authentication method, you must set SQL Server Login Name for connecting to SQL Server.|
            |Password|The password for connecting to SQL Server based on the authentication method you select.|

        2.  Click **Next**.
    2.  Create a client
        1.  Set the parameters for creating a client, as described in the following table.

            |Parameter|Description|
            |---------|-----------|
            |**Source Client**|             -   **New Client**: Select this option if no file backup client is installed and activated on the server from which you want to back up data.
            -   **Select Activated Client**: Select this option if a file backup client has been installed and activated on the server from which you want to back up data. Then, select the file backup client that has been activated.
 |
            |**Client Name**|The name of the client. The client name can be a maximum of 64 characters in length.|
            |**Software Platform**|The operating system that is running on the server from which you want to back up data.             -   Windows 32-bit
            -   Windows 64-bit
 |
            |**Network Type**|             -   **Virtual Private Cloud \(VPC\)**: Select this option if the server from which you want to back up data is located in a VPC and in the same region as the backup vault.
            -   **Public Network**: Select this option the server is not located in a VPC.
 |

        2.  Click **Create**. The **Download Client** button appears.
    3.  Download and install the client
        1.  Click **Download Client**.
        2.  Save the downloaded client.
        3.  Log on to the server where SQL Server is installed and install the client.

            **Note:** All the logs and executable files of the client are stored in the selected installation directory. Therefore, you must ensure that the disk where the installation directory is located has sufficient space.

    4.  Activate the client
        1.  After the client is installed, you need to activate the client. Return to the Register SQL Server Instance dialog box in the HBR console, click **Next**, and set the parameters for activating the client, as described in the following table.

            |Parameter|Description|
            |:--------|:----------|
            |**Client IP Address**|The IP address of the server or virtual machine where the client is installed. **Note:** The IP address must be reachable from your current browser.

 |
            |**AccessKey ID**|The AccessKey ID of the Alibaba Cloud account that has activated the HBR service. For more information, see [AccessKey](../../../../intl.en-US/FAQ/Common issues/Create an AccessKey for a RAM user.md).|
            |**AccessKey Secret**|The AccessKey secret of the Alibaba Cloud account that has activated the HBR service. For more information, see [AccessKey](../../../../intl.en-US/FAQ/Common issues/Create an AccessKey for a RAM user.md).|
            |**Create Client Password**|The logon password of the client. The password must be a minimum of six characters in length.|

        2.  Click **Activate Client**.

**Note:** 

-   After the file backup client is installed and activated, you can view the installation status of the client on the node of the SQL Server instance. To delete the file backup client from the node, click **Delete** in the Actions column for the client.
-   After the SQL Server instance is registered, you can click the **SQL Server Instance** tab on the SQL Server Backup page to view the registration information and status of the instance. You can click **Edit Instance** in the Actions column for the instance to modify the connection information of the instance.

## Install clients on new nodes {#section_tvy_8x6_m4v .section}

If new nodes are added to the SQL Server instance after it is registered, you can install clients on the new nodes. The procedure is as follows:

1.  Find the target SQL Server instance and click the instance ID or click **View Detail** in the Actions column for the instance. The SQL Server Instance page appears.
2.  Click the **Client** tab and then click **Create Client** in the upper-right corner.
3.  Set the parameters as required and click **Create**. The **Download Client** button appears. For more information about the parameters, see [this table](#li_yr7_wuq_28x).
4.  If the client is not downloaded to the target node, copy the downloaded client to the target node and install the client.
5.  Log on to the HBR console and find the client. Click **Activate Client** and set the parameters as required. For more information about the parameters, see [this table](#table_iun_vpz_iuy).
6.  Click **Activate Client** to activate the client on the new node.

## Create a database group to be backed up {#section_5ey_jh7_czm .section}

Before starting the backup, you need to add the databases that use the same backup plan to the same database group. The procedure is as follows:

**Note:** If you want to back up only a single database, you can create a separate group for the database.

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, choose **On-Premises Backup** \> **SQL Server Backup**.
3.  Click the **Database Group** tab. Click **Edit Database Group** in the upper-right corner.
4.  In the Edit Database Group dialog box that appears, set Group Name and Description and select one or more databases to add them to the group.
5.  Click **OK** to create the group.

