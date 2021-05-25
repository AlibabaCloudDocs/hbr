# Back up an SQL Server database

You can use Hybrid Backup Recovery \(HBR\) to back up SQL Server databases deployed on Elastic Compute Service \(ECS\) instances and restore these databases as needed. This topic describes how to back up an SQL Server database.

## Precautions

Before you back up an SQL Server database, take note of the following information:

-   You must install .NET Framework 4.5 or later in advance.
-   You can back up only an SQL Server database whose version is supported by HBR. For more information, see [Overview](/intl.en-US/Back up ECS/ECS database backup/Overview.md).
-   If compression is enabled for a file system, the files of the SQL Server database cannot be installed on the file system. For more information about the limits on SQL Server installation, see [File Locations for Default and Named Instances of SQL Server](https://docs.microsoft.com/en-us/sql/sql-server/install/file-locations-for-default-and-named-instances-of-sql-server?view=sql-server-2017).
-   If the SQL Server database uses the simple recovery model, **Log Backup** is not supported. You can select only **Full Backup** or **Cumulative Incremental Backup**.
-   If you are using a master database, **Cumulative Incremental Backup** and **Log Backup** are not supported. You can select only **Full Backup**.

## Create a backup plan

After you register an SQL Server instance, you can create a backup plan to back up the instance. To create a backup plan, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS Database Backup**.

3.  On the ECS Database Backup page, click the **SQL Server** tab.

4.  Select the region where the SQL Server instance to be backed up resides.

5.  On the Instances tab, find the SQL Server instance to be backed up. Click Back Up in the **Actions** column.

6.  In the **Create Backup Plan** panel, perform the following steps:

    1.  Set the parameters for the backup.

        1.  Specify **Plan Name**.
        2.  Select the SQL Server instance that you want to back up.
        3.  Click **Next**.
    2.  Configure the backup plan.

        1.  Select a backup policy.

            |Parameter|Description|
            |---------|-----------|
            |Full Backup|If you select Full Backup, all the database files in the operating system are backed up. However, you can restore only the files that are backed up after a specific point in time.

You can back up database files immediately or at the specified time. You can also schedule periodic backup by hour, day, week, or month. A custom backup plan is supported. |
            |Cumulative Incremental Backup|If you select Cumulative Incremental Backup, incremental database files in the operating system are backed up. However, you can restore only the files that are backed up after a specific point in time.

You can back up files immediately or at the specified time. You can also schedule periodic backup by hour, day, week, or month. A custom backup plan is supported. |
            |Log Backup|If you select Log Backup, database logs are backed up. You can restore the logs that are backed up after a specific point in time. You can back up database logs immediately or at the specified time. You can also schedule periodic backup by hour, day, week, or month. A custom backup plan is supported. |

        2.  Click **Next**.
    3.  Configure the backup settings. Click **Next**.

        You can specify the number of concurrent nodes, the retry time, and the limit of the backup speed.

    4.  Select a backup vault.

        -   If you have created backup vaults, click **Select Vault** and select a backup vault from the **Vault Name** drop-down list.
        -   If you want to create a backup vault, click **Create Vault** and specify the Vault Name parameter.
7.  Click **OK**.


## What to do next

After a backup plan is created, you can view and manage the backup plan, cancel backup jobs, and view the records of database backups and log backups.

-   Manage a backup plan

    In the HBR console, you can view the information and status of the backup plan. You can also manage the backup plan. To view and manage a backup plan, perform the following steps:

    1.  In the left-side navigation pane, choose **Backup** \> **ECS Database Backup**.
    2.  Click the **SQL Server** tab.
    3.  On the SQL Server tab, click the **Backup Plan** tab. On the Backup Plans tab, view the information and status of the backup plan.
    4.  Click a button in the Actions column as needed to manage the backup plan. You can click **Modify**, **Run Now**, **Cancel Job**, or **Delete**. If you delete the backup plan, HBR no longer runs backup jobs for the plan, but the backup data is retained.
-   Configure alerts

    You can configure alerts for the backup plan. To configure alerts for the backup plan, perform the following steps:

    1.  In the left-side navigation pane, choose **Backup** \> **ECS Database Backup**.
    2.  Click the **SQL Server** tab.
    3.  On the SQL Server tab, click the **Backup Plan** tab. On the Backup Plans tab, view the information and status of the backup plan.
    4.  In the Actions column, choose **More** \> **Alert Settings**.
    5.  Configure an alert policy and click **OK**.

        The following alert policies are supported:

        -   Disabled: If you set Alert Policy to Disabled, the alerting feature is disabled.
        -   Same as Vault: If you set Alert Policy to Same as Vault, the alert policy of the backup plan is the same as that of the backup vault.
        -   Default: If you set Alert Policy to Default, the alert notification method of the backup plan is the same as that of the backup vault.
        -   Custom: If you set Alert Policy to Custom, customize an alert contact based on your needs.
        For more information, see [Create a notification contact](/intl.en-US/Back up on-premises severs/File backup/Configure alert notifications.md).

-   View the records of database backups and log backups

    You can view all backup records in the HBR console. To view the backup records of an SQL Server instance, perform the following steps:

    1.  In the left-side navigation pane, choose **Backup** \> **ECS Database Backup**.
    2.  Click the **SQL Server** tab.
    3.  On the SQL Server tab, click the **Execution History** tab. On the Execution History tab, view the records of database backups and log backups.

