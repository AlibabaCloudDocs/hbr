# Migrate data from VMware VMs to ECS instances

This topic describes how to migrate a VMware virtual machine \(VM\) on an on-premises host or storage to Alibaba Cloud by using the Hybrid Backup Recovery \(HBR\) console.

## Prerequisites

The system disk of each migration source has at least 1 GB available space before migration. Grand Unified Bootloader \(GRUB\) 1.99 or later is used for VMs that run the Linux operating system.

**Note:**

-   For earlier operating system versions such as CentOS 5, Red Hat 5, and Debian 7, you must use GRUB 1.99 or later.
-   For certain operating systems such as Amazon Linux, you must use GRUB 2.02 or later.

## Background information

HBR provides non-intrusive, agentless, and full-copy migration for data that is stored on VMware VMs. HBR migrates data by using VMware snapshots and reading data from disks. These features allow you to migrate all the data that is stored on disks of VMware VMs to disks of ECS instances.

-   Regions

    HBR provides the VMware VM migration service in the following regions: China \(Beijing\), China \(Shanghai\), China \(Shenzhen\), China \(Hangzhou\), China \(Zhangjiakou-Beijing Winter Olympics\), China \(Hong Kong\), Singapore \(Singapore\), US \(Silicon Valley\), Indonesia \(Jakarta\), Australia \(Sydney\), and Germany \(Frankfurt\). This service will be available in more regions soon.

-   Operating systems

    You can use HBR to migrate VMware VMs that run the following operating systems: CentOS, Ubuntu, CoreOS, Aliyun Linux, Debian, Gentoo, SUSE Linux, openSUSE, FreeBSD, Red Hat Enterprise Linux \(RHEL\), Windows Server 2003, Windows Server 2008, Windows Server 2012, Windows Server 2016, Windows 7, custom Linux distribution, Mars, and NeoKylin.


## Step 1: Create a migration gateway

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Migration** \> **VMware VM Migration**.

3.  In the upper-right corner of the Migration Gateways tab, click **Create Migration Gateway**.

    **Note:** You can create only one migration gateway in each region.

4.  In the **Create Migration Gateway** pane, set the parameters and click **Create**.

    The following table describes the parameters.

    |Parameter|Description|
    |:--------|:----------|
    |Gateway Name|The name of the migration gateway. The name must be 1 to 64 characters in length.|
    |Software Platform|The software platform of the VMware VM from which you want to migrate data. Set the value to **vSphere**.|
    |Network Type|    -   **Virtual Private Cloud \(VPC\)**: If you select this option, the migration gateway transmits data over a VPC.
    -   **Internet**: If no VPC is available, select this option. |
    |Use HTTPS|Specifies whether to use HTTPS for encrypted data transmission. Note that HTTPS compromises the performance of data transmission. Data that is stored in the backup vault is encrypted, regardless of the setting of this switch. If you modify the setting of this parameter, the modification takes effect on the next migration or restore job.|

5.  Click **Download Client** and **Download Certificate**.

    **Note:** You must install the backup client and use the certificate to activate the client before you can use HBR to back up data of a VM. You can also download the client and certificate from the client list.


## Step 2: Install the backup client

After you download the client and certificate, install the client on a VM. You can use the client to run migration jobs after the client is installed. To install the client, perform the following steps:

1.  Log on to the vSphere Web Client.

    **Note:** HBR supports only vCenter Server 5.5, 6.0, and 6.5.

2.  In the left-side navigation pane, right-click the VM, and select **Deploy OVF Template** from the shortcut menu.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9256449951/p35163.png)

    **Note:** For more information, see [Deploying OVF and OVA Templates](https://docs.vmware.com/cn/VMware-vSphere/6.5/com.vmware.vsphere.vm_admin.doc/GUID-AFEDC48B-C96F-4088-9C1F-4F0A30E965DE.html?spm=a2c4g.11186623.2.20.37f4127dVeFZcm).

3.  In the Deploy OVF Template dialog box, select **Local file**. Click **Browse**, select the client template that you downloaded, and then click **Next**.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9256449951/p35164.png)

4.  Enter the name of the open virtual format \(OVF\) or open virtual appliance \(OVA\) template, select the location where you want to deploy the template, and then click **Next**.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/5051409951/p68313.jpg)

5.  Select the location where you want to run the deployed template, and click **Next**.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9256449951/p35166.png)

6.  Verify the information of the template and click **Next**.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9256449951/p35167.png)

7.  Select the required virtual disk format, select a storage to store files for the deployed template, and then click **Next**.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9256449951/p35168.png)

8.  Select the destination network for each source network and click **Next**.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/5051409951/p68314.jpg)

9.  Configure the required deployment properties for the software solution and click **Next**.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9256449951/p35170.png)

10. Verify the configurations and click **Finish**.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/0356449951/p35171.png)

11. View the progress of the deployment task in the Recent Tasks section.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6051409951/p68331.jpg)

12. After the deployment task is complete, start the VM on which the OVF or OVA template is deployed.

13. Open a browser, and enter `http://hostname:8011` in the address bar.

    **Note:** Replace `hostname` with the IP address of the VM on which the OVF or OVA template is deployed.

