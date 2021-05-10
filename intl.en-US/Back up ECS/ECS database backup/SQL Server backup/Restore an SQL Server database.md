# Restore an SQL Server database

After you use Hybrid Backup Recovery \(HBR\) to back up an SQL Server database to a backup vault, you can restore the SQL Server database as needed. You can restore the database to the original SQL Server instance, another SQL Server instance that uses the same backup vault, or an SQL Server instance in another region.

## Prerequisites

The SQL Server database is backed up. For more information, see [t2037309.md\#]().

## Background information

Before you restore an SQL Server database, take note of the following information:

-   If you restore an SQL Server database that is backed up on an incremental basis, HBR automatically restores all the data that is backed up.
-   To restore a database of an SQL Server instance to another SQL Server instance, you must check the version of the source SQL Server instance. This version cannot be later than that of the destination SQL Server instance.
-   Before you restore a master database, HBR restarts the SQL Server instance in single-user mode.

## Create a restoration job

To create a restoration job, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS Database Backup**. On the ECS Database Backup page, click **SQL Server**.

3.  Select the region where the SQL Server instance to be backed up resides.

4.  On the Database Instance tab, find the MySQL instance to be backed up. Click Restore in the **Actions** column.

5.  In the Create Restore Job dialog box, configure the following settings as prompted. Click **Next**.

    1.  Configure the basic information of the restoration.

        |Parameter|Description|
        |---------|-----------|
        |Restoration Source|Set this parameter to Database.|
        |Restorable Databases|Select the database that you want to restore from the drop-down list.|
        |Restoration Method|Specify method to restore the database.         -   If you want to restore data that is backed up after a specific point in time, set this parameter to **Specified Start Time**.
        -   If you want to restore database logs that have specified serial numbers, set this parameter to **Specified LSN**.
        -   If you want to restore specified database files, set this parameter to **Specified Files**. In the **Backup** list, select the backup files or logs that you want to restore. |

    2.  Configure the restoration job.

        -   Job Name: the name of the restoration job.
        -   Restoration Time: By default, this parameter is set to Right Now, which indicates that the restoration job is immediately run.
    3.  Configure the restoration settings.

        -   Reconnection Time: the interval between the time when the database is disconnected and the time when the database is reconnected.
        -   Restoration Rate Limit: the amount of data that is restored per second.
    4.  Configure the destination database instance.

        Select a destination database instance. Default value: Source Instance.

6.  Click **Create**.

7.  After you create a restoration job, the job automatically starts. On the **Restore Jobs** tab, you can view the status of the restoration job that you have created.


