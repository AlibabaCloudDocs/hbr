# Restore an Oracle database

After you use Hybrid Backup Recovery \(HBR\) to back up an Oracle database to a backup vault, you can restore the Oracle database as needed. You can restore the database to the original Oracle instance, another Oracle instance that uses the same backup vault, or an Oracle instance in another region.

## Prerequisites

The Oracle database is backed up. For more information, see [Back up an Oracle database](/intl.en-US/Back up ECS/ECS database backup/Oracle backup/Back up an Oracle database.md).

## Create a restoration job

To create a restoration job, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS Database Backup**. On the ECS Database Backup page, click **Oracle**.

3.  Select the region where the Oracle instance to be backed up resides.

4.  On the Database Instance tab, find the Oracle instance to be backed up. Click Restore in the **Actions** column.

5.  In the Create Restore Job dialog box, configure the following settings as prompted. Click **Next**.

    1.  Set the parameters for the restoration job.

        |Parameter|Description|
        |---------|-----------|
        |Restoration Source|Set this parameter to Database.|
        |Restorable Databases|Select the database that you want to restore from the drop-down list.|
        |Restoration Method|Specify method to restore the database.         -   If you want to restore data that is backed up after a specific point in time, set this parameter to **Specified Start Time**.
        -   If you want to restore database logs with specified system change numbers, set this parameter to **Specified SCN**. |

    2.  Configure the restoration job.

        -   Job Name: the name of the restoration job.
        -   Restoration Time: By default, this parameter is set to Right Now, which indicates that the restoration job is immediately run.
    3.  Configure the restoration settings.

        -   Reconnection Time: the interval between the time when the database is disconnected and the time when the database is reconnected.
        -   Restoration Rate Limit: the amount of data that is restored per second.
    4.  Configure the destination database instance.

        Select a destination database instance. Default value: Source Instance.

6.  Click **Create**.

7.  After you create a restoration job, the job automatically starts. On the **Restore Jobs** tab, you can view the status of the restoration job.


