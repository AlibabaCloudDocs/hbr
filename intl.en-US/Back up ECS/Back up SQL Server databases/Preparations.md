# Preparations {#concept_ckh_mrh_dhb .concept}

You can use Hybrid Backup Recovery \(HBR\) to back up SQL Server databases deployed on Alibaba Cloud Elastic Compute Service \(ECS\) instances and restore these databases as required. This topic describes the preparations that you need to make before backing up data.

**Note:** 

HBR supports the following SQL Server versions: SQL Server 2008 R2, SQL Server 2012, SQL Server 2014, SQL Server 2016, and SQL Server 2017. For more information, see [Limits](../../../../intl.en-US/Product Introduction/Limits.md#table_dpw_vgq_dhb).

SQL Server databases cannot be installed in a file system where compression is enabled. For more information about SQL Server installation limits, see [File Locations for Default and Named Instances of SQL Server](https://docs.microsoft.com/en-us/sql/sql-server/install/file-locations-for-default-and-named-instances-of-sql-server?view=sql-server-2017).

## Authorize roles {#section_pts_5z5_fgb .section}

Before using HBR to back up files from ECS instances, you must authorize two roles AliyunHBRDefaultRole and AliyunECSAccessingHBRRole to access your cloud resources. The procedure is as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, choose **ECS Backup** \> **ECS File Backup**. Authorization dialog boxes appear one by one. Follow instructions to authorize the two roles to access your cloud resources.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83216/156819086360226_en-US.png)


## Install Cloud Assistant {#section_qb5_wz5_fgb .section}

-   An ECS backup client must work with Cloud Assistant. By default, a Cloud Assistant client is installed on ECS instances that are created after December 1, 2017. To back up files from ECS instances that you bought before December 1, 2017, you must [install a Cloud Assistant client](../../../../intl.en-US/Deployment & Maintenance/Cloud assistant/Configure the cloud assistant client.md).
-   When a Cloud Assistant client is installed on an ECS instance that is located on a classic network, you need to perform the following operations to configure the Cloud Assistant client based on the operating system of the ECS instance.
    -   Windows:
        1.  Connect to the ECS instance. In the C:\\ProgramData\\aliyun\\assist\\ directory, create a file named `region-id` and enter the `region ID` in the file based on the region where the ECS instance is located. For example, for an ECS instance that is located in China \(Hangzhou\), you need to enter `cn-hangzhou`.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82684/156819086339296_en-US.png)

            The following table lists regions and their region IDs.

            |Region|Region ID|
            |:-----|:--------|
            |China \(Hangzhou\)|cn-hangzhou|
            |China \(Shanghai\)|cn-shanghai|
            |China \(Beijing\)|cn-beijing|
            |China \(Shenzhen\)|cn-shenzhen|

        2.  Restart AliyunService in Task Manager.
    -   Linux:
        1.  Connect to the ECS instance. In the /usr/local/share/aliyun-assist/ directory, create a file named `region-id` and enter the `region ID` in the file based on the region where the ECS instance is located. For example, for an ECS instance that is located in China \(Hangzhou\), you need to enter `cn-hangzhou`.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/82684/156819086339297_en-US.png) 

            The following table lists regions and their region IDs.

            |Region|Region ID|
            |:-----|:--------|
            |China \(Hangzhou\)|cn-hangzhou|
            |China \(Shanghai\)|cn-shanghai|
            |China \(Beijing\)|cn-beijing|
            |China \(Shenzhen\)|cn-shenzhen|

        2.  To restart the Cloud Assistant client, run the `chkconfig agentwatch off` command and then the `chkconfig agentwatch on` command. Alternatively, you can run the `systemctl restart agentwatch` command.

            **Note:** If the Cloud Assistant client still does not work after the restart, you need to run the preceding commands to restart it again.


## Register a SQL Server instance {#section_fsy_5lj_dhb .section}

When you register a SQL Server instance, you need to configure the connection information about the SQL Server instance. After the SQL Server instance is registered, an ECS backup client is installed on each node of the SQL Server instance. The procedure is as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the upper-left corner of the page, select a region where ECS instances that you need to back up are located.
3.  In the left-side navigation pane, choose **ECS Backup** \> **SQL Server Backup**.
4.  In the upper-right corner, click **Register SQL Server Instance**.
5.  In the Register SQL Server Instance dialog box, set the parameters as instructed in the following table.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/141162/156819086360289_en-US.jpg)

    |Parameter|Description|
    |:--------|:----------|
    |Backup Vault Name|Specify the backup vault. A backup vault is a repository used by HBR to store backup data on the cloud. You can back up data from multiple clients to the same vault.     -   If you have created backup vaults:

