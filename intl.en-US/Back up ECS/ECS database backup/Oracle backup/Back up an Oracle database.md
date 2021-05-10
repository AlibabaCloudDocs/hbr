# Back up an Oracle database

You can use Hybrid Backup Recovery \(HBR\) to back up Oracle databases deployed on Elastic Compute Service \(ECS\) instances and restore these databases as needed. This topic describes how to back up an Oracle database.

## Create a backup plan

After you register an Oracle instance, you can create a backup plan to back up the instance. To create a backup plan, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS Database Backup**. On the ECS Database Backup page, click the **Oracle** tab.

3.  Select the region where the Oracle instance to be backed up resides.

4.  On the Database Instance tab, find the Oracle instance to be backed up. Click Back Up in the **Actions** column.

5.  In the **Create Backup Plan** panel, perform the following steps:

    1.  Set the parameters for the backup.

        1.  Specify **Plan Name**.
        2.  Select the Oracle instance that you want to back up.
        3.  Click **Next**.
    2.  Configure the backup plan.

        1.  Select a backup policy.

            |Parameter|Description|
            |---------|-----------|
            |Full Backup|If you select Full Backup, all the database files in the operating system are backed up. However, you can only restore files that are backed up after a specific point in time. You can back up files immediately or at the specified time. You can also back up files by hour, day, week, or month. |
            |Cumulative Incremental Backup|If you select Cumulative Incremental Backup, all the database files in the operating system are backed up. However, you can only restore files that are backed up after a specific point in time. You can back up files immediately or at the specified time. You can also back up files by hour, day, week, or month. |
            |Log Backup|If you select Log Backup, database logs are backed up. **Scheduled Backup** and **Continuous Backup** are supported.             -   Scheduled Backup

You can back up database logs immediately or at the specified time. You can also schedule periodic backup by hour, day, week, or month.

            -   Continuous Backup

Before you enable Continuous Backup, you must complete a full backup. After Continuous Backup is enabled, database logs are continuously backed up. Therefore, the recovery point objective \(RPO\) of data backups can be reduced to seconds. If you use the Continuous Backup feature, you are charged for the storage capacity of log backups. For more information, see [HBR pricing](https://cn.aliyun.com/price/detail/hbr).

**Note:** You can create only one backup plan that contains continuous backup for a single Oracle instance. |

        2.  Select the Oracle instance that you want to back up.
        3.  Click **Next**.
    3.  Configure the backup settings. Click **Next**.

        You can specify the number of backup channels, the reconnection time, and the limit of the backup speed.

    4.  Select a backup vault.

        -   If you have created backup vaults, click **Select Vault** and select a backup vault from the **Vault Name** drop-down list.
        -   If you want to create a backup vault, click **Create Vault** and specify the Vault Name parameter.
6.  Click **OK**.


