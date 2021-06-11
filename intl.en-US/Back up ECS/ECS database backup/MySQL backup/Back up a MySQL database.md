# Back up a MySQL database

You can use Hybrid Backup Recovery \(HBR\) to back up MySQL databases that are deployed on Elastic Compute Service \(ECS\) instances. You can also restore these databases as needed. This topic describes how to back up a MySQL database.

## Create a backup plan

After you register a MySQL instance, you must create a backup plan to back up the instance by using HBR. To create a backup plan, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS Database Backup**.

3.  On the ECS Database Backup page, click the **MySQL** tab.

4.  Select the region where the MySQL instance that you want to back up resides.

5.  On the Database Instance tab, find the MySQL instance that you want to back up. Click Back Up in the **Actions** column.

6.  In the **Create Backup Plan** panel, perform the following steps:

    1.  Set the backup parameters.

        1.  Specify **Plan Name**.
        2.  Select the MySQL instance that you want to back up.
        3.  Click **Next**.
    2.  Configure the backup plan.

        1.  Select a backup policy. The following table describes the related parameters.

            |Parameter|Description|
            |---------|-----------|
            |Full Backup|If you select Full Backup, all the database files in the operating system are backed up. However, you can restore the files only to a specific point in time. You can back up files immediately or at a specified time. You can also schedule periodic backups by hour, day, week, or month. |
            |Cumulative Incremental Backup|If you select Cumulative Incremental Backup, incremental database files in the operating system are backed up. However, you can restore the files only to a specific point in time. You can back up files immediately or at a specified time. You can also schedule periodic backups by hour, day, week, or month.

**Note:** If your MySQL database \(earlier than MySQL 5.5\) uses the MyISAM engine, the database does not support incremental backup. In this case, HBR changes incremental backup to full backup. |
            |Log Backup|If you select Log Backup, database logs are backed up. You can select **Scheduled Backup** or **Continuous Backup**, depending on your backup scenarios.             -   Scheduled Backup

You can back up database logs immediately or at a specified time. You can also schedule periodic backup by hour, day, week, or month.

            -   Continuous Backup

Before you enable Continuous Backup, you must complete a full backup. After Continuous Backup is enabled, database logs are continuously backed up. Therefore, the recovery point objective \(RPO\) of data backups can be reduced to seconds. When you use continuous log backup, you are charged for the storage capacity of log backups. For more information, see [HBR pricing](https://cn.aliyun.com/price/detail/hbr).

**Note:** You can create only one backup plan for a single MySQL instance if you enable continuous backup for the backup plan. |

        2.  Click **Next**.
    3.  Configure the backup settings.

        1.  Configure the backup settings.
            -   **Number of Concurrent Nodes**: the number of concurrent nodes when files are being backed up.
            -   **Retry Time**: the interval between the time when the database is disconnected and the time when it is reconnected during backup.
            -   **Speed Limit**: the maximum size of data that is backed up per second.
        2.  Click **Next**.
    4.  Select a backup vault.

        -   If you have created backup vaults, click **Select Vault** and select a backup vault from the **Vault Name** drop-down list.
        -   If you want to create a backup vault, click **Create Vault** and specify the Vault Name parameter and other parameters as prompted.
7.  Click **OK**.


