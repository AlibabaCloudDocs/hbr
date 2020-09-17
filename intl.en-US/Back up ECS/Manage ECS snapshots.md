# Manage ECS snapshots

This topic describes how to configure a snapshot plan in the Hybrid Backup Recovery \(HBR\) console to enable disk protection for all or specified disks of an Elastic Compute Service \(ECS\) instance. This topic also describes how to clone or roll back an ECS instance or a specified disk based on snapshots.

## Background information

HBR supports disk protection for all or specified disks of ECS instances based on snapshots. You can also back up the snapshots to a backup vault. This provides cost-effective and long-term protection for the ECS instances.

![ECS](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/3996749951/p99924.jpg)

**Note:** Features such as snapshot backup and instant access will be available soon.

## Step 1: Add an ECS instance

1.  Log on to the [HBR console](https://hbr.console.aliyun.com/).

2.  In the left-side navigation pane, choose **Backup** \> **ECS Snapshots**.

3.  In the upper-right corner of the **ECS Snapshots** page, click **+Add ECS Instance**.

4.  In the Create ECS Protection Plan wizard, select the ECS instance that you want to protect.

    **Note:** If you need to protect all disks of the ECS instance, turn on the **Protect All Disks** switch. In this case, disks that are attached after the snapshot plan is created are also protected. If you need to protect only some of the disks, turn off the **Protect All Disks** switch and select the disks that you want to protect.


## Step 2: Configure a snapshot plan

Turn on the **On Schedule** switch if you need snapshots to be created at regular intervals. If you turn off the switch, a snapshot of the ECS instance is immediately created.

1.  In the Create ECS Protection Plan wizard, configure a snapshot plan.

    If you turn on the **On Schedule** switch, set the following parameters.

    |Parameter|Description|
    |---------|-----------|
    |Plan Name|The name of the scheduled snapshot plan. If you do not specify this parameter, a random name is used.|
    |Start Time|The start time of the scheduled snapshot plan. The time is accurate to seconds.|
    |Snapshot Interval|The interval between two consecutive snapshots. Unit: hours, days, or weeks.|
    |Retention Period|The retention period of snapshots. Unit: days, weeks, months, or years.|

2.  Click **OK**.

    If a snapshot plan is configured, ECS snapshots will be immediately created at the specified interval, starting from the specified time. On the **Protection Plans** tab, you can perform the following operations on the snapshot plan:

    -   To start a snapshot job, find the snapshot plan and click **Run Immediately** in the **Actions** column.
    -   To modify a snapshot plan, find the snapshot plan and click **Modify** in the **Actions** column. For example, you can modify the snapshot interval.
    -   To pause a running snapshot job, find the snapshot plan and choose **More** \> **Suspend Plan** in the **Actions** column. To resume a paused snapshot job, choose **More** \> **Resume Plan** in the **Actions** column.
    -   To delete a snapshot job, find the snapshot plan and choose **More** \> **Delete Plan** in the **Actions** column. After you delete a snapshot plan, HBR no longer runs the plan but the backup data is retained.

## Restore a protected ECS instance \(Optional\)

If a system failure or error occurs on a protected ECS instance, you can perform the following steps to clone or roll back the ECS instance based on a snapshot. To clone or roll back the ECS instance, you must have a minimum of one snapshot.

1.  On the **Protected ECS Instances** tab, find the ECS instance.

2.  Click **Clone** or **Roll Back** in the **Actions** column.

3.  On the **Instance Protection** tab, select an available snapshot point to clone or roll back.

    -   Select an available snapshot point to clone
        1.  Click the available snapshot point. In the dialog box that appears, click **Clone**.
        2.  In the Create ECS Instance from Snapshot pane, set the parameters as prompted.
        3.  Click **Create**.
    -   Select an available snapshot point to roll back

        **Note:** An ECS instance can be rolled back only if the ECS instance is stopped and no snapshot is being created for the ECS instance. The data that is written to the protected ECS instance will be deleted when the ECS instance is rolled back. Proceed with caution.

        1.  Click the available snapshot point. In the dialog box that appears, click **Roll Back**.
        2.  In the message that appears, click **OK**.

## Restore a protected disk \(Optional\)

If a system failure or error occurs on a protected disk of an ECS instance, you can perform the following steps to clone or roll back the disk based on a snapshot. To clone or roll back the disk, you must have a minimum of one snapshot.

1.  On the **Protected ECS Instances** tab, find the ECS instance.

2.  Click **Clone** or **Roll Back** in the **Actions** column.

3.  On the **Disk Protection** tab, select an available snapshot point to clone or roll back.

    -   Select an available snapshot point to clone
        1.  Click the available snapshot point. In the dialog box that appears, click **Clone**.
        2.  In the Select ECS Instance step of the **Create Disk from Snapshot** wizard, select an ECS instance to mount the new disk, and then click **Next**.
        3.  In the Set Mount Parameters step, select **Ultra Disk** or **Standard SSD** as **Disk Type**.
        4.  Click **Create**.
    -   Select an available snapshot point to roll back

        **Note:** A disk can be rolled back only if the ECS instance is stopped and no snapshot is being created for the disk. The data that is written to the protected disk will be deleted when the disk is rolled back. Proceed with caution.

        1.  Click the available snapshot point. In the dialog box that appears, click **Roll Back**.
        2.  In the message that appears, click **OK**.

