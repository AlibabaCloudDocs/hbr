# Restore an SAP HANA database {#concept_kjd_p1k_ggb .concept}

After using Hybrid Backup Recovery \(HBR\) to back up SAP HANA databases to a backup vault, you can restore the SAP HANA databases to the original SAP HANA instance or another SAP HANA instance that uses the same backup vault.

**Note:** When restoring SAP HANA databases, HBR automatically stops these databases. As a result, you cannot access these databases during restoration.

## Procedure {#section_wbp_t3s_ggb .section}

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, choose **ECS Backup** \> **SAP HANA Backup**.
3.  Click the **SAP HANA Instance** tab.
4.  Find the SAP HANA instance to be restored, and click **Restore** in the Actions column.
5.  In the New Restore Task dialog box, select the source SAP HANA instance and click **Next**.
6.  Verify the information about the source SAP HANA instance and the destination SAP HANA instance. Set **Source System Name**, select a database on the destination SAP HANA instance, and then click **Next**.

    **Note:** The **Source System Name** parameter specifies the name of the source database. Enter the name in the following format: `Source database name@SID`.

7.  Set **Restore Policy** and other parameters as required. The following table describes restoration policies.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83256/156818810760278_en-US.jpg)

    |Restoration policy|Description|Parameter|
    |:-----------------|:----------|:--------|
    |Most Recent|Restores the database to the latest available status.|     -   **Use Differential**: Turn on this switch if you want to use differential backup or incremental backup to restore the database. If you turn off this switch, HBR uses log backup to restore the database.
    -   **Use Log Area**: specifies whether to initialize a log area. If you turn on this switch, you initialize the log area and cannot use log entries in this log area. Set this parameter as required. You can turn on this switch when the log area is unavailable, or you want to restore the database to a different system.
    -   **Validate Differential and Log**: If you turn on this switch, HBR checks the availability of the required differential backup and log backup when the restoration job starts. If the differential backup or the log backup is unavailable, HBR stops the restoration job until the backup data is available.
 |
    |Time Point|Restores the database to the status at a specified time point.|     -   **Use Differential**: Turn on this switch if you want to use differential backup or incremental backup to restore the database. If you turn off this switch, HBR uses log backup to restore the database.
    -   **Use Log Area**: specifies whether to initialize a log area. If you turn on this switch, you initialize the log area and cannot use log entries in this log area. Set this parameter as required. You can turn on this switch when the log area is unavailable, or you want to restore the database to a different system.
    -   **Validate Differential and Log**: If you turn on this switch, HBR checks the availability of the required differential backup and log backup when the restoration job starts. If the differential backup or the log backup is unavailable, HBR stops the restoration job until the backup data is available.
    -   **Restore to Time**: Select a time point that you want to restore the database to. HBR restores the database to the status closest to the specified time point.
 |
    |From Snapshot|Restores the database to a specified backup.|     -   **Use Catalog**: specifies whether to restore the database from catalog backup.
    -   **Backup Prefix**: If you turn off Catalog, you need to specify the prefix of a backup file. This allows HBR to find the backup file to restore the database.
 |
    |Log Position|Restores the database to the status when a specified log was generated.|     -   **Use Differential**: Turn on this switch if you want to use differential backup or incremental backup to restore the database. If you turn off this switch, HBR uses log backup to restore the database.
    -   **Use Log Area**: specifies whether to initialize a log area. If you turn on this switch, you initialize the log area and cannot use log entries in this log area. Set this parameter as required. You can turn on this switch when the log area is unavailable, or you want to restore the database to a different system.
    -   **Validate Differential and Log**: If you turn on this switch, HBR checks the availability of the required differential backup and log backup when the restoration job starts. If the differential backup or the log backup is unavailable, HBR stops the restoration job until the backup data is available.
    -   **Log Position**: Specify the log generated in the status that you want to restore the database to.
    -   **Volume ID**: Specify the ID of the volume to be restored.
 |

8.  Click **Next**.
9.  Specify a backup as the reference. Then, click **Create**.

## Related operations {#section_clt_1by_ggb .section}

In the HBR console, you can view the status of restoration jobs and cancel ongoing restoration jobs. The procedure is as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, choose **ECS Backup** \> **SAP HANA Backup**.
3.  Click the **Restore Jobs** tab.
4.  View the restoration job status on the Restore Jobs tab.
5.  To cancel an ongoing restoration job, click **Cancel** in the right-side Actions column for the job.

