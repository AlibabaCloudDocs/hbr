# Restore a MySQL database

After you use Hybrid Backup Recovery \(HBR\) to back up a MySQL database to a backup vault, you can restore the MySQL database as needed. You can restore the database to the original MySQL instance, another MySQL instance that uses the same backup vault, or a MySQL instance in another region.

## Prerequisites

The MySQL database is backed up. For more information, see [Back up a MySQL database](/intl.en-US/Back up ECS/ECS database backup/MySQL backup/Back up a MySQL database.md).

## Create a restoration job

To create a restoration job, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS Database Backup**. On the ECS Database Backup page, click **MySQL**.

3.  Select the region where the MySQL instance to be backed up resides.

4.  On the ECS Instances tab, find the destination ECS instance, and click Restore in the **Actions** column.

5.  In the Create Restore Job dialog box, configure the following settings as prompted. Click **Next**.

    1.  Set the parameters for the restoration job.

        Select **Database** from the **Restoration Source** drop-down list.

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


