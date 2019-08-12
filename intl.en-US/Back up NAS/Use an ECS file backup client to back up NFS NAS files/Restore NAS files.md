# Restore NAS files {#task_960860 .task}

You can restore backup NAS files to their original ECS instance or another ECS instance in the same vault. When necessary, you can also restore NAS files backed up by a file backup client in a local IDC to the specified ECS instance.

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, choose **Cloud Backup** \> **ECS File Backup**.
3.  On the ECS File Backup page, click the **ECS Instance** tab.
4.  Locate the target ECS instance and click **Restore** in the Actions column.
5.  In the New Restore Task dialog box that appears, set Restore Resource. 

    -   **From This ECS** 

        Select this option if you need to restore backup files from the current ECS instance. Then, perform the following steps:

        1.  Click **Next**.
        2.  Select a snapshot and click **Next**.
        3.  Set Restore Path, select the files to be restored, and then click **Create**.
    -   **From Other ECS** 

        Select this option if you need to restore backup files from another ECS instance in the same vault to the current ECS instance. Then, perform the following steps:

        1.  Select the ECS instance where the backup files reside and click **Next**.
        2.  Select a snapshot and click **Next**.
        3.  Set Restore Path, select the files to be restored, and then click **Create**.
    -   **From Local Client** 

        Select this option if you need to restore files backed up by a file backup client in a local IDC to the current ECS instance. Then, perform the following steps:

        1.  Select the local client where the backup files reside and click **Next**.
        2.  Select a snapshot and click **Next**.
        3.  Set Restore Path, select the files to be restored, and then click **Create**.
    **Note:** On the ECS File Backup page, click the **Restore Jobs** tab to view the progress of the restoration job.


