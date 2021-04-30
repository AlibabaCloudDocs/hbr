# Migrate data from VMware VMs to ECS instances

This topic describes how to migrate a VMware virtual machine \(VM\) on an on-premises host or storage to Alibaba Cloud by using the Hybrid Backup Recovery \(HBR\) console.

## Prerequisites

The system disk of each migration source has at least 1 GB of available space before migration. Grand Unified Bootloader \(GRUB\) 1.99 or later is used for VMs that run the Linux operating system.

**Note:**

-   For earlier operating system versions such as CentOS 5, Red Hat 5, and Debian 7, you must use GRUB 1.99 or later.
-   For some operating systems such as Amazon Linux, you must use GRUB 2.02 or later.

## Background information

HBR provides non-intrusive, agentless, and full-copy migration of data that is stored on VMware VMs. HBR migrates data by using VMware snapshots and reading data from disks. These features allow you to migrate all the data from the disks of VMware VMs to the disks of ECS instances.

-   Regions

    HBR allows you to migrate VMware VMs to Alibaba Cloud in multiple regions. You can log on to the HBR console to view the supported regions.

-   Operating systems

    You can use HBR to migrate VMware VMs that run the following operating systems: CentOS, Ubuntu, CoreOS, Aliyun Linux, Debian, Gentoo, SUSE Linux, openSUSE, FreeBSD, Red Hat Enterprise Linux \(RHEL\), Windows Server 2003, Windows Server 2008, Windows Server 2012, Windows Server 2016, Windows 7, custom Linux distribution, Mars, and NeoKylin.


## Step 1: Create a migration gateway

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Migration** \> **VMware VM Migration**.

3.  In the upper-right corner of the Migration Gateway tab, click **Create Migration Gateway**.

    **Note:** You can create only one migration gateway in one region.

4.  In the **Create Migration Gateway** panel, set the required parameters and click **Create**.

    The following table describes the required parameters.

    |Parameter|Description|
    |:--------|:----------|
    |Gateway Name|The name of the migration gateway. The name must be 1 to 64 characters in length.|
    |Software Platform|The software platform of the VMware VM from which you want to migrate data. You can set the value to **vSphere**.|
    |Network Type|    -   **VPC**: Select this option if you want the migration gateway to transmit data over a VPC.
    -   **Internet**: Select this option if no VPCs are available. |
    |Use HTTPS|Specifies whether to use HTTPS to transmit encrypted data that is stored in a backup vault. If HTTPS is used, the performance of data transmission is compromised. If you modify the setting of this parameter, the modification takes effect on the next backup or restoration job.|

5.  Click **Download Client** and **Download Certificate**.

    **Note:** The backup client is used to connect your server or VM to HBR. The certificate is used to activate the client. You can also download the client and the certificate from the client list.


## Step 2: Install the backup client

After you download the client and the certificate, install the client on a VM. After the client is installed, you can use the client to run migration jobs. To install the client, perform the following steps:

1.  Log on to the vSphere Web Client.

    **Note:** HBR supports only vCenter Server 5.5, 6.0, and 6.5.

2.  In the left-side navigation pane, right-click the VM, and select **Deploy OVF Template** from the shortcut menu.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9256449951/p35163.png)

    **Note:** For more information, see [Deploying OVF and OVA Templates](https://docs.vmware.com/cn/VMware-vSphere/6.5/com.vmware.vsphere.vm_admin.doc/GUID-AFEDC48B-C96F-4088-9C1F-4F0A30E965DE.html?spm=a2c4g.11186623.2.20.37f4127dVeFZcm).

3.  In the Deploy OVF Template dialog box, select **Local file**. Click **Browse**, select the client template that you downloaded, and then click **Next**.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9256449951/p35164.png)

4.  Enter the name of the open virtual format \(OVF\) or open virtual appliance \(OVA\) template, select the location where you want to deploy the template, and then click **Next**.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5051409951/p68313.jpg)

5.  Select the location where you want to run the deployed template and click **Next**.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9256449951/p35166.png)

6.  Verify the details of the template and click **Next**.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9256449951/p35167.png)

7.  Select the format of the virtual disk as needed, select a storage to store files for the deployed template, and then click **Next**.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9256449951/p35168.png)

8.  Select the destination network for each source network and click **Next**.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5051409951/p68314.jpg)

9.  Configure the required deployment properties for the software solution and click **Next**.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9256449951/p35170.png)

10. Verify the configurations and click **Finish**.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0356449951/p35171.png)

11. View the progress of the deployment task in the Recent Tasks section.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6051409951/p68331.jpg)

12. After the deployment task is completed, start the VM on which the OVF or OVA template is deployed.

13. Open a browser, and enter `http://hostname:8011` in the address bar.

    **Note:** The value of `hostname` is the IP address of the VM. This is the VM on which the OVF or OVA template is deployed.

14. On the Register page, set the parameters and click **Register** to log on to the HBR gateway. The following table describes the required parameters.

    |Parameter|Description|
    |:--------|:----------|
    |AccessKey ID|The AccessKey ID and AccessKey secret of the Resource Access Management \(RAM\) user that is used to access HBR. You can obtain the AccessKey ID and AccessKey secret of a RAM user from your Alibaba Cloud account for which HBR is activated. For more information, see [Create an AccessKey for a RAM user](/intl.en-US/FAQ/Common issues/Create an AccessKey for a RAM user.md).|
    |AccessKey Secret|
    |Certificate|The certificate that you download from the HBR console. If a VM is shut down for more than five days after you use the certificate to activate the client on the VM, the certificate expires. In this case, you must download a new certificate to reactivate the client.|

    After the client is activated, click **OK** to go to the HBR console.


