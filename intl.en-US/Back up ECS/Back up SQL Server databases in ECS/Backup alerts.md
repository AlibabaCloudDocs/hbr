# Backup alerts

Backup alerts provide you with alerts, such as when a backup fails or a client is disconnected from a server. By default, alerts are sent to an Alibaba Cloud account. You can also configure contacts, contact groups, and contact methods.

**Note:** One hour after a backup fails or a client is disconnected from a server, the specified contact will receive an alert.

## Configure alert contacts

An alert contact is a person who is assigned to receive backup alerts. You can add an alert contact in the HBR console. The procedure is as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, click **Alarm Contact**.
3.  On the Alarm Contact Management page, click the Alarm Contact tab.
4.  Click **New Contact** in the upper-right corner.
5.  In the New Contact dialog box, set Contact Name.
6.  Select **Email** as a Contact Method.

    Enter the **Contact Email**, and then click **Send Verification**. Log on to the specified email to view the verification code, go back to the HBR console, and enter the verification code in the Email Verification field.

7.  Click **OK**.

**Note:**

-   On the Alarm Contact tab, you can view a list of all alert contacts and their contact information.
-   You can click **Edit** to modify the email address of an alert contact.
-   You cannot delete an alert contact who is specified to receive alert notifications or added to an alert contact group.

## Configure alert contact groups

If you need multiple alert contacts to receive alert notifications, you can add an alert contact group and add alert contacts to the group so that you can manage them more conveniently. When an alert is generated, HBR sends an alert notification to all alert contacts in the specified alert contact group.

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, click **Alarm Contact**.
3.  On the Alarm Contact Management page, click the Alarm Contact Group tab.
4.  Click **New Contact Group** in the upper-right corner.
5.  In the New Contact Group dialog box, set Group Name.
6.  Select one or more alert contacts, and click ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9281029951/p38146.png). These alert contacts are displayed in the Selected Contacts section.
7.  Click **OK**.

    **Note:**

    -   On the Alarm Contact Group tab, you can view a list of all alert contact groups and the number of alert contacts in each group.
    -   You can click **Edit** to modify an alert contact group.
    -   You cannot delete an alert contact group that is specified to receive alert notifications.

## Customize alert policies

You can customize the following types of alert policies:

**Note:** By default, HBR sends alert notifications by email to the alert contact specified in your Alibaba Cloud account. If you customize alert policies, the instance-level alert policy takes precedence over the vault-level alert policy.

-   Vault-level alert policy

    A vault-level alert policy applies to all the backup clients of a vault. The backup clients include those installed on Alibaba Cloud Elastic Compute Service \(ECS\) instances, local hosts, and local virtual machines.

    Set a vault-level alert policy as follows:

    1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
    2.  On the Overview page, find the vault for which you need to set an alert policy.
    3.  In the upper-right corner of a vault card, click the Settings icon.
    4.  In the Vault Setting dialog box, set Alarm Policy as required.
        -   **Disabled**

            If you select this option, HBR does not send an alert notification when an alert is generated for a backup client or an instance that is related to the vault.

        -   **Default Notification**

            If you select this option, HBR sends alert notifications by email to the alert contact specified in your Alibaba Cloud account when backup alerts are generated for the vault.

        -   **Customized Notification**

            If you select this option, you can specify one or more alert contacts or alert contact groups. Then, HBR sends alert notifications to the specified alert contacts or alert contact groups when backup alerts are generated for the vault.

    5.  Click **OK**.
-   Instance-level alert policy

    An instance-level alert policy applies to all ECS backup clients of an SQL Server instance.

    Set an instance-level alert policy as follows:

    1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
    2.  Find the SQL Server instance for which you need to set an alert policy. In the right-side Actions column, click **Alarm Setting** for the instance.
    3.  In the Alarm Policy dialog box, set Alarm Policy as required.

        |Alarm policy|Description|
        |:-----------|:----------|
        |Disabled|If you select this option, HBR does not send an alert notification when an alert is generated for the SQL Server instance.|
        |Same as Vault|If you select this option, the alert policy of the vault where the SQL Server instance is located applies to the instance.|
        |Default Notification|If you select this option, HBR sends alert notifications by email to the alert contact specified in your Alibaba Cloud account when backup alerts are generated for the SQL Server instance.|
        |Customized Notification|If you select this option, you can specify one or more alert contacts or alert contact groups. Then, HBR sends alert notifications to the specified alert contacts or alert contact groups when backup alerts are generated for the SQL Server instance.|

    4.  Click **OK**.