Click Select Existing Vault and select a vault from the drop-down list.

    -   If you have not created any backup vaults:

Click **Create New Vault**, and then set **Backup Vault Name** and **Vault Description** to create a vault. The vault name cannot exceed 64 bytes in length.

 |
    |Server Name|Specify the name of the server where the SQL Server instance is located.|
    |Authentication|Select an authentication method for connecting to the SQL Server instance.|
    |Windows Login Name|If you select Windows Login, enter the username used to log on to the SQL Server instance in Windows in the Windows Login Name field.|
    |SQL Server User|If you select SQL Server Login, enter the username used to log on to the SQL Server instance in the SQL Server User field.|
    |Password|Enter the password used to log on to the SQL Server instance based on the selected authentication method.|

6.  Click **Next**.
7.  Select all ECS instances where the SQL Server instance is deployed so that HBR can install an ECS backup client on these ECS instances. In the drop-down list on the left of the search box, select Instance ID or Instance Name as the keyword. Enter a complete or partial ID or name in the search box to search for ECS instances.

    **Note:** If you select an ECS instance that is located on a classic network, you must enter the [AccessKey ID and AccessKey secret](../../../../intl.en-US/FAQ/Common issues/Create an AccessKey for a RAM user.md).

8.  Click **Create**. HBR automatically installs an ECS backup client on the selected ECS instances.

    **Note:** After the SQL Server instance is registered, you can click the **SQL Server Instance** tab on the SQL Server Backup page. On this tab, you can view the registration information and status of the registered SQL Server instance. In the right-side Actions column, you can choose More \> **Edit Instance** to modify the SQL Server instance.


## View and manage clients {#section_ny2_lfr_ggb .section}

After the SQL Server instance is registered, you can view the installation status of the ECS backup client on each node of the SQL Server instance. You can also install an ECS backup client on newly added nodes.

 **Install a client on a new node** 

If an ECS instance is added to the SQL Server cluster, you can install an ECS backup client on this ECS instance. The procedure is as follows:

1.  Find the target SQL Server instance. Click the instance name or ID, or click **View Detail** for the instance in the right-side Actions column. The SQL Server Instance page appears.
2.  Click the **Client** tab. In the upper-right corner of the Client tab, click **Create Client**.
3.  Select the new ECS instance so that HBR can install an ECS backup client on this ECS instance. In the drop-down list on the left of the search box, select Instance ID or Instance Name as the keyword. Enter a complete or partial ID or name in the search box to search for this ECS instance.

    **Note:** If you select an ECS instance that is located on a classic network, you must enter the [AccessKey ID and AccessKey secret](../../../../intl.en-US/FAQ/Common issues/Create an AccessKey for a RAM user.md).

4.  Click **OK**.

 **Check the client installation status** 

To check the installation status of the ECS backup client on a node, perform the following operations:

1.  Ensure that the SQL Server instance is registered. On the SQL Server Backup page, click the **SQL Server Instance** tab.
2.  Find the target SQL Server instance. Click the instance name or ID, or click **View Detail** for the instance in the right-side Actions column. The SQL Server Instance page appears.
3.  Click the **Client** tab to view the installation status of the ECS backup client on nodes. If the ECS backup client is installed, the node status is Activated. The following table describes the operations that you can perform in this case.

    |Operation|Procedure|
    |:--------|:--------|
    |Reinstall a backup client|If the backup client fails to be installed on a node, choose More \> **Re-install** in the right-side Actions column for the node.|
    |Uninstall a backup client|To uninstall the backup client from a node, choose More \> **Uninstall Client** in the right-side Actions column for the node.|
    |Delete a backup client|To uninstall the backup client from a node and delete the node, click **Delete** in the right-side Actions column for the node. **Note:** Before deleting a backup client, you need to ensure that the backup client has no backup job in the Running or Completed state.

 |


 **View databases** 

You can view the databases of a SQL Server instance. The procedure is as follows:

1.  Find the target SQL Server instance. Click the instance name or ID, or click **View Detail** for the instance in the right-side Actions column. The SQL Server Instance page appears.
2.  Click the **Database** tab. On this tab, you can view the database information of the target SQL Server instance.

## Create a backup database group {#section_uys_rsj_dhb .section}

Before starting backup, you need to group databases by backup plan. The procedure is as follows:

**Note:** If you want to back up a database separately, create a group exclusively for this database.

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, choose **ECS Backup** \> **SQL Server Backup**.
3.  Click the **Database Group** tab. In the upper-right corner of the tab, click **Edit Database Group**.
4.  In the Edit Database Group dialog box, set Group Name and Description. Then, select one or more databases, and add them to the group.
5.  Click **OK**.

