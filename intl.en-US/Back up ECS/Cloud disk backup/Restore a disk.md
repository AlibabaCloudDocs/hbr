# Restore a disk

If a disk that is attached to an Elastic Compute Service \(ECS\) instance encounters a system failure or an error operation, you can roll back or clone the disk to restore data. You can use a backup point in the source region or a backup point in the destination region. This topic describes how to restore a disk.

The disk backup feature can protect all disks that are attached to ECS instances, including the disks that are subsequently attached. This feature can also protect specified disks. To restore a disk, you can use a backup in the source region or a backup that is replicated to the destination region.

## Clone and roll back a disk

If a disk that is attached to an ECS instance encounters a system failure or an error operation, you can restore the disk by using an existing backup.

1.  On the **Protected ECS Instances** tab, find the ECS instance.

2.  Click the ![jia](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1974887161/p261872.png) icon before the ECS instance.

3.  On the **Disk Backup History** tab, select a backup point in the source region or a backup point in the destination region.

    -   Clone a disk by using a backup point in the instance backup history
        1.  Click a backup point. Click **Clone**.
        2.  On the Restore Backup Point to New Disk page, select the ECS instance to which the new disk is attached. Click **Next**.
        3.  On the Configure Attachment Parameters tab, select a disk type.
        4.  Click **Create**.
    -   Roll back a disk by using a backup point in the instance backup history

        **Note:**

        -   A disk can be rolled back only if the ECS instance is stopped and no snapshot is being created for the disk. The data that is written to the protected ECS instance is removed when the disk is rolled back. Proceed with caution.
        -   Backups that are replicated to the destination region can only be used for the clone operation, but not for the roll back operation.
        1.  Click a backup point. Click **Roll Back**.
        2.  In the message that appears, click **OK**.

