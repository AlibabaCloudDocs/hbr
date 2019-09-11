# Configure the backup alerting feature {#concept_t5n_5nm_qfb .concept}

You can enable the backup alerting feature. If a backup fails or a client is disconnected from a server, Hybrid Backup Recovery \(HBR\) sends an alert notification to the alert contact specified in your Alibaba Cloud account by default. You can also customize alert policies and alert contacts or alert contact groups that receive alert notifications.

**Note:** About one hour after a backup fails or a client is disconnected from a server, the specified alert contact or alert contact group can receive an alert notification.

## Configure alert contacts {#section_w5p_14m_qfb .section}

An alert contact is a person who is assigned to receive backup alerts. You can add an alert contact in the HBR console. The procedure is as follows:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, click **Alarm Contact**.
3.  On the Alarm Contact Management page, click the Alarm Contact tab.
4.  Click **New Contact** in the upper-right corner.
5.  In the New Contact dialog box, set Contact Name.
6.  Set Contact Method as required, and then perform the following operations:
    -   **Email** 

        If you select Email as a contact method, enter an email address in the **Contact Email** field, and click **Send Verification**. Log on to the specified email address to view the verification code, go back to the HBR console, and then enter the verification code in the Email Verification field.

    -   **Mobile** 

        If you select Mobile as a contact method, enter a mobile number in the **Mobile** field, and click **Send Verification**. An SMS message that contains a verification code is sent to your mobile phone. Enter the verification code in the Mobile Verification Code field.

7.  Click **OK**.

**Note:** 

-   On the Alarm Contact tab, you can view a list of all alert contacts and their contact information.
-   You can click **Edit** to modify the email address and mobile number of an alert contact.
-   You cannot delete an alert contact who is specified to receive alert notifications or added to an alert contact group.

## Configure alert contact groups {#section_yff_jqm_4gb .section}

If you need multiple alert contacts to receive alert notifications, you can add an alert contact group and add alert contacts to the group so that you can manage them more conveniently. When an alert is generated, HBR sends an alert notification to all alert contacts in the specified alert contact group.

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
2.  In the left-side navigation pane, click **Alarm Contact**.
3.  On the Alarm Contact Management page, click the Alarm Contact Group tab.
4.  Click **New Contact Group** in the upper-right corner.
5.  In the New Contact Group dialog box, set Group Name.
6.  Select one or more alert contacts, and click ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40788/156818814538146_en-US.png). These alert contacts are displayed in the Selected Contact section.
7.  Click **OK**.

    **Note:** 

    -   On the Alarm Contact Group tab, you can view a list of all alert contact groups and the number of alert contacts in each group.
    -   You can click **Edit** to modify an alert contact group.
    -   You cannot delete an alert contact group that is specified to receive alert notifications.

## Customize alert policies {#section_anq_zrs_qfb .section}

You can customize the following types of alert policies:

**Note:** By default, HBR sends alert notifications by SMS or email to the alert contact specified in your Alibaba Cloud account. If you customize alert policies, the instance-level alert policy takes precedence over the vault-level alert policy.

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

            If you select this option, HBR sends alert notifications by SMS or email to the alert contact specified in your Alibaba Cloud account when backup alerts are generated for the vault.

        -   **Customized Notification** 

            If you select this option, you can specify one or more alert contacts or alert contact groups. Then, HBR sends alert notifications to the specified alert contacts or alert contact groups when backup alerts are generated for the vault.

    5.  Click **OK**.
-   Instance-level alert policy

    An instance-level alert policy applies to all ECS backup clients of an SAP HANA instance.

    Set an instance-level alert policy as follows:

    1.  Log on to the [HBR console](https://hbr.console.aliyun.com).
    2.  Find the SAP HANA instance for which you need to set an alert policy. In the right-side Actions column, click **Alarm Setting** for the instance.
    3.  In the Alarm Policy dialog box, set Alarm Policy as required.

        |Alarm policy|Description|
        |:-----------|:----------|
        |Disabled|If you select this option, HBR does not send an alert notification when an alert is generated for the SAP HANA instance.|
        |Same as Vault|If you select this option, the alert policy of the vault where the SAP HANA instance is located applies to the instance.|
        |Default Notification|If you select this option, HBR sends alert notifications by SMS or email to the alert contact specified in your Alibaba Cloud account when backup alerts are generated for the SAP HANA instance.|
        |Customized Notification|If you select this option, you can specify one or more alert contacts or alert contact groups. Then, HBR sends alert notifications to the specified alert contacts or alert contact groups when backup alerts are generated for the SAP HANA instance.|

    4.  Click **OK**.

