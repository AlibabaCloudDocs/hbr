# Back up files from ECS instances

This topic describes how to use Hybrid Backup Recovery \(HBR\) to back up ECS files.

## Prerequisites

[Preparations](/intl.en-US/Back up ECS/ECS file backup (new)/Preparations.md) are completed.

## Create a backup plan

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS File Backup**.

3.  Click the **ECS Assets** tab.

4.  Click **Back Up** in the Actions column corresponding to the ECS instance from which you want to back up files.

5.  In the **Create Backup Plan** panel, set the parameters described in the following table and click **OK**.

    |Parameter|Description|
    |---------|-----------|
    |Backup Vault|If you have created backup vaults, click **Select Vault** and select a backup vault from the Vault Name drop-down list. If you have not created backup vaults, click **Create Vault** and specify Vault Name. The vault name must be 1 to 64 bytes in length. **Note:** A backup vault is a repository where HBR stores backup data in the cloud. You can back up files from multiple HBR backup clients to the same vault. Backup vaults reside in different regions. You can select or create a backup vault only in the current region. |
    |Plan Name|The name of the backup plan. By default, a random name is used.|
    |Backup Folders|Select **All Folders** or **Specified Folders**.    -   If you select **All Folders**, you must select whether to turn on **Exclude System Folders**.
        -   If you turn on **Exclude System Folders**, the system folders of Windows and Linux ECS instances are not backed up.

You can move the pointer over the ![1](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/5987554061/p171965.jpg) icon to the right of **Exclude System Folders** to view the system folders in Windows and Linux.

        -   If you turn off **Exclude System Folders**, all folders of the ECS instances are backed up.
    -   If you select **Specified Folders**, you must enter **Source Paths**.

Specify the paths based on the following rules:

        -   If the source path does not contain an asterisk \(\*\) wildcard, you can enter up to eight source paths.
        -   If the source path contains an asterisk \(\*\) wildcard, you can enter only a single path. The path can be in the `/*/*` format.
        -   Only absolute paths are supported, such as paths that start with `/`, `\\`, `C:\`, or `D:\`.
        -   If VSS backup is used, you can enter only one path. UNC paths and wildcards \(\*\) are not supported. You cannot exclude files from the backup plan.
        -   If UNC paths are used, VSS paths and wildcards \(\*\) are not supported. You cannot exclude files from the backup plan. If a UNC path is specified, HBR does not back up the access control list \(ACL\) of Windows. |
    |Backup File Type|You can select **All Types** or **Specified Type**.You can move the pointer over the ![1](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/5987554061/p171965.jpg) icon to the right of **Backup File Type** to view the supported backup file types.

If you select **Specified Type**, you must select the types of the files you want to back up from the **Select File Type** drop-down list. |
    |Start Time|The start time of the backup plan. The time is accurate to the second.|
    |Backup Interval|The interval at which the backup is performed. Unit: hours, days, or weeks.|
    |Retention Period|The retention period of the backup data. Unit: days, weeks, months, and years.|
    |Throttle Bandwidth|Specifies whether to throttle the bandwidth. You can limit the bandwidth used for data backup during peak hours to guarantee business continuity.If you turn on Throttle Bandwidth, you must select the Time Range \(Hour\) based on your requirements, enter the Max Bandwidth \(MB\) for backup during the specified time range, and then click **Add**. |


## What to do next

-   Use HTTPS to transmit data

    Note that HTTPS compromises the performance of data transmission. If you modify the setting of this parameter, the modification takes effect on the next backup or restore job.

    After data is encrypted and stored in the backup vault, you can choose **More** \> **Client Settings** in the Actions columns and select whether to use HTTPS to transmit data.

-   Configure a backup alert policy

    You can choose **More** \> **Alert Settings** in the Action columns and then select a backup alert policy described in the following table.

    |Alert policy|Description|
    |------------|-----------|
    |**Disabled**|The HBR backup client does not send alert notifications.|
    |**Same as Vault**|The HBR backup client send alert notifications in the same way as the backup vault.|
    |**Default**|The HBR backup client sends alert notifications to the Alibaba Cloud account that owns the ECS instance by using emails.|
    |**Custom**|If you select this option, you must select one or more contacts or contact groups. The HBR backup client sends alert notifications to the selected contacts and contact groups.|

-   Delete a backup

    If you delete a backup, all backup data generated by the HBR backup client is deleted and all backup and restore jobs that are being performed by the client fail. Before you delete an HBR backup client, ensure that the backup data generated by the backup client is no longer required and that no backup and restore jobs are being performed by the backup client.

    You can choose **More** \> **Delete Backup** in the Actions column and then click OK to delete the backup data that is no longer required.