## Step 3: Add a vCenter Server

1.  On the **Migration Gateway** tab, find the migration gateway, and click **View** in the Actions column.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6051409951/p68353.jpg)

2.  In the upper-right corner of the Backend vCenter Servers page, click **Add vCenter Server**.

3.  In the **Add vCenter Server** panel, set the **Server IP**, **Username**, and **Password** parameters. Then, click **Create**.

    You may fail to add a vCenter Server if the password contains the following special characters:

    \` ^ ~ = ; ! / \( \[ \] \{ \} @ $ \\ & \# % +

    **Note:** We recommend that you create a vCenter Server account that is dedicated for backup. We recommend that you use periods \(.\) but not other special characters in the password of the account.


## Step 4: Migrate data from a VMware VM

1.  On the vCenter Servers page, find the vCenter Server, and click **Migrate** in the Actions column.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6051409951/p68364.jpg)

2.  In the Create Migration Plan panel, set parameters in the **Configure Migration Plan** step and click **Next**. The following table describes the required parameters.

    ![plan](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6051409951/p84834.jpg)

    |Parameter|Description|
    |---------|-----------|
    |**Plan Name**|The name of the migration plan. If you do not specify this parameter, a random name is generated by default.|
    |**Configure Migration Plan**|The migration policy. Valid values: **Right Now** and **On Schedule**. If you select **On Schedule**, you must set the **Start Time** parameter. The value is accurate to the second. |
    |**Force Quiesced Snapshot**|    -   If you select this check box, HBR uses quiesced snapshots to migrate data. If quiesced snapshots are unavailable, the backup fails.
    -   If you do not select this check box, HBR attempts to use quiesced snapshots to migrate data. If quiesced snapshots are unavailable, HBR switches to common snapshots to migrate data. By default, this check box is not selected. |
    |**Enable Incremental Sync**|Specifies whether to enable incremental migration. If you enable incremental migration, you must set the **Incremental Sync Frequency** parameter. Unit: hours, days, or weeks.

**Note:**

    -   If Changed Block Tracking \(CBT\) is disabled for the VM, a full migration job instead of an incremental migration job is run.
    -   If incremental migration is enabled, HBR automatically creates an image to test whether workloads can be switched to the destination. The cost of the image is included in the billing for ECS instead of HBR billing. For more information, see [Billing overview](/intl.en-US/Pricing/Billing overview.md). |

3.  In the **Select VMs to Migrate** step, select the source VMs and click **Next**.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6051409951/p68369.jpg)

4.  In the **Configure ECS Instance** step, set the following parameters: **VPC**, **VSwitch**, **Instance Family**, **Instance Type**, **Disk Type**, **Security Group**, **IP Address Type**, **Assign Public IP**, **Reboot After Restoration**, and **Create System Image**. Then, click **Apply to All VMs** or **Apply to Current VM**.

    **Note:** Make sure that the security group allows outbound data transfer over TCP port 80, TCP port 443, and UDP port 53.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6051409951/p68373.jpg)

5.  Click **Create** to start the migration job. On the Migration Plans tab, you can view the progress of the migration job.

    ![syn](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6051409951/p84851.jpg)

    If incremental migration is enabled, you can perform the following operations after the migration is complete:

    -   Click **Sync Tasks** in the Actions column of the migration job to view the size of the migrated incremental data and the migration status.

        ![syn](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6051409951/p85372.jpg)

    -   Click **Create ECS Instance** in the Actions column. In the dialog box that appears, select **Verify Migration** or **Finish Migration**.

        ![verification](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6051409951/p85370.jpg)

        -   If you select **Verify Migration**, HBR creates an ECS instance and migrates data after the last migration to the ECS instance, for example, 20:21:31, February 21, 2020. This way, you can check whether the source VM works as expected. You can perform a maximum of three migration verifications. During migration verifications, incremental migration is performed as planned. After you click **OK**, HBR creates an ECS instance. If you click **Resume Migration** in the Actions column, HBR deletes the ECS instance and resumes the migration.

            ![continue](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6051409951/p85373.png)

        -   If you select **Finish Migration**, HBR creates an ECS instance and migrates data after the last migration to the ECS instance, for example, 20:21:31, February 21, 2020. HBR also stops the migration job. If you select **Run an incremental synchronization task before finishing the migration job**, HBR migrates data that is generated after the last incremental migration to the created ECS instance.
        **Note:**

        -   If you select Run an incremental synchronization task before finishing the migration job, more time is required to finish the migration job.
        -   You are charged for the migration of the VM only the first time you verify the migration or finish the migration job. If you repeatedly perform verifications or if you finish the migration job after a verification, you are not charged. For more information, see [Pricing](https://www.alibabacloud.com/product/hybrid-backup-recovery/pricing).
    -   Click **Cancel Migration** in the Actions column to cancel the migration job.

## Logs

For information about how to collect logs, see [Collect logs and diagnose network issues](/intl.en-US/Back up on-premises severs/Back up virtual machine image/Collect logs and diagnose network issues.md).

