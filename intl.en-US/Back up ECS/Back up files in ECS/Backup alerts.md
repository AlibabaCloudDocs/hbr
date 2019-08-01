# Backup alerts {#concept_t5n_5nm_qfb .concept}

Backup alerts provide you with alerts, such as when a backup fails or a client is disconnected from a server. By default, alerts are sent to an Alibaba Cloud account. You can also configure contacts, contact groups, and contact methods.

**Note:** One hour after a backup fails or a client is disconnected from a server, the specified contact will receive an alert.

## Create an alarm contact {#section_w5p_14m_qfb .section}

An alarm contact is a person that is assigned to receive backup alerts. You can create an alarm contact as follows:

1.  Log on to the [Hybrid Backup Recovery \(HBR\) console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, select **Alarm Contact**.
3.  On the Alarm Contact Management page, select the Alarm Contact tab.
4.  Click **New Contact** in the upper-right corner.
5.  In the New Contact dialog box, enter the Contact Name.
6.  Select a Contact Method, and then perform the following steps.
    -   **Email**

        If you select Email as a contact method, enter the **Contact Email**, and then click **Send Verification**. Log on to the specified email to view the verification code, go back to the HBR console, and enter the verification code in the Email Verification field.

    -   **Mobile**

        If you select Mobile as a contact method, enter the **Mobile** and then click**Send Verification**. An SMS message that contains a verification code will be sent to your mobile phone. Enter the verification code in the Mobile Verification Code field.

7.  Click **OK**.

**Note:** 

-   On the Alarm Contact tab, you can view a list of all contacts and the related information of each contact.
-   You can click **Edit** to modify the email and mobile number.
-   You cannot delete a contact that is selected to receive alerts or added to a contact group.

## Create an alarm contact group {#section_yff_jqm_4gb .section}

If you need multiple contacts to receive alerts, you can create an alarm contact group and add these contacts to the contact group to facilitate management. When an alert occurs, all contacts that are included in a contact group will receive an alert.

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, select **Alarm Contact**.
3.  On the Alarm Contact Management page, select the Alarm Contact Group tab.
4.  In the upper-right corner, click **New Contact Group**.
5.  In the New Contact Group dialog box, enter the Group Name.
6.  Select one or more contacts, and click the ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40788/156465313338146_en-US.png) icon to add the contact to the group. These contacts are displayed in the Selected Contacts area.
7.  Click **OK**.

    **Note:** 

    -   On the Alarm Contact Group tab, you can view a list of all contact groups and the number of contacts in each group.
    -   You can click **Edit** to modify a contact group.
    -   You cannot delete a contact group that is selected to receive alerts.

## Create custom alarm policies {#section_anq_zrs_qfb .section}

You can create the following types of alarm policies:

**Note:** By default, alert SMS messages or emails are sent to an Alibaba Cloud account. If you create custom alarm policies, instance-level alarm policies are prioritized over vault-level alarm policies.

-   **Vault-level alarm policies**

    A vault-level alarm policy applies to all the backup clients of a vault. The backup clients include those installed on ECS instances, local hosts, and local virtual machines.

-   **Instance-level alarm policies**

    An instance-level alarm policy applies to the backup client installed on a specific instance.


**Create a vault-level alarm policy**

Proceed as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  On the Overview page, locate the vault for which you need to create an alarm policy.
3.  In the upper-right corner of a vault card, click Settings.
4.  On the Vault Setting page, select an Alarm Policy as required.
    -   **Disabled**

        After you select this option, no alert is sent when an alarm occurs on a backup client or instance that is related to the vault.

    -   **Default Notification**

        After you select this option, alerts for the vault are sent to an Alibaba Cloud account by using SMS messages and emails.

    -   **Customized Notification**

        After you select this option, you can select one or more contacts, and contact groups. After you complete the configuration, alert for the vault are sent to the selected contacts or contact groups.

5.  Click **OK**.

**Create an instance-level alarm policy for an ECS instance**

Proceed as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  Locate an ECS instance for which you need to create an alarm policy. In the Actions column of the ECS instance, click the More icon and select **Alarm Setting**.
3.  In the Alarm Setting dialog box, select an Alarm Policy.

    |Alarm Policy|Description|
    |:-----------|:----------|
    |Disabled|If you select this option, no alert is sent when an alarm occurs on the instance.|
    |Same as Vault|If you select this option, the alarm policy of the vault where the ECS instance is located applies to the instance.|
    |Default Notification|If you select this option, alerts for the instance are sent to an Alibaba Cloud account by using SMS messages and emails.|
    |Customized Notification|You can select one or more contacts and contact groups. After you complete the configuration, alerts for the instance are set to the selected contacts or contact groups.|

4.  Click **OK**.

