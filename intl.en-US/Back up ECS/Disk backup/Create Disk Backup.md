# Create Disk Backup

Hybrid Backup Recovery \(HBR\) is integrated with the Alibaba Cloud snapshot service to provide agentless backup for Elastic Compute Service \(ECS\) instances and disks. HBR can create crash-consistent backup for all disk categories, including system and data disks. You can use these backups to restore an entire disk.

## Step 1: Select Disk

**Note:** When you add an ECS instance and disks, you must make sure that the disks are in the **In Use** or **Unattached** state. If the disks are in the In Use state, the ECS instance must be in the **Running** or **Stopped** state.

1.  Log on to the [HBR console](https://hbr.console.aliyun.com/).

2.  In the left-side navigation pane, choose **Backup** \> **Disk Backup**.

3.  Click **Disk Backup Wizard** in the upper-right corner.

4.  Select the disks that you want to protect.

    **Note:** If you want to protect all disks of the ECS instance, enable **Protect All Disks**. In this case, disks to be attached in the future are also protected.

    If you want to protect only some of the disks, disable **Protect All Disks**.


## Step 2：Configure Backup Plan

1.  Select **Backup Type**.

    -   Manual backup

        If you use this method, you only need to specify the **Backup Name** parameter.

        The name must be 2 to 128 characters in length and cannot start with a special character or digit. It can contain periods \(.\), underscores \(\_\), hyphens \(-\), and colons \(:\).

    -   Automatic backup

        If you use this method, you can select an existed backup policy. You can also click **Create Backup Policy** to configure a new backup policy and specify the following parameters.

        |Parameter|Description|
        |---------|-----------|
        |**Policy Name**|The name of the custom plan.|
        |**Backup Time**|The time when the backup job was created.|
        |**Backup Week**|The interval between backups.|
        |**Retention Period**|The retention period of the backup data in the source region.         -   **Keep For**: You can specify a retention period. Valid values: 1 to 65536. Unit: days.
        -   **Continuous Retention**: Backups in the destination region are always retained. |
        |**Cross-region Replication**|If you enable Cross-region Replication, backups created by this backup plan are automatically replicated to the destination region.         -   Backups can be replicated between the China \(Hong Kong\) and Singapore \(Singapore\) regions.
        -   If the ECS instance is affected by viruses or data loss is caused by accidental deletion, you can use backups in the source region or backups replicated to the destination region to create an instance or disk to restore data. |
        |**Destination Region**|The region to which you replicate the backups.|
        |**Retention Period of Replication**|The retention period of the backup data in the destination region.         -   **Keep For**: You can specify a retention period. Valid values: 1 to 65536. Unit: days.
        -   **Continuous Retention**: Backups in the destination region are always retained. |

2.  Click **OK**。


