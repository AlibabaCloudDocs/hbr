# 为RAM用户创建AccessKey {#task_1461202 .task}

安装文件备份客户端和虚机备份客户端时，需要AccessKey ID和AccessKey Secret。本文介绍如何为RAM用户（子用户）创建访问密钥（AccessKey）。

禁止使用主账号AK，因为主账号AK泄露会威胁您所有资源的安全。请使用子账号AK进行操作，可有效降低AK泄露的风险。

## 操作步骤 {#section_djo_71t_um4 .section}

请执行如下步骤为RAM用户创建AccessKey。

1.  云账号登录[RAM控制台](https://ram.console.aliyun.com/)。
2.  在左侧导航栏的**人员管理**菜单下，单击**用户**。
3.  在**用户登录名称/显示名称**列表下，单击目标RAM用户名称。
4.  在**用户AccessKey** 区域下，单击**创建新的AccessKey**。 

    **说明：** 首次创建时需填写手机验证码。

5.  单击**确认**。 

    **说明：** 

    -   AccessKeySecret只在创建时显示，不提供查询，请妥善保管。
    -   若AccessKey泄露或丢失，则需要创建新的AccessKey，最多可以创建2个AccessKey。

