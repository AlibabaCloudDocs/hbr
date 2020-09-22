# Restore shares of a gateway

You can use Hybrid Backup Recovery \(HBR\) to restore shares to the source gateway. You can also restore shares to a gateway that resides in the same region as the source gateway.

## Procedure

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  Select the region where the destination gateway resides.

3.  In the left-side navigation pane, choose **Backup** \> **CSG Backup**.

4.  On the CSG Backup page, click the Storage Gateways tab.

5.  On the Storage Gateways tab, find the destination gateway, and click **Restore** in the Actions column.

6.  In the Create Restore Job pane, set the **Restore From** parameter.

    -   **Current Gateway**

        Select this option if you need to restore files from the current gateway. Then, perform the following steps:

        1.  Click **Next**.
        2.  Select a backup and click **Next**.
        3.  In the Configure Restore Policy step, enter a destination path, select a restore policy, specify the files that you want to restore based on the policy, and then click **Create**.
    -   **Other Gateway**

        Select this option if you need to restore files from another gateway that uses the same backup vault as the current gateway. Then, perform the following steps:

        1.  Select the source gateway and click **Next**.
        2.  Select a backup and click **Next**.
        3.  In the Configure Restore Policy step, enter a destination path, select a restore policy, specify the files that you want to restore based on the policy, and then click **Create**.

## What to do next

You can view the status of the restore job on the Restore Jobs tab of the CSG Backup page. You can also cancel the job when it is running.

