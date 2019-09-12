# Restore data from a backup to an ECS instance {#task_tb2_bgm_qfb .task}

You can restore files to an ECS instance from a backup stored on it or another ECS instance in the same vault. You can also restore files to an ECS instance from a backup that is created by a backup client.

1.  Log on to the [Hybrid Backup Recovery \(HBR\) console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, choose **ECS Backup** \> **ECS File Backup**.
3.  On the ECS File Backup page, select the **ECS instance** tab.
4.  Locate the target ECS instance, and click **Restore** in the Actions column of the instance.
5.  In the New Restore Task dialog box, select a Restore Source. 

    -   From this ECS

        If you need to restore data from a backup stored on this ECS instance, you can select this option and perform the following steps.

        1.  Click **Next**.
        2.  Select a snapshot, and click **Next**.
        3.  Enter the Restore Path, select files to be restored, and click **Create**.
    -   From Other ECS

        If you need to restore data from a backup stored on another ECS instance in the same vault to this ECS instance, you can select this option and perform the following steps.

        1.  Select an ECS instance where the backup is located and click **Next**.
        2.  Select a snapshot and click **Next**.
        3.  Enter the Restore Path, select files to be restored, and click **Create**.
    -   From Local Client

        If you need to restore a backup that is created by a file client from a local data center to this ECS instance, you can select this option and perform the following steps.

        1.  Select a local host where the required backup is located and click **Next**.
        2.  Select a snapshot, and click **Next**.
        3.  Enter the Restore Path, select files to be restored, and click **Create**.
    **Note:** On the ECS File Backup page, select the **Restore Jobs** tab to view the progress of the new restore job.


