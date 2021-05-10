# Register an SQL Server instance

Before you use Hybrid Backup Recovery \(HBR\) to back up SQL Server databases deployed on ECS instances, you must register an SQL Server instance in the HBR console.

-   When you register an SQL Server instance, you must set the connection parameters of the SQL Server instance. After the SQL Server instance is registered, an ECS backup client is installed on each node of the SQL Server instance.
-   After an SQL Server instance is registered, you can view the installation status of the ECS backup client on each node of the SQL Server instance. Make sure that an ECS backup client is installed on all the nodes to be backed up. You can also upgrade, uninstall, or delete an ECS backup client based on your business needs.

## Register a database instance

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS Database Backup**. On the ECS Database Backup page, click **SQL Server**.

3.  Select the region where the SQL Server instance to be backed up resides.

4.  In the upper-right corner, click **Register Database Instance**.

5.  In the **Select Database Instance** step, all the databases in the current region are displayed. Select a database. Click **Next**.

6.  In the **Authenticate** step, set the required parameters as described in the following table.

    |Parameter|Description|
    |:--------|:----------|
    |Database Account|The username of the database instance.|
    |Password|The password of the database instance.|

7.  Click **Create**.

    After the registration is complete, you can view the details and status of the database instance on the Database Instance tab.