14. On the Register page, set the parameters and click **Register** to log on to the migration gateway. The following table describes the parameters.

    |Parameter|Description|
    |:--------|:----------|
    |AccessKey ID|The AccessKey ID and AccessKey secret of the Resource Access Management \(RAM\) user that is used to access HBR. You can obtain the AccessKey ID and AccessKey secret of a RAM user under your Alibaba Cloud account for which HBR is activated. For more information, see [Create an AccessKey for a RAM user](/intl.en-US/FAQ/Common issues/Create an AccessKey for a RAM user.md).|
    |AccessKey Secret|
    |Certificate|The certificate that is downloaded from the HBR console. If a VM is shut down for more than five days after you use the certificate to activate the client on the VM, the certificate expires. In this case, you must download a new certificate and reactivate the client.|

    After the client is activated, click **OK** to go to the HBR console.


## Step 3: Add a vCenter Server

1.  On the **Migration Gateways** tab, find the migration gateway, and click **View** in the Actions column.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6051409951/p68353.jpg)

2.  In the upper-right corner of the vCenter Servers page, click **Add vCenter Server**.

3.  In the **Add vCenter Server** pane, set the **Server IP Address**, **Username**, and **Password** parameters. Then, click **Create**.

    The addition of a vCenter Server may fail if the password contains the following special characters:

    \` ^ ~ = ; ! / \( \[ \] \{ \} @ $ \\ & \# % +

    **Note:** We recommend that you create a vCenter Server account that is dedicated for backup. The password of the account must include periods \(.\) and cannot include other special characters.


## Step 4: Migrate data from a VMware VM

1.  On the vCenter Servers page, find the vCenter Server, and click **Migrate** in the Actions column.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6051409951/p68364.jpg)

2.  In the **Configure Migration Plan** step, set the parameters and click **Next**.

    ![plan](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6051409951/p84834.jpg)

    |Parameter|Description|
    |---------|-----------|
    |**Plan Name**|The name of the migration plan. By default, a random name is used.|
    |**Configure Migration Plan**|The migration policy. Valid values: **Right Now** and **On Schedule**. If you select **On Schedule**, you must set the **Start Time** parameter. The time is accurate to seconds. |
    |**Force Quiesced Snapshot**|    -   If you select this check box, HBR uses quiesced snapshots to migrate data. If quiesced snapshots are unavailable, the backup fails.
    -   If you clear this check box, HBR attempts to use quiesced snapshots to migrate data. If quiesced snapshots are unavailable, HBR uses common snapshots to migrate data. By default, this check box is cleared. |
    |**Enable Incremental Sync**|Specifies whether to enable incremental synchronization. If you enable incremental synchronization, you must set the **Incremental Sync Frequency** parameter. Valid units: hours, days, and weeks.

**Note:**

    -   If Changed Block Tracking \(CBT\) is disabled for the VM, a full synchronization task is run instead of incremental synchronization.
    -   If incremental synchronization is enabled, HBR automatically creates an image to test whether workloads can be switched to the destination. You are charged by ECS for the image. For more information, see [Billing overview](/intl.en-US/Pricing/Billing items/Billing overview.md). |

3.  In the **Select VMs to Migrate** step, select the source VMs and click **Next**.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6051409951/p68369.jpg)

4.  In the **Configure ECS Instance** step, set the **VPC**, **Switch**, **Instance Type**, **Instance Family**, **Storage Type**, **Security Group**, **IP Address Type**, **Assign Public IP**, **Reboot After Restoration**, and **Create System Image**. Then, click **Apply to All VMs** or **Apply to Current VM**.

    **Note:** Make sure that the security group allows outbound data transfer over TCP port 80, TCP port 443, and UDP port 53.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6051409951/p68373.jpg)

5.  Click **Create** to start the migration job. On the Migration Plans tab, you can view the migration progress.

    ![syn](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6051409951/p84851.jpg)

    If incremental synchronization is enabled, you can perform the following operations after the migration is complete:

    -   Click **Sync Tasks** in the Actions column to view information such as the volume of incremental data that is migrated and the migration status.

        ![syn](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6051409951/p85372.jpg)

    -   Click **Create ECS Instance** in the Actions column. In the dialog box that appears, select **Verify Migration** or **Finish Migration**.

        ![verification](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6051409951/p85370.jpg)

        -   If you select **Verify Migration**, HBR creates an ECS instance and migrates data after the last migration \(for example, 20:21:31, February 21, 2020\) to the ECS instance. You can use the ECS instance to test whether workloads can be switched to the destination. You can perform a maximum of three migration verifications. During migration verifications, incremental synchronization is performed as planned. After you click **OK**, HBR creates an ECS instance. If you click **Resume Migration** in the Actions column, HBR deletes the ECS instance and resumes the migration.

            ![continue](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6051409951/p85373.png)

        -   If you select **Finish Migration**, HBR creates an ECS instance based on the migrated data \(for example, data migrated before 20:21:31 on February 21, 2020\). HBR also stops the migration job. If you select **Run an incremental synchronization task before finishing the migration job**, HBR migrates data that is generated after the last incremental synchronization to the created ECS instance.
        **Note:**

        -   If you select **Run an incremental synchronization task before finishing the migration job**, a longer time is required to finish the migration job.
        -   You are charged for the migration of the VM only the first time you verify the migration or finish the migration job. If you repeatedly perform verifications or if you finish the migration job after a verification, you are not charged. For more information, see [Pricing](https://www.alibabacloud.com/product/hybrid-backup-recovery/pricing).
    -   Click **Cancel** in the Actions column to cancel the running or pending migration job.

