# Create disk backups

Hybrid Backup Recovery \(HBR\) is integrated with the Alibaba Cloud snapshot service to provide agentless backup for Elastic Compute Service \(ECS\) instances and disks. HBR can create crash-consistent snapshots for all disk categories, including system and data disks. You can use these snapshots to back up or restore an entire disk.

## Step 1: Add an ECS instance and disks

When you add an ECS instance and disks, you must make sure that the disks are in the **In Use** or **Unattached** state. If the disks are in the In Use state, the ECS instance must be in the **Running** or **Stopped** state.

1.  Log on to the [HBR console](https://hbr.console.aliyun.com/).

2.  In the left-side navigation pane, choose **Backup** \> **Disk Backup**.

3.  In the upper-right corner of the page that appears, click **+Add ECS Instance and Disk**.

4.  In the Disk Backup Wizard dialog box, select the ECS instance and disks that you want to protect.

    **Note:** If you want to protect all disks of the ECS instance, enable **Protect All Disks**. In this case, disks to be attached in the future are also protected.

    If you want to protect only some of the disks, disable **Protect All Disks**.


## Step 2: Configure a backup plan

Enable On Schedule if you want to create disk backups on a regular basis. If you disable On Schedule, a disk backup of the ECS instance is immediately created.

1.  In the Disk Backup Wizard dialog box, configure a backup plan.

    If you enable On Schedule, configure the following parameters.

    |Parameter|Description|
    |---------|-----------|
    |**Plan Name**|The name of the backup plan. If you do not specify this parameter, a random name is generated and assigned to the backup plan.|
    |**Start Time**|The start time of the scheduled backup plan. The time is accurate to seconds.|
    |**Backup Interval**|The interval between backups. Unit: hours, days, or weeks.|
    |**Retention Period**|The retention period of backup data. Unit: days, weeks, months, or years.|
    |**Cross-region Replication**|If you enable Cross-region Replication, backups created by this backup plan are automatically replicated to the destination region.     -   Backups can be replicated between the China \(Hong Kong\) and Singapore \(Singapore\) regions.
    -   If the ECS instance is affected by viruses or data loss is caused by accidental deletion, you can use backups in the source region or backups replicated to the destination region to create a instance or disk to restore data. |
    |**Destination Region**|The region to which to replicate the backups.|
    |**Replicated Backup Point Retention Period**|The retention period of the backup point replicated to the destination region.     -   **Keep For**: The retention period of the backups. Unit: days. Valid values: 1 to 65536.
    -   **Continuous Retention**: Backups in the destination region are always retained. |

2.  Click **OK**.

    After the backup plan is created, HBR backs up data from the specified start time at the specified interval. On the **Protection Plans** tab, you can perform the following operations on the backup plan:

    -   To start a backup job, find the backup plan and click **Run Now** in the **Actions** column.
    -   To modify a backup plan, find the backup plan and click **Modify** in the **Actions** column. For example, you can modify the interval between backups.
    -   To suspend a running backup job, find the backup plan and choose **More** \> **Suspend Plan** in the **Actions** column. To resume a suspended backup job, find the backup plan and choose **More** \> **Resume Plan** in the Actions column.
    -   To delete a backup plan, find the backup plan and choose **More** \> **Delete Plan** in the **Actions** column. After you delete the backup plan, HBR no longer runs backup jobs for the plan. However, the backup data is retained.

