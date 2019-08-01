# Back up the image of a VMware virtual machine {#concept_dhr_h4c_ggb .concept}

You can use a VM client to back up the image of a local virtual machine. HBR supports the following backup modes: instant backup and scheduled backup. You can select the required backup mode based on your business needs.

## Instant backup {#section_jlf_vb2_qfb .section}

If you have no regular backup plan and only need to perform a full backup, you can perform the following steps:

1.  Log on to the Hybrid Backup Recovery Gateway. In the top navigation pane, select **Backup**.
2.  Add target backup servers. Click **Add Server** in the upper-right corner or choose **Actions** \> **Add Server**.
3.  In the Add Server dialog box, enter the Type, IP Address, Username, and Password, and click **OK**.
4.  In the upper-right corner of the page, click **Create Backup Plan**.
5.  Enter the Plan Name, specify the Retention, and select **Instant**. Click **Next**.
6.  Select one or more virtual machines and click **Next**.
7.  Confirm the backup and virtual machine information, and click **Create**.

**Note:** After a backup plan is created, you can view the details of the backup plan on the Backup Plans tab.

## Scheduled backup {#section_ypd_r4d_ggb .section}

If you have a regular backup plan, you can create a scheduled backup based on a custom backup policy. Proceed as follows:

1.  Log on to the Hybrid Backup Recovery Gateway. In the top navigation bar, click **Backup**.
2.  Click **Add Server** in the upper-right corner or choose **Actions** \> **Add Server** to add the target backup server.
3.  In the Add Server dialog box, enter the IP address, username, and password of the target backup server, and click **OK**.
4.  Click **Create Backup Plan**.
5.  Enter the name of a backup plan, select a retention period, and select **Scheduled**.
6.  Select a full backup policy. If you need to perform an incremental backup, select an incremental backup policy and click **Next**.

    **Note:** When you perform an incremental backup for a virtual machine, you must enable Changed Block Tracking \(CBT\) on the virtual machine. For more information about CBT, see [VMware documentation](https://kb.vmware.com/s/article/1020128?spm=a2c4g.11186623.2.15.1dbd3d605QVWc7).

7.  Select one or more virtual machines, and then click **Next**.
8.  Confirm the backup and virtual machine information, and click **Create**.

    **Note:** After a backup plan is created, you can view the details of the backup plan on the Backup Plans tab.


