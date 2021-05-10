# Precheck an SQL Server database

Before you use Hybrid Backup Recovery \(HBR\) to back up SQL databases that are deployed on ECS instances, you can perform a precheck to identify conditions that may cause backup failure.

After you register a SQL Server instance, you can precheck the instance to identify conditions that may cause backup failure. This way, you can prevent backup failure in advance. To start a precheck, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS File Backup**. On the ECS Database Backup page, click **SQL Server** in the top navigation bar.

3.  Select the region where the SQL Server instance that you want to back up resides.

4.  On the Database Instances tab, find the SQL Server instance that you want to precheck, and click **Precheck** in the **Actions** column.

5.  On the **Backup Precheck** page, click **Start Check**.

    You can click **View Last Precheck Result** to view the results of the most recent backup precheck. The following table describes the check items of the precheck.

    |Check items|Description|
    |-----------|-----------|
    |OSS connectivity|Checks whether the Oracle instance is connected to the **VPC Access from ECS \(Internal Network\)** domain of the OSS instance. If the check fails, you cannot perform backup and recovery operations.|
    |Control network connectivity|Checks whether the instance is connected to the control network. If the check fails, you cannot perform operations on this database instance.|
    |Recovery mode|Checks the recovery mode of the SQL database. If the check fails, the prompted database cannot be incrementally backed up.|
    |Database offline status|Checks whether the SQL Server is online. If the check fails, you cannot back up or recover the prompted SQL Server databases.|

6.  The precheck requires about one minute to complete. The following figure indicates that the precheck is complete.

    If a check item fails the precheck, check whether the failure affects backup and recovery of the database.

    -   If the failure does not affect backup and recovery of the database, the precheck is complete.
    -   If the backup and recovery of the database are affected, you can read the description in the preceding table to fix the issue.
    ![sqlserver](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9841460261/p260735.png)


