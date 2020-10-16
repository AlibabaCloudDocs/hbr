# Preparations

You can use Hybrid Backup Recovery \(HBR\) to back up files from Elastic Compute Service \(ECS\). You can then restore the files if needed. This topic describes the preparations that you must make before backup.

## Background information

Before you use HBR to back up files from ECS, note the following information:

-   To achieve the optimal backup speed, we recommend that you run a backup client on an ECS instance that has the following configurations: 64-bit processors, two or more CPU cores, and more than 8 GB available memory. If you need to back up tens of millions of files, 16 GB available memory is recommended.
-   The volume of data that can be backed up depends on the available memory. If a host has 4 GB available memory, a maximum of one million files or 8 TB data can be backed up.
-   You can use the ECS file backup service in the following regions: China \(Beijing\), China \(Shanghai\), China \(Shenzhen\), China \(Hangzhou\), China \(Qingdao\), China \(Zhangjiakou-Beijing Winter Olympics\), China \(Hohhot\), China \(Hong Kong\), Singapore \(Singapore\), US \(Silicon Valley\), Indonesia \(Jakarta\), Malaysia \(Kuala Lumpur\), Australia \(Sydney\), Germany \(Frankfurt\), and Japan \(Tokyo\). This service will be available in more regions soon.

## Step 1: Create and assign RAM roles to HBR

Before using HBR to back up files from ECS, you must create and assign the AliyunHBRDefaultRole and AliyunECSAccessingHBRRole roles to HBR. To create and assign the two roles, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS File Backup**. Two authorization dialog boxes appear one after one.

3.  In each dialog box, click Authorize. On the page that appears, create and assign the role to HBR as prompted.


## Step 2: Install and configure Cloud Assistant

-   An ECS backup client requires interaction with Cloud Assistant. By default, Cloud Assistant is installed on ECS instances that are created after December 1, 2017. However, you must [manually install Cloud Assistant](/intl.en-US/Deployment & Maintenance/Cloud assistant/Configure the Cloud Assistant client/Install the Cloud Assistant client.md) on ECS instances that are created before December 1, 2017.
-   If the network type of an ECS instance is classic network, perform the following steps to configure the Cloud Assistant client after you install the Cloud Assistant client on the ECS instance.
    -   Windows:
        1.  Log on to the ECS instance. In the C:\\ProgramData\\aliyun\\assist\\ directory, create a file named `region-id`. In the file, enter the ID of the region where the ECS instance resides. For example, if an ECS instance resides in the China \(Hangzhou\) region, enter `cn-hangzhou` in the file.

            ```
            echo cn-hangzhou >C:\ProgramData\aliyun\assist\region-id
            ```

            The following table lists region IDs.

            |Region|ID|
            |:-----|:-|
            |China \(Hangzhou\)|cn-hangzhou|
            |China \(Shanghai\)|cn-shanghai|
            |China \(Beijing\)|cn-beijing|
            |China \(Shenzhen\)|cn-shenzhen|

        2.  Restart the AliyunService service by using Task Manager.
    -   Linux:
        1.  Log on to the ECS instance. In the /usr/local/share/aliyun-assist/ directory, create a file named `region-id`. In the file, enter the ID of the region where the ECS instance resides. For example, if an ECS instance resides in the China \(Hangzhou\) region, enter `cn-hangzhou` in the file.

            ```
            echo cn-hangzhou >/usr/local/share/aliyun-assist/region-id
            ```

            The following table lists region IDs.

            |Region|ID|
            |:-----|:-|
            |China \(Hangzhou\)|cn-hangzhou|
            |China \(Shanghai\)|cn-shanghai|
            |China \(Beijing\)|cn-beijing|
            |China \(Shenzhen\)|cn-shenzhen|

        2.  Start the Cloud Assistant client.

            For information about how to start Cloud Assistant clients of different versions, see [Install the Cloud Assistant client](/intl.en-US/Deployment & Maintenance/Cloud assistant/Configure the Cloud Assistant client/Install the Cloud Assistant client.md#).


