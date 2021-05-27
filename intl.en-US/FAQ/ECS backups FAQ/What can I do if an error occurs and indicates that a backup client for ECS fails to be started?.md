# What can I do if an error occurs and indicates that a backup client for ECS fails to be started?

If a backup client fails to be started, the probable cause is that an antivirus application is installed on an ECS instance.

## Troubleshooting

Connect to the ECS instance and check whether an antivirus application is installed on the ECS instance. For more information, see [Connect to an ECS instance from a remote client](/intl.en-US/Instance/Connect to instances/Overview.md). If an antivirus application runs, the ECS client fails to be installed.

You can [uninstall the backup client from the ECS instance](/intl.en-US/FAQ/Common issues/How do I uninstall a backup client?.md), stop antivirus applications, and then reinstall the ECS client. You can perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup** \> **ECS File Client**.

3.  Find the ECS instance where the backup client failed to be installed. Choose **Operations** \> **Reinstall**.


