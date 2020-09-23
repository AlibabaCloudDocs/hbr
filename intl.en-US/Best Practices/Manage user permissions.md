# Manage user permissions

Resource Access Management \(RAM\) is an Alibaba Cloud service that helps you manage user identities and access to your cloud resources. You can create RAM users and manage their permissions to reduce risks to your Alibaba Cloud account.

## Background information

You can create and manage multiple RAM users under an Alibaba Cloud account. You can also grant different permissions to each RAM user. This allows each RAM user to have different access permissions on Alibaba Cloud resources. By using RAM, you do not need to share AccessKey pairs with other users. You can assign minimal permissions to each RAM user to reduce data security risks for your enterprise. For more information, see [What is RAM?](/intl.en-US/Product Introduction/What is RAM?.md) and [Policy overview](/intl.en-US/Policy Management/Policy overview.md).

To manage user permissions by using RAM, you must create RAM users or groups. Then, you need to grant different permissions to each RAM user or group.

## Create a RAM user

To create a RAM user, perform the following steps:

1.  Log on to the [RAM console](https://ram.console.aliyun.com/) with an Alibaba Cloud account.

2.  In the left-side navigation pane, click **Users** under **Identities**.

3.  On the Users page, click **Create User**.

    **Note:** You can click **Add User** to create multiple RAM users at a time.

4.  Set the **Logon Name** and **Display Name** parameters.

5.  In the **Access Mode** section, select **Console Password Logon** or **Programmatic Access**.

    -   **Console Password Logon**: If you select this access mode, you must complete the logon security settings. These settings specify whether to use a system-generated or custom logon password, whether the password must be reset on the next logon, and whether to enable multi-factor authentication \(MFA\).
    -   **Programmatic Access**: If you select this access mode, an AccessKey pair is automatically created for the RAM user. The RAM user can call API operations or use development tools to access Alibaba Cloud resources.
    **Note:** To ensure the security of your Alibaba Cloud account, we recommend that you select only one access mode for the RAM user. This prevents the RAM user from using an AccessKey pair to access Alibaba Cloud resources after the RAM user leaves the organization.

6.  Click **OK**.


## Create a user group

If you have multiple RAM users under your Alibaba Cloud account, you can create RAM user groups to classify and authorize these RAM users. This simplifies the management of RAM users and permissions.

1.  Log on to the [RAM console](https://ram.console.aliyun.com/) with an Alibaba Cloud account.

2.  In the left-side navigation pane, click **Groups** under **Identities**.

3.  On the Groups page, click **Create Group**.

4.  In the Create Group pane, specify the **Group Name**, **Display Name**, and **Note** parameters.

5.  Click **OK**.

6.  Click **Close**.


## Grant permissions to a RAM user or group

By default, a RAM user or group has no permissions. You must grant permissions to a RAM user or group before the RAM user or group can be used to perform operations in the console or call API operations.

RAM provides two system policies for Hybrid Backup Recovery \(HBR\):

-   AliyunHbrFullAccess: grants a RAM identity the full access permissions on HBR.
-   AliyunHbrReadOnlyAccess: grants a RAM identity the read-only permissions on HBR.

You can authorize a RAM user or group by attaching the policies to the RAM user or group in the RAM console. To attach a policy to a RAM user or group, perform the following steps:

1.  Log on to the [RAM console](https://ram.console.aliyun.com/) with an Alibaba Cloud account.

2.  In the left-side navigation pane, click **Grants** under **Permissions**.

3.  Click **Grant Permission**.

4.  In the **Principal** field, enter the name of the RAM user or group, and then select the RAM user or group from the auto-complete results.

    **Note:** Fuzzy match is supported for RAM users, user groups, or roles.

5.  In the **Policy Name** column, select the policies that you want to attach to the RAM user or group. In this example, the AliyunHbrFullAccess and AliyunHbrReadOnlyAccess policies are selected.

    ![](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/8355580061/p53982.jpg)

    **Note:** In the Selected section, you can click the cross sign \(**×**\) next to a policy to remove the policy.

6.  Click **OK**.

7.  Click **Complete**.


**Note:** In addition to the system policies, you can also [create custom policies](/intl.en-US/Policy Management/Custom policies/Create a custom policy.md).

