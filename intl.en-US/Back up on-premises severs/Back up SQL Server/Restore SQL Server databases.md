# Restore SQL Server databases

After you use Hybrid Backup Recovery \(HBR\) to back up SQL Server databases to a backup vault, you can restore the databases to the source SQL Server instance or another SQL Server instance that uses the same backup vault.

## Prerequisites

SQL Server databases are backed up. For more information, see [Back up SQL Server databases](/intl.en-US/Back up on-premises severs/Back up SQL Server/Back up SQL Server databases.md).

## Background

Before you restore SQL Server databases, note the following points:

-   Currently, the restore paths of SQL Server databases cannot be modified. Therefore, the paths of the destination SQL Server database on the destination SQL Server instance must be the same as the default paths of the source SQL Server database on the source SQL Server instance. If not, the restored SQL Server database cannot be loaded.

    **Note:** To view the default paths of an SQL Server database, you can open the **Server Properties** dialog box of the SQL Server instance, click **Database Settings**, and then view the paths of the SQL Server database in the **Database default locations** section.

-   If the source SQL Server database has more than one .ndf files, you can only restore this database to the destination database that has the same name. If not, the source database cannot be restored.
-   When you restore an SQL Server database from incremental backup, HBR automatically uses full backup to restore the database before using incremental backup.
-   To restore the databases of an SQL Server instance to another SQL Server instance, make sure that the version of the source SQL Server instance is not later than that of the destination SQL Server instance.
-   To restore the primary database of an SQL Server instance, start the SQL Server instance in single-user mode.

## Create a restore job

To create a restore job, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **On-Premises Backup**. On the On-Premises Backup page, click **SQL Server**.

3.  Click the **SQL Server Instances** tab.

4.  On the SQL Server Instances tab, find the SQL Server instance that you want to restore, and click **Restore** in the Actions column.

5.  In the Create Restore Job pane, select the source SQL Server instance and click **Next**.

6.  In the Source Database step, select the database that you want to restore, and click **Next**. In the Restore Policy step, set the parameters. The following table describes the parameters.

    |Parameter|Description|
    |:--------|:----------|
    |**Destination Database**|The name of the destination database in the destination SQL Server instance. **Note:**

    -   If you need to overwrite an existing database, enter the name of the database and select the **Overwrite Existing Database** check box.
    -   If you need to prevent existing databases from being overwritten, enter a name that is different from the existing database names. |
    |**Restore To**|    -   Latest Recovery Point

Restores the database to the latest recovery point.

    -   Specified Time Point

Restores the database to the recovery point that is closest to a specified time point. If you select this option, you must specify a time point.

    -   Specified Backup

Restores the database to a specified backup. If you select this option, you must specify a backup. |

7.  Click **Next**. In the Confirmation step, confirm the settings of the restore job and click **Create**.


## What to do next

To view the status of restore jobs or cancel running restore jobs, perform the following steps:

1.  In the left-side navigation pane, choose **Backup** \> **On-Premises Backup**. On the On-Premises Backup page, click **SQL Server**.

2.  Click the **Restore Jobs** tab.

3.  View the status of each restore job in the Status column.

4.  To cancel a running restore job, find the job and click **Cancel** in the Actions column.


