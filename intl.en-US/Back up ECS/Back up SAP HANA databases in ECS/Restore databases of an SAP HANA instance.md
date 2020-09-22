# Restore databases of an SAP HANA instance

After you use Hybrid Backup Recovery \(HBR\) to back up SAP HANA databases to a backup vault, you can restore the databases to the source SAP HANA instance, another SAP HANA instance that uses the same backup vault, or an SAP HANA instance in another region.

## Prerequisites

Databases of an SAP HANA instance are backed up. For more information, see [Back up an SAP HANA database](/intl.en-US/Back up ECS/Back up SAP HANA databases in ECS/Back up an SAP HANA database.md).

## Background

When an SAP HANA database is being restored, HBR automatically stops the database. Therefore, you cannot access the database during the restoration.

## Restore a database to the source SAP HANA instance

To restore a database to the source SAP HANA instance, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS Application Backup**. On the ECS Application Backup page, click **SAP HANA**.

3.  Click the **SAP HANA Instances** tab.

4.  On the SAP HANA Instances tab, find the SAP HANA instance and click **Restore** in the Actions column.

5.  In the Create Restore Job pane, select the destination SAP HANA instance as the source instance and click **Next**.

    ![HANA instance](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8459029951/p96449.jpg)

6.  Confirm the source and destination SAP HANA instances, select the source database, and then click **Next**.

    ![DB](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8459029951/p96454.jpg)

7.  Set the parameters, including **Restore To**, and click **Next**.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8459029951/p35979.png)

    The following table describes the valid values of the Restore To parameter.

    |Value of the Restore To parameter|Description|Parameter|
    |:--------------------------------|:----------|:--------|
    |**Latest Recovery Point**|Restores the database to the latest recovery point.|    -   **Use Differential Backup**: Turn on this switch if you need to restore a differential or incremental backup of the database. If you turn off this switch, HBR uses a log backup to restore the database.
    -   **Initialize Log Area**: Turn on this switch if you need to delete all the log entries from the log area after restoration.
    -   **Validate Differential and Log Backups**: If you turn on this switch, HBR checks whether the required differential backup and log backup are available before the restore job starts. If the differential backup or log backup is unavailable, HBR does not start the restore job. |
    |**Specified Time Point**|Restores the database to the recovery point that is closest to a specified time point.|    -   **Use Differential Backup**: Turn on this switch if you need to restore a differential or incremental backup of the database. If you turn off this switch, HBR uses a log backup to restore the database.
    -   **Initialize Log Area**: Turn on this switch if you need to delete all the log entries from the log area after restoration.
    -   **Validate Differential and Log Backups**: If you turn on this switch, HBR checks whether the required differential backup and log backup are available before the restore job starts. If the differential backup or log backup is unavailable, HBR does not start the restore job.
    -   **Time Point**: Select a time point to which that you want to restore the database. HBR restores the database to the recovery point that is closest to the time point. |
    |**Specified Backup**|Restores the database to a specified backup.|**Use Catalog**: Turn on this switch if you need to restore a catalog backup of the database. **Note:** If you turn off this switch, you must specify the prefix of a backup version. This allows HBR to find the backup based on the version to restore the database. |
    |**Specified Log Entry**|Restores the database to the status when a specified log entry is generated.|    -   **Use Differential Backup**: Turn on this switch if you need to restore a differential or incremental backup of the database. If you turn off this switch, HBR uses a log backup to restore the database.
    -   **Initialize Log Area**: Turn on this switch if you need to delete all the log entries from the log area after restoration.
    -   **Validate Differential and Log Backups**: If you turn on this switch, HBR checks whether the required differential backup and log backup are available before the restore job starts. If the differential backup or log backup is unavailable, HBR does not start the restore job.
    -   **Log Entry**: Specify a log entry. HBR will restore the database to the status when the log entry is generated.
    -   **Volume ID**: Specify the ID of the volume to restore. |

8.  Select a backup version to restore and click **Create**.


## Restore a database to another SAP HANA instance in the same region

The procedure for restoring an SAP HANA database to another SAP HANA instance that uses the same backup vault and resides in the same region is similar to that for restoring an SAP HANA database to the source SAP HANA instance. The only difference is that you must select a source SAP HANA instance that is different from the destination SAP HANA instance.

![instance2](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8459029951/p96460.jpg)

In addition, after confirming the source and destination SAP HANA instances, you must set **Source Database Name** in the `<Source database name>@<SID>` format.

![systemname](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8459029951/p96469.jpg)

**Note:** For more information about how to restore the SAP HANA database to another SAP HANA instance, see [Restore a database to the source SAP HANA instance](#section_ddv_n6h_rx6).

## Restore a database to an HAP SANA instance in another region

A backup vault is a repository that HBR uses to store backup data in the cloud. A mirror vault is the mirror of a backup vault. The two vaults reside in different regions. You can restore an SAP HANA database across regions by using a mirror vault to implement disaster recovery.

Before you can restore an SAP HANA database to an SAP HANA instance in another region, you must create a mirror vault for the backup vault of the source SAP HANA database. For information about how to create a mirror vault, see [Use a mirror vault to back up data across regions](/intl.en-US/Remote backup/Use a mirror vault to back up data across regions.md).

To restore an SAP HANA database to an SAP HANA instance in another region, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS Application Backup**. On the ECS Application Backup page, click **SAP HANA**.

3.  Select the region where the mirror vault resides.

4.  On the **SAP HANA Instances** tab, install a backup client on each node of the SAP HANA instance.

    **Note:** You must select an existing mirror vault. Mirror vaults are tagged with \[COPY\]. For more information about how to set other parameters when installing the backup client, see [Register an SAP HANA instance](/intl.en-US/Back up ECS/Back up SAP HANA databases in ECS/Manage backup clients for an SAP HANA instance/Register an SAP HANA instance.md).

5.  On the SAP HANA Instances tab, find the source SAP HANA instance, and click **Restore** in the Actions column.

    For information about the other steps, see [Restore a database to another SAP HANA instance in the same region](#section_5ox_k3g_4am).


## What to do next

To view the status of restore jobs or cancel running restore jobs, perform the following steps:

1.  In the left-side navigation pane, choose **Backup** \> **ECS Application Backup**. On the ECS Application Backup page, click **SAP HANA**.

2.  Click the **Restore Jobs** tab.

3.  View the status of each restore job in the Status column.

4.  To cancel a running restore job, find the job and click **Cancel** in the Actions column.


