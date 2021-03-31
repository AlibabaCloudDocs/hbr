# Restore an ECS instance

When an ECS instance encounters a system failure or an error operation, you can roll back the instance by cloning or rolling back a backup point. This topic describes how to restore an ECS instance.

## Clone and roll back an ECS instance

When an ECS instance encounters a system failure or an error operation, you can roll back the instance by cloning or rolling back a backup point.

1.  On the **Protected ECS Instances** tab, find the ECS instance.

2.  Click the ![+](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3501817161/p259616.png) icon before the ECS instance.

3.  On the **ECS Backup History** tab, select a backup point.

    -   Clone an ECS instance by using a backup point in the instance backup history
        1.  Click a backup point. Click **Clone**.
        2.  On the Restore Backup Point to New ECS Instance page, configure the parameters such as hostname, instance name, VPC, and vSwitch.
        3.  Click **Create**.
    -   Roll back an ECS instance by using a backup point in the instance backup history

        **Note:** An ECS instance can be rolled back only if the ECS instance is stopped and no snapshot is being created for the ECS instance. The data that is written to the protected ECS instance is removed when the ECS instance is rolled back. Proceed with caution.

        1.  Click a backup point. Click **Roll Back**.
        2.  In the message that appears, click **OK**.

