# Preparations

You can use Hybrid Backup Recovery \(HBR\) to back up files from Elastic Compute Service \(ECS\) instances and restore the files based on your requirements. This topic describes the preparations that you must make before backup.

## Usage notes

Before you use HBR to back up files from ECS instances, take note of the following items:

-   To achieve the optimal backup speed, we recommend that you run a backup client on an ECS instance that has the following configurations: 64-bit processors, two or more CPU cores, and more than 8 GB available memory. If you want to back up tens of millions of files, we recommend that you configure 16 GB available memory for the backup client.
-   The volume of data that can be backed up depends on the available memory. If a backup client has 4 GB available memory, up to one million files or 8 TB of data can be backed up.

## Step 1: Create and assign RAM roles to HBR

Before you use HBR to back up files from ECS, you must create and assign the AliyunHBRDefaultRole and AliyunECSAccessingHBRRole roles to HBR. To create and assign the two roles, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS File Backup**. Two authorization dialog boxes appear in succession.

3.  In each dialog box, click Authorize. On the page that appears, create and assign the role to HBR as prompted.


## Step 2: Install and configure Cloud Assistant

-   An HBR backup client for ECS must work with Cloud Assistant. By default, Cloud Assistant is installed on all ECS instances that are created after December 1, 2017. If your ECS instance is created before December 1, 2017, you must manually install Cloud Assistant on the instance. For more information, see [Install the Cloud Assistant client](/intl.en-US/Deployment & Maintenance/Cloud assistant/Configure the Cloud Assistant client/Install the Cloud Assistant client.md).
-   If the network type of the ECS instance is classic network, perform the following steps to configure the Cloud Assistant client after you install Cloud Assistant on the ECS instance.
    -   Windows:
        1.  Log on to the ECS instance. In the C:\\ProgramData\\aliyun\\assist\\ directory, create a file named `region-id`. In the file, enter the ID of the region where the ECS instance resides.`` For example, for an ECS instance that resides in the China \(Hangzhou\) region, enter `cn-hangzhou`.

            ```
            echo cn-hangzhou >C:\ProgramData\aliyun\assist\region-id
            ```

            The following table lists the ID of each region.

            |Region|region-id|
            |:-----|:--------|
            |China \(Hangzhou\)|cn-hangzhou|
            |China \(Shanghai\)|cn-shanghai|
            |China \(Beijing\)|cn-beijing|
            |China \(Shenzhen\)|cn-shenzhen|

        2.  Restart AliyunService by using the task manager.
    -   Linux:
        1.  Log on to the ECS instance. In the /usr/local/share/aliyun-assist/ directory, create a file named `region-id`. In the file, enter the ID of the region where the ECS instance resides.`` For example, for an ECS instance that resides in the China \(Hangzhou\) region, enter `cn-hangzhou`.

            ```
            echo cn-hangzhou >/usr/local/share/aliyun-assist/region-id
            ```

            The following table lists the ID of each region.

            |Region|region-id|
            |:-----|:--------|
            |China \(Hangzhou\)|cn-hangzhou|
            |China \(Shanghai\)|cn-shanghai|
            |China \(Beijing\)|cn-beijing|
            |China \(Shenzhen\)|cn-shenzhen|

        2.  Start the Cloud Assistant client.

            For information about how to start different versions of Cloud Assistant clients, see [Install the Cloud Assistant client](https://www.alibabacloud.com/help/zh/doc-detail/64921.htm#title-8j8-b5k-y9x).


## Step 3: Install and activate the HBR backup client for ECS

On the ECS Assets tab, choose **More** \> **Reinstall Client** in the Actions column corresponding to the ECS instance to which you want to restore files.

If the HBR backup client for ECS fails to be activated, choose **More** \> **Uninstall Client** in the Actions column corresponding to the ECS instance to which you want to restore files, and then reinstall the HBR backup client on the ECS instance.

