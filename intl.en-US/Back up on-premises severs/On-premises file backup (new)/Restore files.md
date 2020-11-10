# Restore files

You can restore files that are backed up on an HBR backup client to an on-premises server. You can also restore files that are backed up on another backup client in the same backup vault to the current backup client.

## Prerequisites

Files of the on-premises server are backed up. For more information, see [Back up files](/intl.en-US/Back up on-premises severs/On-premises file backup (new)/Back up files.md).

## Create a restore job

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **On-Premises Backup**.

3.  On the **Backup Plans** tab, click the ![+](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/1097554061/p172225.jpg) icon on the left of any completed backup plan.

    ![1](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6864794061/p172251.jpg)

4.  Click a backup and click **Restore**.

    You can also click **Browse** to view all the files in the client you want to restore.

    ![2](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6864794061/p172253.jpg)

5.  In the **Select Destination Instance** step, select the backup client to which you want to restore the files. Then, click **Next**.

6.  In the **Config Restore Policy** step, set **Destination Path** and **Restore Policy**.

    The following restore policies are supported:

    -   **Include All Files**: All files in the client are restored.
    -   **Include Specified Files** or **Exclude Specified Files**: In the field, enter the paths of folders or files that you want to restore or exclude. HBR restores files in the client based on the specified restore policy.

        In the Enter Paths field, enter one path in each line and ensure that each path starts with the lowest-level folder in the directory that is backed up. For example, if the files in folder/test/data are backed up and you want to restore the file.txt and abc.png files in the data folder, enter the following paths:

        ```
        /data/file.txt
        /data/abc.png
        ```

7.  Click **Start Restore**.

    After a restore job is created, you can view the job progress in the **Status** column on the Restore Jobs tab.


