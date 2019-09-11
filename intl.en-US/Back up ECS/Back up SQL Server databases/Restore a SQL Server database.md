# Restore a SQL Server database {#concept_bwn_4rh_dhb .concept}

After using Hybrid Backup Recovery \(HBR\) to back up SQL Server databases to a backup vault, you can restore the SQL Server databases to the original SQL Server instance or another SQL Server instance that uses the same backup vault.

**Note:** 

-   When you choose to restore a SQL Server database from incremental backup, HBR automatically uses full backup to restore the database before using incremental backup.
-   To restore the primary database of a SQL Server instance, you need to start the SQL Server instance in single-user mode.
-   To restore the databases of a SQL Server instance to another SQL Server instance, ensure that the source SQL Server instance version is not later than the destination SQL Server instance version.

## Procedure {#section_ysg_4dk_dhb .section}

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, choose **ECS Backup** \> **SQL Server Backup**.
3.  Click the **SQL Server Instance** tab.
4.  Find the SQL Server instance to be restored, and click **Restore** in the right-side Actions column.
5.  In the New Restore Task dialog box, select the source SQL Server instance and click **Next**.
6.  Select a database to be restored, and click **Next**. Then, set restoration rules as instructed in the following table.

    |Parameter|Description|
    |:--------|:----------|
    |**Destination Database**|Specify the name of the database restored on the destination SQL Server instance. **Note:** 

    -   If you want to use the restored database to overwrite an existing database, enter the name of the existing database in this field, and then select Override existing database.
    -   Otherwise, do not enter a name that is the same as that of any existing databases.
 |
    |**Restore Policy**|     -   Most Recent 

Restores the database to the latest available status.

    -   Time Point 

Restores the database to the status closest to a specified time point. After selecting this option, you need to specify a time point.

    -   From Snapshot 

Restores the database to a specified backup. After selecting this option, you need to specify a backup.

 |

7.  Click **Next**, confirm the configuration, and then click **Create**.

## View and cancel restoration jobs {#section_clt_1by_ggb .section}

In the HBR console, you can view the status of restoration jobs and cancel ongoing restoration jobs. The procedure is as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, choose **ECS Backup** \> **SQL Server Backup**.
3.  Click the **Restore Jobs** tab.
4.  View the restoration job status on the Restore Jobs tab.
5.  To cancel an ongoing restoration job, click **Cancel** in the right-side Actions column for the job.

