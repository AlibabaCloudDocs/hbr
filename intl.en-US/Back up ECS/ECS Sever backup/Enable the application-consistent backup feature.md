# Enable the application-consistent backup feature

Hybrid Backup Recovery \(HBR\) works with Cloud Assistant and the snapshot service to provide the application-consistent backup feature. Application-consistent backups can be used for rollbacks to avoid log rollbacks when applications such as databases start. This ensures that the applications start in a consistent state.

-   The instance allows access from the Internet. A public IP address is configured or an elastic IP address \(EIP\) is associated.
-   The instance runs one of the following operating systems:
    -   Windows: Windows Server 2019, Windows Server 2016, and Windows Server 2012.
    -   Linux: CentOS 7.6 or later, Ubuntu 18.04 or later, and Alibaba Cloud Linux 2 \(2.1903 LTS 64-bit\).
-   The disks of the instance are enhanced SSDs \(ESSDs\) and the file system is EXT3, EXT4, XFS, or NTFS.
-   The application-consistent backup feature is supported in the US \(Virginia\), Singapore \(Singapore\), and China \(Hong Kong\) regions.

By default, backups created in HBR in combination with the snapshot service are crash-consistent. If you enable the application-consistent backup feature when you create a disk backup, the system creates an application-consistent backup based on your requirements.

The application-consistent backup feature can back up the data in memory and the database transactions in progress when the backups are created. This ensures consistency of the application data and database transactions. When application-consistent backups are used for rollbacks, no data corruption or loss occurs, logs are not rolled back when databases start, and applications start in a consistent state.

## Procedure

1.  [Step 1: Configure a RAM role for the ECS instance](#section_qez_tzh_rwa)

    Before you enable the application-consistent backup feature, you must configure a RAM role for the ECS instance.

2.  [Step 2: Enable the application-consistent backup feature](#section_kqu_a40_ztc)

    For Windows ECS instances, you can use Volume Shadow Copy Service \(VSS\) to implement application consistency.

    For Linux ECS instances, you must configure shell scripts \(application pre-freeze and post-thaw scripts\) based on the applications in the instance to implement application consistency.


## Step 1: Configure a RAM role for the ECS instance

1.  Log on to the [RAM console](https://ram.console.aliyun.com/) by using your Alibaba Cloud account.

2.  Create a RAM role for the application-consistent backup feature. For more information about how to create a RAM role, see [Create a RAM role for a trusted Alibaba Cloud service](/intl.en-US/RAM Role Management/Create a RAM role/Create a RAM role for a trusted Alibaba Cloud service.md).

    The following figure shows how to create the AppSnapshotRoleName RAM role.

    ![RAM role for the application-consistent backup feature](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6800666161/p250036.png)

3.  Create a policy for the application-consistent backup feature. For more information about how to create a policy, see [Create a custom policy](/intl.en-US/Policy Management/Custom policies/Create a custom policy.md).

    ![Snapshot policy](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6800666161/p249921.png)

    Create the AppSnapshotPolicy policy to grant the permissions to query snapshot details, create snapshots, configure tags, and then query disk details. You can use the following policy:

    ```
    {
        "Version": "1",
        "Statement": [
            {
                "Effect": "Allow",
                "Action": [
                    "ecs:DescribeSnapshot*",
                    "ecs:CreateSnapshot*",
                    "ecs:TagResources",
                    "ecs:DescribeDisks"
                ],
                "Resource": [
                    "*"
                ],
                "Condition": {}
            }
        ]
    }
    ```

4.  Attach the AppSnapshotPolicy policy to the AppSnapshotRoleName RAM role. For more information about how to attach a policy to a RAM role, see [Grant permissions to a RAM role](/intl.en-US/RAM Role Management/Grant permissions to a RAM role.md).

    ![Grant permissions](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6800666161/p250505.png)

5.  Attach the AppSnapshotRoleName RAM role to the ECS instance. For more information about how to attach a RAM role to an ECS instance, see [Bind an instance RAM role](/intl.en-US/Security/Instance RAM roles/Bind an instance RAM role.md).


## Step 2: Enable the application-consistent backup feature

-   Enable the application-consistent backup feature for a Windows ECS instance
    1.  Log on to the [HBR console](https://hbr.console.aliyun.com/).
    2.  Select a protected ECS instance. Select **Add ECS instances** .
    3.  On the **Create ECS Protection Plan** page, select **Enable Application-consistent Backup**, an application-consistent backup is created.

        **Note:** If the Cloud Assistant client is not installed on your instance, the client is automatically installed when the backup is created after you select **Enable Application-consistent Backup**.

    4.  Click **OK**.
-   Enable the application-consistent backup feature for a Linux ECS instance
    1.  Write the application pre-freeze and post-thaw scripts based on the applications in the instance and upload the scripts to the instance.

        You can use the FTP service or Cloud Assistant to upload the application pre-freeze and post-thaw scripts to the instance.

        -   Application pre-freeze script: Configure the script to allow only the root user to have the read, write, and execute permissions on the script. Set the save path to /tmp/prescript.sh.
        -   Application post-thaw script: Configure the script to allow only the root user to have the read, write, and execute permissions on the script. Set the save path to /tmp/postscript.sh.
        **Note:** If the script configurations such as permissions, save path, or file name are invalid, a file-system consistent backup is created.

        You can reference the following application-consistent scripts:

        -   Click [here](https://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/206129/cn_zh/1618215539272/Linux-MySQL-Scripts.tar.gz) to download the MySQL application-consistent script.

            After you download and deploy the script, you must set the password of a MySQL database in the script.

        -   Click [here](https://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/206129/cn_zh/1618215573447/Linux-Oracle-Scripts.tar.gz) to download the Oracle application-consistent script.

            After you download and deploy the script, you must set the path to install an Oracle database in the script.

    2.  Log on to the [HBR console](https://hbr.console.aliyun.com/).
    3.  Select a protected ECS instance. Select **Protect Now**.
    4.  On the **Edit Plan** page, configure application-consistency backup parameters.

        -   If you select **Enable Application-consistent Backup** and **Enable File System Freeze and Thaw** and configure valid scripts, an application-consistent backup is created.
        -   If you select **Enable Application-consistent Backup** and **Enable File System Freeze and Thaw** but do not configure valid scripts, a file-system consistent backup is created.
        **Note:** If the Cloud Assistant client is not installed on your instance, the client is automatically installed when the backup is created after you select **Enable Application-consistent Backup**.

    5.  Click **OK**.

