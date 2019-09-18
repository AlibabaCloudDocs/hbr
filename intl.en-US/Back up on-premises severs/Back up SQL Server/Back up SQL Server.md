# Back up SQL Server {#concept_189232 .concept}

You can use Hybrid Backup Recovery \(HBR\) to back up SQL Server databases deployed in a local data center and restore them as needed. This topic describes how to back up SQL Server databases.

## Prerequisites {#section_0ns_mwu_mgu .section}

[Preparations](intl.en-US/Back up on-premises severs/Back up SQL Server/Preparations.md#) are completed.

## Procedure {#section_a8h_5d2_5kj .section}

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, choose **On-Premises Backup** \> **SQL Server Backup**.
3.  Find the target SQL Server instance and click **Backup** in the Actions column for the instance.
4.  In the **Create Plan** dialog box that appears, select the databases to be backed up.
    -   If you have added the databases to be backed up to a database group, click **Database Group** and select the database group.
    -   If you have not [added the databases to be backed up to a database group](intl.en-US/Back up on-premises severs/Back up SQL Server/Preparations.md#section_5ey_jh7_czm), click **Select Database**. Select the databases to be backed up and enter a name in Group Name to create a database group.
    -   To back up all databases, click **All Database**.
5.  Click **Next** and configure the backup plan. The following table describes the parameters of the backup plan.

    |Parameter|Description|
    |:--------|:----------|
    |Backup Type|     -   Complete: backs up all data.
    -   Differential: backs up the data changed after the last full backup.

**Note:** 

        -   Complete a full backup before running the first incremental backup.
        -   If you need to run an incremental backup after a database is restored, complete a full backup first.
    -   Log: backs up logs of the databases.
        -   Complete a full backup before running the first log backup.
        -   If you need to run a log backup after a database is restored, complete a full backup first.
 |
    |Plan Name|The name of the backup plan.|
    |Start Time|The time when the backup starts. The time is accurate to the second.|
    |Plan Interval|The interval for backing up the databases. The interval units include hour, day, and week. **Note:** The retention period of incremental backup data is the same as that of full backup data and cannot be changed.

 |
    |Retention|The period for retaining backup data. The value can be one day to five years.|

6.  When the configuration is complete, click **Create**.

## View backup plans, backup jobs, and databases {#section_u1j_b2y_ggb .section}

-   View and manage backup plans

    You can view the status of backup plans and manage backup plans. The procedure is as follows:

    1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
    2.  In the left-side navigation pane, choose **On-Premises Backup** \> **SQL Server Backup**.
    3.  Click the **Backup Plan** tab.
    4.  View the status of backup plans in the backup plan list.
    5.  Manage a backup plan by clicking the required button in the Actions column for the backup plan. You can **edit**, **run**, **suspend**, **resume**, and **delete** a backup plan. After a backup plan is deleted, the plan will not be run again but the completed backup files are retained.
-   View and cancel backup jobs

    You can view the status of backup jobs and cancel ongoing backup jobs. The procedure is as follows:

    1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
    2.  In the left-side navigation pane, choose **On-Premises Backup** \> **SQL Server Backup**.
    3.  Click the **Backup Jobs** tab.
    4.  View the status of backup jobs in the backup job list.
    5.  To cancel an ongoing backup job, click **Cancel** in the Actions column for the backup job.
-   View the database and log backup history

    You can view the backup history of all databases and logs. The procedure is as follows:

    1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
    2.  In the left-side navigation pane, choose **On-Premises Backup** \> **SQL Server Backup**.
    3.  Click the **SQL Server Instance** tab.
    4.  Find the target SQL Server instance and click the instance ID or click **View Detail** in the Actions column for the instance.
    5.  On the SQL Server Instance page that appears, click the **Data Backups** or **Log Backups** tab to view the database or log backup history.

