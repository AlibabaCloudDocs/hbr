# Backup alerts {#concept_t5n_5nm_qfb .concept}

Backup alerts provide you with alerts, such as when a backup fails or when a client is disconnected from a server. You can also configure contacts, contact groups, and contact methods.

**Note:** One hour after a backup fails or a client is disconnected from a server, the specified contact will receive an alert.

## Create an alarm contact {#section_w5p_14m_qfb .section}

An alarm contact is a person that is selected to receive backup alerts. You can create an alarm contact as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, select **Alarm Contact**.
3.  On the Alarm Contact Management page, select the Alarm Contact tab.
4.  Click **New Contact** in the upper-right corner.
5.  In the New Contact dialog box, enter the Contact Name.
6.  Select a Contact Method as required, and then perform the following steps.
    -   **Email**

        If you select Email as a contact method, enter the **Contact Email**, and then click **Send Verification**. Log on to the specified email to view the verification code, go to the HBR console, and enter the verification code in the Email Verification field.

    -   **Mobile**

        If you select Mobile as a contact method, enter the **Mobile**, and then click **Send Verification**. An SMS message that contains a verification code is sent to your mobile phone. Enter the verification code in the Mobile Verification Code field.

7.  Click **OK**.

**Note:** 

-   On the Alarm Contact tab, you can view a list of all contacts and the details of each contact.
-   You can click **Edit** to modify the email and mobile number.
-   You cannot delete a contact that is selected to receive alerts or added to a contact group.

## Create an alarm contact group {#section_yff_jqm_4gb .section}

If you need multiple contacts to receive alerts, you can create an alarm contact group and add these contacts to the contact group to facilitate management. When an alert occurs, all contacts that are included in a contact group will receive an alert.

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, select **Alarm Contact**.
3.  On the Alarm Contact Management page, select the Alarm Contact Group tab.
4.  In the upper-right corner, click **New Contact Group**.
5.  In the New Contact Group dialog box, enter the Group Name.
6.  Select one or more contacts to add to the group, and click the ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40788/156465347038146_en-US.png) icon. These contacts are displayed in the Select Contacts section.
7.  Click **OK**.

    **Note:** 

    -   On the Alarm Contact Group tab, you can view a list of contact groups and the number of contacts in each group.
    -   You can click **Edit** to modify a contact group.
    -   You cannot delete a contact group that is selected to receive alerts.

## Create custom alarm policies {#section_anq_zrs_qfb .section}

You can create the following types of alarm policies:

-   Vault-level alarm policies

    A vault-level alarm policy applies to all the backup clients of a vault. The backup clients include those installed on ECS instances, local hosts, and local virtual machines. If you create an alarm policy for the vault where a client is located, the alarm policy of the vault applies to the client by default.

-   Client-level alarm policies

    A client-level alarm policy applies to the backup client installed on a specific host. After you create an alarm policy for a client, the client no longer uses the alarm policy of the vault or the default alarm policy.


**Note:** If you create no alarm policy for a vault or a client, alerts are sent to an Alibaba Cloud account by using emails.

**Create a vault-level alarm policy**

Proceed as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  On the Overview page, locate the required vault to create an alarm policy.
3.  In the upper-right corner of a vault, click Settings.
4.  In the Vault Setting dialog box, select an Alarm Policy as required.
    -   **Disabled**

        If you select this option, no alert is sent when an alarm occurs on a client or ECS instance that is located in the vault.

    -   **Default Notification**

        If you select this option, alerts for the vault are sent to an Alibaba Cloud account by using emails.

    -   **Customized Notification**

        If you select this option, you can select one or more contacts and contact groups. After you complete the configuration, alerts for the vault are sent to the selected contacts or contact groups.

5.  Click **OK**.

**Create an alarm policy for a client**

Proceed as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  Locate a client to create an alarm policy, choose **More** \> **Alarm Setting** next to the client.
3.  In the Alarm Policy dialog box, select the required Alarm Policy.

    |Alarm Policy|Description|
    |:-----------|:----------|
    |Disabled|If you select this option, no alert is sent when an alarm occurs on the client.|
    |Same as Vault|The alarm policy of the vault where the client is located applies to the client.|
    |Default Notification|Alerts for the client are sent to an Alibaba Cloud account by using emails.|
    |Customized Notification|You can select one or more contacts and contact groups. After you complete the configuration, alerts for the client are sent to the selected alarm contacts or alarm contact groups.|

4.  Click **OK**.

