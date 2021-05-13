# Precheck an MySQL database

Before you use Hybrid Backup Recovery \(HBR\) to back up MySQL databases that are deployed on ECS instances, you can perform a precheck to identify conditions that may cause backup failure.

After you register a MySQL instance, you can precheck the instance to identify conditions that may cause backup failure. This way, you can prevent backup failure in advance. To start a precheck, perform the following steps:

1.  In the left-side navigation pane, choose **Backup** \> **ECS Database Backup**. On the ECS Database Backup page, click **MySQL** in the top navigation bar.

2.  On the Database Instances tab, find the MySQL instance that you want to precheck, and click **Precheck** in the **Actions** column.

3.  On the **Backup Precheck** page, click **Start Check**.

    You can click **View Last Precheck Result** to view the results of the most recent backup precheck. The following table describes the check items of the precheck.

    |Check items|Description|
    |-----------|-----------|
    |OSS connectivity|Checks whether the Oracle instance is connected to the **VPC Access from ECS \(Internal Network\)** domain of the OSS instance. If the check fails, you cannot perform backup and recovery operations.|
    |Control network connectivity|Checks whether the instance is connected to the control network. If the check fails, you cannot perform operations on this database instance.|
    |Support full backup version|Checks the version of the MySQL database that supports full backup. MySQL 8.0 does not support incremental backup.|
    |BINLOG|Checks whether the binlog configuration of the MySQL instance is correctly configured. If the check fails, you cannot backup the binary logs of the database.|

4.  The precheck requires about one minute to complete. The following figure indicates that the precheck is complete.

    If a check item fails the precheck, check whether the failure affects backup and recovery of the database.

    -   If the failure does not affect backup and recovery of the database, the precheck is complete.
    -   If the backup and recovery of the database are not affected, you can read the description in the preceding table to fix the issue.
    ![mysql](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8470460261/p260715.png)


