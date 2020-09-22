# Back up SQL Server databases

You can use Hybrid Backup Recovery \(HBR\) to back up on-premises SQL Server databases and restore the databases if needed. This topic describes how to back up SQL Server databases.

## Prerequisites

[Preparations](/intl.en-US/Back up on-premises severs/Back up SQL Server/Preparations.md) are completed.

## Create a backup plan

To create a backup plan for an SQL Server instance, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **On-Premises Backup**. On the On-Premises Backup page, click **SQL Server**.

3.  Click the SQL Server Instances tab. On the SQL Server Instances tab, find the SQL Server instance, and click **Back Up** in the Actions column.

4.  In the **Create Backup Plan** pane, select the databases that you want to back up.

    -   If you have added the databases to a database group, click **Database Group** and select the database group.
    -   If you have not added the databases to a database group, click **Selected Databases**. Select the databases and enter a database group name to create a database group. For more information, see [Create a database group](/intl.en-US/Back up on-premises severs/Back up SQL Server/Preparations.md).
    -   If you need to back up all databases, click **All Databases**.
5.  Click **Next**. In the Configure Plan step, set the following parameters.

    |Parameter|Description|
    |:--------|:----------|
    |Backup Type|    -   **Full**: backs up all data in the databases.
    -   **Differential**: backs up the data that is modified after the most recent full backup.

**Note:**

        -   Before you start the first differential backup for a database, a full backup must be completed.
        -   After you restore a database, you must perform another full backup for the database before you can perform a differential backup.
    -   **Log**: backs up the logs of the database.
        -   Before you start the first log backup for a database, a full backup must be completed.
        -   After you restore a database, you must perform another full backup for the database before you can perform a log backup. |
    |Plan Name|The name of the backup plan.|
    |Start Time|The start time of the backup plan. The time is accurate to seconds.|
    |Backup Interval|The interval at which data backup is performed, in hours. **Note:** The retention period of differential backup data is the same as that of full backup data, and is not configurable. |
    |Retention Period|The retention period of the backup data. Minimum retention period: 1 day. Maximum retention period: 5 years.|

6.  Click **OK**.


## What to do next

After a backup plan is created, you can manage the backup plan, cancel backup jobs, and view data backups and log backups.

-   Manage a backup plan

    In the HBR console, you can view the information and status of created backup plans and manage the backup plans. To manage a backup plan, perform the following steps:

    1.  In the left-side navigation pane, choose **Backup** \> **On-Premises Backup**. On the On-Premises Backup page, click **SQL Server**.
    2.  Click the **Backup Plans** tab.
    3.  On the Backup Plans tab, view the information and status of backup plans.
    4.  Click a button in the Actions column to manage the backup plan if needed. In the Actions column, you can click **Modify**, **Run Immediately**, **Suspend Plan**, **Resume Plan**, or **Delete Plan**. If you delete the backup plan, HBR no longer runs backup jobs for the plan but the backup data is retained.
-   View or cancel a backup job

    You can view the status of backup jobs and cancel running backup jobs. To view or cancel a backup job, perform the following steps:

    1.  In the left-side navigation pane, choose **Backup** \> **On-Premises Backup**. On the On-Premises Backup page, click **SQL Server**.
    2.  Click the **Backup Jobs** tab.
    3.  On the Backup Jobs tab, find the backup job and view its information and status.
    4.  To cancel a running backup job, find the job and click **Cancel** in the Actions column.
-   View data backups and log backups

    To view data backups and log backups of an SQL Server instance, perform the following steps:

    1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
    2.  In the left-side navigation pane, choose **Backup** \> **On-Premises Backup**. On the On-Premises Backup page, click SQL Server.
    3.  Click the **SQL Server Instances** tab.
    4.  On the SQL Server Instances tab, find the SQL Server instance. Click the instance ID in the Hostname/Instance Name column or choose More \> **View Details** in the Actions column. The SQL Server Instances page appears.
    5.  On the SQL Server Instances page, click the **Data Backups** tab to view data backups or the **Log Backups** tab to view log backups.

