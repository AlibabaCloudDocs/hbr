# What should I do if an error occurs while starting the client fails?

## Description

When you install an ECS client, the Installation Failed status is displayed. An error message appears, indicating that you failed to start the client.

## Troubleshoot

[Connect to an ECS instance from a remote client](/intl.en-US/Instance/Connect to instances/Overview.md) and check whether anti-virus applications are installed on the ECS instance. Anti-virus software causes the installation failure of an ECS client.

## Solution

You can uninstall the ECS client from the ECS instance, stop anti-virus software, and then reinstall the ECS client. You can perform the following steps:

1.  [Uninstall an ECS client from an ECS instance](/intl.en-US/FAQ/Common issues/How do I uninstall a backup client?.md).
2.  Stop anti-virus software.
3.  Log on to the [Hybrid Backup Recovery console](https://hbr.console.aliyun.com).
4.  In the left-side navigation pane, choose **ECS Backup** \> **ECS File Client**.
5.  Locate the ECS instance where the ECS client failed to install. Choose **Operations** \> **Reinstall**.

