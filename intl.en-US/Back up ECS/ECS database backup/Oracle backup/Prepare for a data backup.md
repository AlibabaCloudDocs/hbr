# Prepare for a data backup

You can use Hybrid Backup Recovery \(HBR\) to back up Oracle databases deployed on Elastic Compute Service \(ECS\) instances and restore these databases as needed. This topic describes the preparations that you must make before a data backup.

## Step 1: Create and assign RAM roles to HBR

Before you use HBR to back up SQL Server databases deployed on ECS instances, you must authorize the AliyunHBRDefaultRole and AliyunECSAccessingHBRRole roles to access your cloud resources. To create and assign the roles, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS Database Backup**. Click **Oracle**. On the page that appears, assign the roles as prompted.


## Step 2: Install and configure Cloud Assistant

-   An HBR backup client for ECS must be used in combination with Cloud Assistant. By default, a Cloud Assistant client is installed on ECS instances that are created after December 1, 2017. On ECS instances purchased before December 1, 2017, install a Cloud Assistant client. For more information, see [Install the cloud Assistant client](/intl.en-US/Deployment & Maintenance/Cloud assistant/Configure the Cloud Assistant client/Install the Cloud Assistant client.md).
-   After you install a Cloud Assistant client on an ECS instance whose network type is classic network, configure the Cloud Assistant client based on the operating system of the ECS instance.
    -   Windows:
        1.  Connect to the ECS instance. In the C:\\ProgramData\\aliyun\\assist\\ directory, create a file named `region-id`. In the file, enter the ID of the region where the ECS instance resides.`` For example, for an ECS instance that resides in the China \(Hangzhou\) region, enter `cn-hangzhou`.

            ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8895084951/p39296.png)

            The following table lists the regions and region IDs.

            |Region|region-id|
            |:-----|:--------|
            |China \(Hangzhou\)|cn-hangzhou|
            |China \(Shanghai\)|cn-shanghai|
            |China \(Beijing\)|cn-beijing|
            |China \(Shenzhen\)|cn-shenzhen|

        2.  Restart AliyunService in Task Manager.
    -   Linux:
        1.  Connect to the ECS instance. In the /usr/local/share/aliyun-assist/ directory, create a file named `region-id`. In the file, enter the `region ID` based on the region where the ECS instance resides. For example, for an ECS instance that resides in the China \(Hangzhou\) region, enter `cn-hangzhou`.![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8895084951/p39297.png)

            The following table lists the regions and region IDs.

            |Region|region-id|
            |:-----|:--------|
            |China \(Hangzhou\)|cn-hangzhou|
            |China \(Shanghai\)|cn-shanghai|
            |China \(Beijing\)|cn-beijing|
            |China \(Shenzhen\)|cn-shenzhen|

        2.  To restart the Cloud Assistant client, run the `chkconfig agentwatch off` command and then the `chkconfig agentwatch on` command. Otherwise, you can run the `systemctl restart agentwatch` command.

            **Note:** If the Cloud Assistant client still does not work after the restart, run the preceding commands to restart it again.


