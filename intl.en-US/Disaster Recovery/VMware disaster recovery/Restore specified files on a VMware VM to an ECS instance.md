# Restore specified files on a VMware VM to an ECS instance

This topic describes how to use the instant mount feature of the Hybrid Backup Recovery \(HBR\) console to restore specified files on a VMware virtual machine \(VM\) to an Elastic Compute Service \(ECS\) instance.

## Background information

In some scenarios, you may need to restore only specific backed-up files on a VMware VM. In this case, you can use the instant mount feature of HBR to mount the disk that stores backed-up files on the VMware VM to an ECS instance. This way, you can view and restore the backed-up files on the VM.

For more information about how to restore a VMware VM to an Alibaba Cloud ECS instance, see [Restore a VMware VM to an ECS instance](/intl.en-US/Disaster Recovery/VMware disaster recovery/Restore a VMware VM to an ECS instance.md).

## Limits

When you mount the disk of a VM to an ECS instance, note the following items:

-   The ECS instance must support the file system of the disk. In addition, the file system version of the ECS instance must be the same to or later than the file system version of the disk.
-   If the disk of the VM contains LVM volumes, you must ensure that LVM tools are installed on the ECS instance and the names of volume groups \(VGs\) and logical volumes \(LVs\) on the disk are different from those on the ECS instance.
-   LVM volumes across disks are not supported.
-   SoftRAID volumes are not supported.

## Supported resources

The following OSs, volume types and file systems are supported:

-   Supported OSs for the source VM: Ubuntu 20.04 LTS, Ubuntu 18.04 LTS, Ubuntu 16.04 LTS, Debian 10.X, Debian 9.X, CentOS 7.X, CentOS 8.X, RHEL 7.X, and RHEL 8.X
-   Supported OSs for the destination ECS instance: CentOS 7.X and CentOS 8.X
-   Supported volume types: RAW volume and LVM volume
-   Supported file systems for disks: ext3, ext4, and xfs

## Procedure

Perform the following steps to restore specific files on a VMware VM to an ECS instance by using the instant mount feature in the HBR console:

1.  Mount a disk to an ECS instance.

    1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

    2.  In the left-side navigation pane, choose **Disaster Recovery** \> **VMware Disaster Recovery**.

    3.  On the VMware Disaster Recovery page, click the Backups tab. Find the backup record to restore and click **Instant Mount** in the Actions column corresponding to the record.

    4.  In the Select Disk step, select the disk that you want to mount and click **Next**.

    5.  In the Select ECS Instance step, select an ECS instance to which you want to mount the disk and click **Next**.

        **Note:** Cloud Assistant must be installed on the ECS instance.

    6.  In the Set Mount Parameters step, confirm the settings of the **Disk Name**, **ECS Instance Name**, and **ECS Instance ID** parameters. Then, set **Mount Point** for caching and **Mount Point** and click **Create**.

        You can customize the path used to temporarily store the backed-up files restored from the mounted VM disk. The default path is **/tmp**. You can also customize the path to which the VM disk is mounted. The default path is **/mnt**.

        After the disk is mounted to the ECS instance, an agent is automatically installed on the ECS instance to provide access to the mounted disk.

        **Note:** The path to which the VM disk is mounted must be empty.

2.  Restore files on the VMware VM.

    1.  Log on to the destination ECS instance.

        Go to the path to which the source VM disk is mounted. View directory of each mounted volume and select the files to restore.

        ![1](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/1880703061/p148919.png)

    2.  Run the cp command to restore the files to a specified folder.

        For example, you can run the cp -v /mnt/vg3-vg3-lvdata/mnt4/govc\_linux\_amd64.gz /media/ command to restore the govc\_linux\_amd64.gz file in /mnt/vg3-vg3-lvdata/mnt4/ to the /media directory.

3.  Uninstall the agent.

    1.  After the files are restored, ensure that the path to which the VM disk is mounted is not used.

    2.  Go back to the HBR console. Click the Restore Jobs tab. Find the restore job and click **Uninstall** in the Actions column corresponding to the job.

        If the status of the job changes to **Uninstalled**, the agent is uninstalled.


