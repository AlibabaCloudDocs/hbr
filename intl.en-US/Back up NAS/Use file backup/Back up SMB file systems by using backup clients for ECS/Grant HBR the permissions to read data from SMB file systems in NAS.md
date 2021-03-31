# Grant HBR the permissions to read data from SMB file systems in NAS

Hybrid Backup Recovery \(HBR\) does not have the permissions to read data from a Server Message Block \(SMB\) file system. This file system is based on Active Directory \(AD\) permission control. Therefore, HBR cannot be used to back up the data of SMB file systems. To back up the data of SMB file systems, you first must grant HBR the permissions to read data from the SMB file systems. This topic describes how to grant HBR the permissions to read data from SMB file systems on a Windows-based Elastic Compute Service \(ECS\) instance.

-   You cannot use HBR to back up the data of an SMB file system that is based on AD permission control. HBR has no permissions to read data from the file systems. To fix this issue, we recommend that you mount the SMB file system to a Windows-based ECS instance. Then, you can authorize HBR to access the SMB file system.
-   Before you start the following procedure, you must install a file backup client for ECS. For more information about the billing of the backup client, see [Hybrid Backup Recovery \(HBR\) Pricing](https://cn.aliyun.com/price/detail/hbr).

## Step 1: Install a file backup client for ECS

Install a file backup client for ECS. For more information, see [Install a backup client for ECS](t789612.dita#concept_977495/section_wj8_7oh_c66).

## Step 2: Grant permissions to the HBR client

Perform the following steps to grant the HBR client the permissions to read files from the SMB file system.

1.  Connect to the ECS instance. For more information, see [Connect to an ECS instance](/intl.en-US/Instance/Connect to instances/Overview.md).

2.  Press `Win+R`. In the **Run** dialog box, enter `services.msc` and click **OK**.

    ![serice.msc](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6526517161/p259151.png)

3.  Find Aliyun Hybrid Backup Service in the service list. Right-click the service and select **Properties**.

    ![properties](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6526517161/p259146.png)

4.  In the dialog box that appears, click the **Log On** tab.

5.  Select **This account**, click browse, and then enter the account and password to gain full access to the SMB system. Click **OK**.

    ![account](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6526517161/p259150.png)

6.  Restart Aliyun Hybrid Backup Service.

    ![restart](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6526517161/p259149.png)


## Step 3: Create a backup plan

Create a backup plan. For more information, see [Create a backup plan](t789612.dita#concept_977495/section_kmh_tmi_ee4).

