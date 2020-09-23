# Cross-zone disaster recovery

If a production site encounters force majeure events such as a fire disaster or an earthquake or equipment failures such as software or hardware failures, applications may fail to run in a certain period. To ensure business continuity, Elastic Compute Service \(ECS\) disaster recovery provides cross-zone disaster recovery for you to back up application data and switch workloads to another zone to deal with failures in a single zone at the required recovery time objective \(RTO\) and recovery point objective \(RPO\).

## Prerequisites

A zone to deploy the disaster recovery system is selected. A virtual private cloud \(VPC\) is created in the zone. A VSwitch for replication and a VSwitch for restoration are created in the VPC.

## Step 1: Create a disaster recovery site pair

To create a disaster recovery site pair that provides cross-zone disaster recovery protection for ECS instances in the primary site, perform the following steps:

1.  Log on to the [Hybrid Backup Recovery \(HBR\) console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Disaster Recovery** \> **ECS Disaster Recovery**.

3.  In the upper-right corner of the Disaster Recovery Center page, click **+ Add**.

4.  In the Create Disaster Recovery Site Pair \(Continuous Data Replication\) pane, select **Zone To Zone** as Type and select the region and VPC for the primary and secondary sites.

    ![sitepair2](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/5163922951/p100126.jpg)

5.  Click **Create**.


## Step 2: Add the ECS instances to be protected

To add the ECS instances to be protected, perform the following steps:

1.  Click the Protected Server tab. In the upper-right corner of this tab, select the disaster recovery site pair that you created in [Step 1](#sitepair) from the drop-down list.

2.  On the Protected Server tab, click **+ Add**. In the Add Protected Server pane, select the ECS instances and click **OK**.

    You must select 1 to 10 ECS instances.

    In the Server Status column, verify that the status of the added ECS instances is Agent Installing and then changes to Initialized. If the status of an ECS instance is not Initialized, choose **More** \> **Server Operation** \> **Restart Server** in the Operation column to initialize the instance.


## Step 3: Start replication

To replicate ECS instances to the cloud and maintain real-time replication, follow these steps:

1.  On the **Protected Server** tab, find the ECS instance to be replicated and choose **More** \> **Failover** \> **Start Replication** in the Operation column.

2.  In the Enable Replication pane that appears, set **Recovery Point Policy**, **Use SSD**, **Replication Network**, **Recovery Network**, and **Automatic restart after replication interruption**.

    **Note:** The VSwitches used for the replication and restoration networks must be in the same zone.

    ![copy](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/5163922951/p100143.jpg)

3.  Click **Start**.

    Then, the ECS instance enters the **Enable Replicating**, **Initial Full Sync**, and **Replicating** states in sequence.

    -   **Enable Replicating**: ECS Disaster Recovery is scanning data on the ECS instance and evaluating the overall data volume. This process usually lasts a few minutes.
    -   **Initial Full Sync**: ECS Disaster Recovery is replicating valid data on the ECS instance to Alibaba Cloud. The replication duration depends on factors such as the volume of valid data on the instance and the network bandwidth. The progress bar in the Server Status column shows the replication progress.
    -   **Replicating**: After all valid data on the ECS instance is replicated to Alibaba Cloud through full replication, Aliyun Replication Service \(AReS\) monitors all write operations performed on disks on the ECS instance and continuously replicates incremental data to Alibaba Cloud in real time.

## \(Optional\) Perform a disaster recovery drill

After an ECS instance enters the Replicating state, you can perform a disaster recovery drill on the ECS instance.

A disaster recovery drill is an important part of disaster recovery. It allows you to run a protected ECS instance on the cloud to verify the correctness of relevant applications. It has the following core features:

-   Allows you to easily check whether a protected application can be run on the cloud.
-   Helps you be familiar with the disaster recovery process and makes sure that you can smoothly perform failover when the primary site encounters a failure.

To perform a disaster recovery drill, follow these steps:

1.  On the **Protected Server** tab, find the target ECS instance and click **Disaster Recovery Drill** in the Operation column.

2.  In the Test Failover pane that appears, set **Recovery Network**, **IP Address**, **Use ECS Specification**, **Hard Disk Type**, **Recovery Point**, **Elastic Public Network IP**, and **Execute script after failover**.

    **Note:**

    -   HBR automatically retains 24 recovery points in the last 24 hours for each ECS instance.
    -   If you do not select Use ECS Specification, you must specify the number of vCPUs and memory capacity.
3.  Click **Start**.

    Then, Alibaba Cloud runs the ECS instance in the background at the specified time. The disaster recovery drill performed in the background does not affect real-time data replication.

4.  After the disaster recovery drill is completed within a few minutes, click the link in the **Disaster Recovery Information** column to verify restored data and applications.

5.  After the verification is completed, click **Clear Test Failover Environment** in the Operation column. Then, the restored ECS instance is deleted.

    **Note:** After the restored ECS instance is verified, we recommend that you delete the restored ECS instance as soon as possible to reduce costs.


## Step 4: Perform failover

Regular disaster recovery drills make sure that you can run your business on the cloud at any time. When a major error occurs in the primary site, you may need to restart your core business on the cloud immediately. In this case, you must perform failover.

**Warning:** Failover is applicable to protected ECS instances where a serious error occurs. During the failover, ECS Disaster Recovery stops real-time data replication. To resume protection for a protected ECS instance, you must restart data replication and replicate all valid data on the ECS instance to Alibaba Cloud again.

To perform failover, follow these steps:

1.  On the **Protected Server** tab, find the target ECS instance and choose **More** \> **Failover** \> **Failover** in the Operation column.

2.  In the Failover pane that appears, set **Recovery Network**, **IP Address**, **Use ECS Specification**, **Hard Disk Type**, **Recovery Point**, **Elastic Public Network IP**, and **Execute script after failover**.

    **Note:** You can restore the ECS instance to the current point in time only once.

3.  Click **Start**.

4.  After the failover is completed, click the link in the **Recovered Instance ID/Name** column to verify restored data and applications.

    -   If the applications run properly after being restored to the current point in time, choose **More** \> **Failover** \> **Commit Failover** in the Operation column.

        **Note:** After you complete the failover or change the recovery point and verify that applications restored from the protected ECS instance are running your business, you can commit the failover to release the cloud resources occupied during failover to save resources.

    -   If the applications do not meet the requirements after being restored to the current point in time, for example, data in the restored database is inconsistent with that in the source database, or dirty data on the source ECS instance is synchronized to the restored ECS instance in the destination region, choose **More** \> **Failover** \> **Change Recovery Point** in the Operation column to change the recovery point before you commit the failover.
    **Note:** The procedure for changing the recovery point is similar to that for failover, except that you must select a recovery point earlier than the current point in time.


## Step 5: Perform reverse replication

After you replicate applications on a protected ECS instance in Zone A to Zone B, you can also perform reverse replication to replicate applications from Zone B to Zone A.

To perform reverse replication, perform the following steps:

1.  On the **Protected Server** tab, find the target ECS instance and choose **More** \> **Failback** \> **Reversed Register** in the Operation column. In the message that appears, confirm that you want to perform reverse registration on the ECS instance.

2.  Choose **More** \> **Failback** \> **Initiate Reverse Replication** in the Operation column.

3.  In the Initiate Reverse Replication pane that appears, set **Original machine recovery**, **Replication Network**, and **Recovery Network**.

    **Warning:** Cross-region disaster recovery and cross-zone disaster recovery allow you to replicate applications back to the original ECS instance. However, when you replicate applications back to the original ECS instance, data on the original ECS instance is overwritten. Perform this operation with caution.

4.  Click **Start**.

5.  After the ECS instance enters the Reversed Enable Replicating state, choose **More** \> **Failback** \> **Failback** in the Operation column.

6.  In the Failback pane that appears, set **CPU**, **Memory**, **Recovery Network**, **IP Address**, and **Execute script after recovery**, and click Start.

7.  After the failback is completed, choose **More** \> **Failover** \> **Registration** in the Operation column to register the protected ECS instance again.


