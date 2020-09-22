# Configure alert notifications

HBR sends alert notifications to the Alibaba Cloud account owner by default when backup fails or a backup client is disconnected from HBR. You can customize notification contacts, contact groups, and methods.

**Note:** A contact receives an alert about one hour after backup fails or a backup client is disconnected from HBR.

## Create a notification contact

A notification contact is a person who receives backup alerts. To create a notification contact, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, click **Notification Contacts**.

3.  On the Notification Contacts page, click the **Contacts** tab.

4.  In the upper-right corner, click **Create Contact**.

5.  In the Create Contact dialog box, enter a contact name.

6.  Select **Email** as Notification Methods.

    After you select Email, enter an email address in the **Email** field and click **Send**. Log on to the specified email address and copy the verification code. Then, paste the code in the Verification Code field in the HBR console.

7.  Click **OK**.

    **Note:**

    -   You can view the information of all created notification alerts on the Contacts tab.
    -   You can click **Modify** to change the email address of a notification contact.
    -   You cannot delete a notification contact if the contact is specified to receive alert notifications or added to a contact group.

## Create a contact group

You can create a contact group and add multiple notification contacts to the group. Then, you can enable the group to receive the same alert notifications. This simplifies the procedure to manage the notification contacts. When an alert is triggered, HBR sends alert notifications to all contacts in the group.

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, click **Notification Contacts**.

3.  On the Notification Contacts page, click the **Groups** tab.

4.  In the upper-right corner, click **Create Group**.

5.  In the Create Group pane, specify a group name.

6.  Select the contacts that you want to add to the group, and click the ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9281029951/p38146.png) button. Then, the selected contacts are added to the Selected Contacts section.

7.  Click **OK**.

    **Note:**

    -   You can view the information of all created contact groups and the number of member contacts in each group on the Groups tab.
    -   You can click **Modify** to modify a contact group.
    -   You cannot delete a contact group if the group is specified to receive alert notifications.

## Create alert policies

You can create the following types of alarm policies:

**Note:** By default, HBR sends alert notifications by using emails to the Alibaba Cloud account owner. If you use custom alert policies, an instance-level alert policy takes precedence over a vault-level alert policy.

-   Vault-level alert policy

    A vault-level alert policy applies to all the backup clients that are associated with the vault. The backup clients include those for ECS, on-premises files, and on-premises virtual machines \(VMs\).

    To configure an alert policy for a vault, perform the following steps:

    1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
    2.  On the Overview page, find the vault.
    3.  In the upper-right corner of the vault card, click the Settings icon.
    4.  In the Modify Backup Vault pane, select an alert policy based on your requirements.

        |Alert policy|Description|
        |:-----------|:----------|
        |Disabled|If you select this option, HBR does not send alert notifications.|
        |Default|If you select this option, HBR sends alert notifications to the Alibaba Cloud account owner by using emails.|
        |Custom|If you select this option, you must select one or more notification contacts or contact groups. HBR sends alert notifications to the selected contacts and contact groups.|

    5.  Click **OK**.
-   Instance-level alert policy

    An instance-level alert policy applies to the backup clients of an SQL Server instance.

    To configure an alert policy for an SQL Server instance, perform the following steps:

    1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
    2.  Find the backup client of the SQL Server instance. In the Actions column, choose **![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/4511470061/p60467.jpg)** \> **Alert Settings**.
    3.  In the Alert Settings pane, select an alert policy based on your requirements.

        |Alert policy|Description|
        |:-----------|:----------|
        |Disabled|If you select this option, HBR does not send alert notifications.|
        |Same as Vault|If you select this option, the alert policy of the backup vault where the backup data of the ECS instance is stored applies to the instance.|
        |Default|If you select this option, HBR sends alert notifications to the Alibaba Cloud account owner by using emails.|
        |Custom|If you select this option, you must select one or more notification contacts or contact groups. HBR sends alert notifications to the selected contacts and contact groups.|

    4.  Click **OK**.

