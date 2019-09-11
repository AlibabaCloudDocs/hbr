# Create an AccessKey for a RAM user {#task_1461202 .task}

The AccessKey ID and AccessKey secret are required when you install the file backup client and the virtual machine backup client. This topic describes how to create an AccessKey for a Resource Access Management \(RAM\) user.

Do not use the AccessKey of your Alibaba Cloud account. If it is leaked, the security of all your resources is threatened. We recommend that you use the AccessKey of a RAM user to reduce the risk of leakage.

## Procedure {#section_djo_71t_um4 .section}

To create an AccessKey for a RAM user, perform the following operations:

1.  Log on to the [RAM console](https://ram.console.aliyun.com/) by using an Alibaba Cloud account.
2.  In the left-side navigation pane, click **Identities**, and click **Users**.
3.  In the **User Logon Name/Display Name** column, click the username of the target RAM user.
4.  In the **User AccessKey Pairs** section, click **Create AccessKey**. 

    **Note:** You must enter a verification code if you are creating an AccessKey pair for the first time.

5.  Click **OK**. 

    **Note:** 

    -   The AccessKey Secret is displayed only once when you first create it. You cannot retrieve the AccessKey Secret if you forget it. We recommend that you save the AccessKey Secret for subsequent use.
    -   If the AccessKey pair is disclosed or lost, you must create a new one. Currently, you can create a maximum of two AccessKey pairs.

