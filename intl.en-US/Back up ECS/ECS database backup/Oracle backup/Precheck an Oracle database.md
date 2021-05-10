# Precheck an Oracle database

Before you use Hybrid Backup Recovery \(HBR\) to back up an Oracle database, you can perform a precheck. This allows you to identify conditions that may cause backup failure.

After you register an Oracle instance, you can precheck the instance to identify conditions that may cause backup failure. This way, you can prevent backup failure in advance. To start a precheck, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS Database Backup**. On the ECS Database Backup page, click **Oracle** in the top navigation bar.

3.  Select the region where the Oracle instance to be backed up resides.

4.  On the Database Instance tab, find the Oracle instance that you want to precheck, and click **Precheck** in the **Actions** column.

5.  On the **Backup Precheck** page, click **Start Check**.

    You can click **View Last Precheck Result** to view the result of the most recent backup precheck. The following table describes the check items of the precheck.

    |Check items|Description|
    |-----------|-----------|
    |OSS connectivity|Checks whether the Oracle instance is connected to the **VPC Access from ECS \(Internal Network\)** domain of the OSS instance. If the check fails, you cannot perform backup or recovery operations.|
    |Control network connectivity|Checks whether the Oracle instance is connected to the control network If the check fails, you cannot perform operations on the Oracle instance|
    |Oracle instance status|Checks whether the Oracle instance is in normal status. If the check fails, you cannot back up or recover Oracle databases that are deployed on the ECS instance.|
    |Oracle database status|Checks whether the Oracle databases in the preceding instance is in normal status. If the check fails, you cannot back up or recover the prompted Oracle databases.|
    |Archive mode|Check whether the archive mode of the Oracle instance is normal. If the check fails, you cannot back up the Oracle databases that are deployed on the ECS instance.|

6.  The precheck requires about one minute to complete. The following figure indicates that the precheck is complete.

    If a check item fails the precheck, check whether the failure affects backup and recovery of the database.

    -   If the failure does not affect backup and recovery of the database, the precheck is complete.
    -   If the failure affects the backup and recovery of the database, you can read the description in the preceding table to fix the issue.
    ![oracle](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5261460261/p260730.png)


