# Restore a disk

When a disk that is attached to an Elastic Compute Service \(ECS\) instance encounters a system failure or an error operation, you can roll back or clone the disk and restore data by using backup points in the source region or backup points replicated to the destination region.

The disk backup feature can protect all disks that are attached to ECS instance, including the disks that are subsequently attached. This feature can also protect specified disks. To restore a disk, you can use a backup in the source region or a backup that is replicated to the destination region.

## Cloning and rollback

1.  Click the **Protected Disk** tab.

2.  Click the ![jia](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1974887161/p261872.png) icon before the required cloud disk.

3.  On the **Disk Backup History** tab, select a backup point in the source region or a backup point in the destination region.

    -   Clone
        1.  Click the backup point. Click **Clone**.
        2.  On the Restore Backup Point to New Disk page, select the ECS instance to which the new disk is attached. Click **Next**.
        3.  On the Configure Attachment Parameters tab, select a disk type.
        4.  Click **Create**.
    -   Rollback

        **Note:**

        -   A disk can be rolled back only if the ECS instance is stopped and no snapshot is being created for the disk. The data that is written to the protected ECS instance is removed when the disk is rolled back. Proceed with caution.
        -   Backups that are replicated to the destination region can only be used for the clone operation, but not for the roll back operation.
        1.  Click the backup point . Click **Restore**.
        2.  In the message that appears, click **OK**.

## Cross region replication

You can replicate the backup of a specified cloud disk to a destination region.

1.  Click the **Protected Disk** tab.

2.  Click the ![jia](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1974887161/p261872.png) icon before the required cloud disk.

3.  On the **Disk Backup History** tab, select a backup point.

    1.  Click a backup point. Click **Copy**.
    2.  On the Copy page, select a destination region, and set a backup name, and specify a backup description.
    3.  Click **Create**.

