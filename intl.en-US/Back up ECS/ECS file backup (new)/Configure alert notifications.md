# Configure alert notifications

This topic describes how to configure alert notifications. If a backup attempt fails or a backup client is disconnected from the server, Hybrid Backup Recovery \(HBR\) sends alert notifications to the owner of the Alibaba Cloud account by default. You can customize notification contacts, contact groups, and methods.

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

6.  Select the contacts that you want to add to the group and click the ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9281029951/p38146.png) button. Then, the selected contacts are added to the Selected Contacts section.

7.  Click **OK**.

    **Note:**

    -   You can view the information of all created contact groups and the number of member contacts in each group on the Groups tab.
    -   You can click **Modify** to modify a contact group.
    -   You cannot delete a contact group if the group is specified to receive alert notifications.

## Create alert policies

You can create the following types of alarm policies:

**Note:** By default, HBR sends alert notifications by using emails to the Alibaba Cloud account owner.

-   Vault-level alert policy

    A vault-level alert policy applies to all the backup clients that are associated with the vault. The backup clients include those for ECS, on-premises files, and on-premises virtual machines \(VMs\). If no client-level alert policies are created, a vault-level alert policy is applied after it is created. To configure an alert policy for a vault, perform the following steps:

    1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
    2.  On theOverview page, find the vault.
    3.  In the upper-right corner of the vault card, click the Settings icon.
    4.  In the Modify Backup Vault pane, select an alert policy based on your requirements.

        |Alert policy|Description|
        |------------|-----------|
        |Disabled|If you select this option, HBR does not send alert notifications.|
        |Default|If you select this option, HBR sends alert notifications to the Alibaba Cloud account owner by using emails.|
        |Custom|If you select this option, you must select one or more notification contacts or contact groups. HBR sends alert notifications to the selected contacts and contact groups.|

    5.  Click **OK**.
-   Client-level alert policy

    A client-level alert policy applies to a specific backup client. After you create an alert policy for a backup client, the vault-level alert policy no longer applies to the client. To configure an alert policy for a backup client, perform the following steps:

    1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
    2.  Find the client, and choose **More** \> **Alert Settings** in the Actions column.
    3.  In the Alert Settings pane, select an alert policy based on your requirements.

        |Alert policy|Description|
        |:-----------|:----------|
        |Disabled|If you select this option, HBR does not send alert notifications.|
        |Same as Vault|If you select this option, the alert policy of the backup vault applies to the instance.|
        |Default|If you select this option, HBR sends alert notifications to the Alibaba Cloud account owner by using emails.|
        |Custom|If you select this option, you must select one or more notification contacts or contact groups. HBR sends alert notifications to the selected contacts and contact groups.|

    4.  Click **OK**.

