# Restore a CSG instance {#task_473652 .task}

You can restore a file gateway backup to its original CSG instance. When necessary, you can also restore the file gateway backup of a CSG instance to another CSG instance in the same vault.

## Procedure {#section_jz8_hor_jph .section}

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  Select the region of the CSG instance to which you want to restore data.
3.  In the left-side navigation pane, click **Storage Gateway Backup**.
4.  On the **Storage Gateway Backup** page, click the Cloud Gateway Instance tab.
5.  Locate the target CSG instance and click **Restore** in the Actions column.
6.  In the Select Source Instance step in the New Restore Task wizard, set **Restore Resource** as needed.
    -   **From This ECS** 

        Select this option if you need to restore backup files from the current CSG instance. Then, perform the following steps:

        1.  Click **Next**.
        2.  In the Select Snapshot step, select a snapshot and click **Next**.
        3.  In the Config Restore Rules step, enter the path to restore data, select the files to be restored, and then click **Create**.
    -   **From Other ECS** 

        Select this option if you need to restore backup files from another CSG instance in the same vault to the current CSG instance. Then, perform the following steps:

        1.  Select the CSG instance where the backup files reside and click **Next**.
        2.  In the Select Snapshot step, select a snapshot and click **Next**.
        3.  In the Config Restore Rules step, enter the path to restore data, select the files to be restored, and then click **Create**.

## Related operations {#section_fpt_mmi_in7 .section}

On the Storage Gateway Backup page, click the Restore Jobs tab. On this tab, you can view the restoration status of a job or cancel a running job.

