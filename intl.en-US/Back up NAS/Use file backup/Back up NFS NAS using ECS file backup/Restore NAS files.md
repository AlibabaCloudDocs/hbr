# Restore NAS files

You can restore Apsara File Storage NAS files to the source Elastic Compute Service \(ECS\) instance or another ECS instance that uses the same backup vault. You can also restore NAS files that are backed up by using a backup client for on-premises files to an ECS instance.

1.  Log on to the [Hybrid Backup Recovery \(HBR\) console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS File Backup**.

3.  On the **ECS Instances** tab, find the destination ECS instance, and click **Restore** in the Actions column.

4.  In the Create Restore Job pane, set the Restore From parameter to one of the following values:

    -   **Current ECS Instance**

        Select this option if you need to restore files from the current ECS instance. Then, perform the following steps:

        1.  Click **Next**.
        2.  In the Select Backup step, select a backup and click **Next**.
        3.  In the Configure Restore Policy step, enter a destination path, select a restore policy, specify the files that you want to restore based on the policy, and then click **Create**.
    -   **Other ECS Instance**

        Select this option if you need to restore files from another ECS instance that uses the same backup vault as the current ECS instance. Then, perform the following steps:

        1.  Select the source ECS instance and click **Next**.
        2.  In the Select Backup step, select a backup and click **Next**.
        3.  In the Configure Restore Policy step, enter a destination path, select a restore policy, specify the files that you want to restore based on the policy, and then click **Create**.
    -   **On-premises Server**

        Select this option if you need to restore NAS files that are backed up by using a backup client for on-premises files. Then, perform the following steps:

        1.  Select the client that is used to back up files from the on-premises server and click **Next**.
        2.  In the Select Backup step, select a backup and click **Next**.
        3.  In the Configure Restore Policy step, enter a destination path, select a restore policy, specify the files that you want to restore based on the policy, and then click **Create**.
    **Note:** You can view the progress of a restore job on the **Restore Jobs** tab of the ECS File Backup page.


