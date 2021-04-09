# Create an ECS instance backup

Hybrid Backup Recovery \(HBR\) is integrated with the Alibaba Cloud backup service to provide agentless backup for Elastic Compute Service \(ECS\) instances and disks. HBR can create crash-consistent snapshots for all disk categories, including system and data disks. You can use these snapshots to back up or restore an entire disk.

## Background

The ECS instance protection feature allows you to protect an ECS instance or specified disks by using a periodic disk backup strategy. This ensures long-term and low-cost protection.

![guide](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4301397161/p261922.png)

## Step 1: Add an ECS instance

1.  Log on to the [HBR console](https://hbr.console.aliyun.com/).

2.  In the left-side navigation pane, choose **Backup** \> **ECS Server Backup**.

3.  In the upper-right corner of the page, click **+Add ECS Instance**.

4.  In the Create ECS Protection Plan wizard, select the ECS instance that you want to protect.

    **Note:** If you need to protect all disks of the ECS instance, turn on the **Protect All Disks** switch. In this case, disks that are subsequently attached to the ECS instance are also protected. If you need to protect only some of the disks, turn off the **Protect All Disks** switch.


## Step 2: Configure a backup plan

If you need to create backups on a regular basis, turn on the On Schedule switch. If you turn off the switch, a snapshot of the ECS instance is immediately created.

In the Create ECS Protection Plan wizard, configure a backup plan. The following table describes the parameters.

|Parameter|Description|
|---------|-----------|
|Plan Name|The name of the backup plan. If you do not specify this parameter, a random name is generated and assigned to the backup plan.|
|Start Time|The start time of the scheduled backup plan. The time is accurate to seconds.|
|Backup Interval|The interval between backups. Unit: hours, days, or weeks.|
|Retention Period|The retention period of backup data. Unit: days, weeks, months, or years.|

## Step 3: Enable application-consistent backup

1.  Enable the application-consistent backup feature.

    You can enable this feature for Windows or Linux instances.

    -   Enable the application-consistent backup feature for a Windows ECS instance

        -   If you select **Enable Application-consistent Backup** and **Contain Writers by Default**, an application-consistent backup is created.
        -   If you select only **Enable Application-consistent Backup**, a file system-consistent backup is created.
        **Note:** If the Cloud Assistant client is not installed on your instance, the client is automatically installed when the backup is created after you select **Enable Application-consistent Backup**.

    -   Enable the application-consistent backup feature for a Linux ECS instance
        1.  Write the application pre-freeze and post-thaw scripts based on the applications in the instance and upload the scripts to the instance.

            You can use the FTP service or Cloud Assistant to upload the application pre-freeze and post-thaw scripts to the instance.

            -   Application pre-freeze script: Configure the script to allow only the root user to have the read, write, and execute permissions on the script. Set the storage path to /tmp/prescript.sh.
            -   Application post-thaw script: Configure the script to allow only the root user to have the read, write, and execute permissions on the script. Set the storage path to /tmp/postscript.sh.
            **Note:** If the script configurations such as permissions, save path, or file name are invalid, a file system-consistent backup is created.

        2.  Configure the application-consistent backup feature.

            -   If you select **Enable Application-consistent Backup** and **Enable File System Freeze and Thaw** and configure valid scripts, an application-consistent backup is created.
            -   If you select **Enable Application-consistent Backup** and **Enable File System Freeze and Thaw** but do not configure valid scripts, a file system-consistent backup is created.
            **Note:** If the Cloud Assistant client is not installed on your instance, the client is automatically installed when the backup is created after you select **Enable Application-consistent Backup**.

2.  Click **OK**.

    After the backup plan is created, HBR backs up data from the specified start time at the specified interval. On the **Protection Plans** tab, you can perform the following operations on the backup plan:

    -   To start a backup job, find the backup plan and click **Run Now** in the **Actions** column.
    -   To modify a backup plan, find the backup plan and click **Modify** in the **Actions** column. For example, you can modify the interval between backups.
    -   To suspend a running backup job, find the backup plan and choose **More** \> **Suspend Plan** in the **Actions** column. To resume a suspended backup job, find the backup plan and choose **More** \> **Resume Plan** in the Actions column.
    -   To delete a backup plan, find the backup plan and choose **More** \> **Delete Plan** in the **Actions** column. After you delete the backup plan, HBR no longer runs backup jobs for the plan. However, the backup data is retained.

## What to do next

The ECS instance backup feature provides the following tabs. This allows you to efficiently manage backup jobs.

|Tab|Description|Operations|
|---|-----------|----------|
|**Protected ECS Instances**|Displays the ECS instances that are protected.|-   **Protect Now**: Specify all or some disks for protection. You can set the Retention Period and Long-term Backup parameters.
-   **Stop Protection**: Stop protection for an ECS instance.

**Note:** If you stop protection for an ECS instance, this ECS instance is removed from the protected ECS instance list. All protection plans of this ECS instance are deleted. The generated ECS instance backups are retained. You can click backup points in the backup history to delete the ECS instance backups. |
|**Protection Plans**|Displays the protection plans that you have configured.|-   **Run Now**: Immediately implement a protection plan.
-   **Modify**: Modify a protection plan.
-   **Suspend Plan**: If you stop a protection plan, no backup or snapshot protection is performed.
-   **Delete Plan**: If a protection plan expires, you can delete the plan. |
|**Jobs**|Displays the status of implemented jobs.|You can cancel the jobs that are being implemented. For the jobs of the Mount Disk type, you can unmount disks.|
|**Export Records**|Displays the exported ECS disk files. HBR allows you to browse and download the exported files.|-   **Browse**: Immediately implement a protection plan.
-   **Download**: Modify a protection plan.
-   **Cancel**: If you suspend a protection plan, no backup protection is performed. |

