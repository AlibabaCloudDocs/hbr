# User permissions {#concept_64817_zh .concept}

Resource Access Management \(RAM\) enables you to manage user access to Alibaba Cloud resources. You can reduce risks to your Alibaba Cloud accounts by creating RAM users and managing their permissions.

You can create and manage multiple RAM users with a single Alibaba Cloud account. You can grant different permissions for each RAM user. This allows each RAM user to have different access permissions on Alibaba Cloud resources. With RAM, you do not need to share an AccessKey with another account. You can assign minimal permissions to each user to reduce as many data security risks for your enterprise as possible. For more information, see [What is Resource Access Management?](../../../../intl.en-US/Product Introduction/What is RAM?.md) and [Permissions and authorization policies](../../../../intl.en-US/User Guide/(Old Version) User Guide/Authorization management/Policy overview.md).

To use RAM to manage user permissions, you must create RAM users and groups. Then, you need to grant different permissions to each RAM user and group. This topic describes how to use RAM to manage user permissions.

## Create a RAM user {#section_gkw_3cl_sfb .section}

1.  Log on to the [Resource Access Management console](https://ram.console.aliyun.com) with your Alibaba Cloud account.
2.  In the left-side navigation pane, click **Users**.
3.  In the upper-left corner, click **Create User** to open the Create User dialog box.
4.  Specify the required information, select **Programmatic Access**, and click **OK**.
5.  After you create a user, an AccessKey is generated for the user. Click **Save AccessKey**.

    **Note:** 

    -   After an AccessKey is generated, you cannot view the AccessKey in the console. You must save your AccessKey and keep it secret.
    -   For more information, see [Create a RAM user](../../../../intl.en-US/Quick Start/(Old Version) Quick Start/Create a RAM user.md).

## Create a user group {#section_hfx_45h_yfb .section}

If you attempt to create multiple RAM users, you can group RAM users with identical responsibilities into the same group and authorize the group. This makes it easier to manage users and their permissions.

1.  Log on to the [Resource Access Management console](https://ram.console.aliyun.com) with your Alibaba Cloud account.
2.  In the left-side navigation pane, click **Groups**.
3.  In the upper-right corner, click **Create Group** to open the Create Group dialog box.
4.  Enter a group name and click **OK**.

**Note:** 

-   For more information about how to create a group, see [Groups](../../../../intl.en-US/Quick Start/(Old Version) Quick Start/Create a RAM user.md).
-   For more information, see [Obtain an AccessKey for a RAM user](../../../../intl.en-US/FAQ/Common issues/Obtain an AccessKey for RAM users.md).

## Grant permissions to a RAM user or group {#section_bmt_q5h_yfb .section}

By default, a new RAM user or group does not have any permissions. You need to grant permissions to the RAM user or group before using the user or group to operate resources by using the console or APIs.

Two types of permissions to use the Hybrid Backup Recovery \(HBR\) service are available for RAM users:

-   AliyunHbrFullAccess: grants a RAM user full access to HBR.
-   AliyunHbrReadOnlyAccess: grants a RAM user read-only access to HBR.

You can grant one of these permissions to a RAM user or group in the RAM console. For more information about how to authorize a RAM user or group, see [Authorize a RAM user](../../../../intl.en-US/Quick Start/(Old Version) Quick Start/Authorize RAM users.md#section_odn_kgf_xdb).

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40360/156747472758766_en-US.jpg)

**Note:** In addition to policies provided by RAM, you can also [create custom policies](../../../../intl.en-US/Quick Start/(Old Version) Quick Start/(Optional) Create a custom policy.md).

