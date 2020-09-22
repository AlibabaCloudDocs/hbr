# Configure alert notifications

HBR sends alert notifications to the Alibaba Cloud account owner by default when backup fails or a backup client is disconnected from HBR. You can customize notification contacts, contact groups, and methods.

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

## Create an alarm contact group

If you need multiple alert contacts to receive alert notifications, you can add an alert contact group and add alert contacts to the group so that you can manage them more conveniently. When an alert is generated, HBR sends an alert notification to all alert contacts in the specified alert contact group.

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, select **Alarm Contact**.
3.  On the Alarm Contact Management page, select the Alarm Contact Group tab.
4.  In the upper-right corner, click **New Contact Group**.
5.  In the New Contact Group dialog box, enter the Group Name.
6.  Select one or more contacts, and click the ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9281029951/p38146.png) icon to add the contact to the group. These contacts are displayed in the Selected Contacts area.
7.  Click **OK**.

    **Note:**

    -   On the Alarm Contact Group tab, you can view a list of all contact groups and the number of contacts in each group.
    -   You can click **Edit** to modify a contact group.
    -   You cannot delete a contact group that is selected to receive alerts.

## Create alert policies

You can create the following types of alarm policies:

**Note:** By default, HBR sends alert notifications by using emails to the Alibaba Cloud account owner. If you use custom alert policies, a gateway-level alert policy takes precedence over a vault-level alert policy.

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
-   Gateway-level alert policy

    A gateway-level alert policy applies to the backup client of a gateway.

    To configure an alert policy for a gateway, perform the following steps:

    1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
    2.  In the left-side navigation pane, click **CSG Backup**.
    3.  On the CSG Backup page, click the **Storage Gateways** tab.
    4.  Find the gateway and choose **![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6062470061/p61198.jpg)** \> **Alert Settings**.
    5.  In the Alert Policy pane, select an alert policy based on your requirements.

        |Alert policy|Description|
        |:-----------|:----------|
        |Disabled|If you select this option, HBR does not send alert notifications.|
        |Same as Vault|If you select this option, the alert policy of the backup vault where the backup data of the storage gateway is stored applies to the storage gateway.|
        |Default|If you select this option, HBR sends alert notifications to the Alibaba Cloud account owner by using emails.|
        |Custom|If you select this option, you must select one or more notification contacts or contact groups. HBR sends alert notifications to the selected contacts and contact groups.|

    6.  Click **OK**.

