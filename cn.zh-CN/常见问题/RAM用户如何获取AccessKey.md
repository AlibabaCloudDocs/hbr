# RAM用户如何获取AccessKey {#concept_lmy_41m_sfb .concept}

安装文件备份客户端和虚机备份客户端时，需要AccessKey ID和Access Key Secret。本文为您介绍RAM用户（子用户）如何获取AccessKey（AK）。

**说明：** 禁止使用主账号AK，因为主账号AK泄露会威胁您所有资源的安全。请使用子账号AK进行操作，可有效降低AK泄露的风险。

## 前提条件 {#section_osr_3gr_sfb .section}

您已经创建了RAM用户，并为RAM用户授权。具体参考[用户权限管理](../../../../intl.zh-CN/最佳实践/用户权限管理.md)。

## 操作步骤 {#section_pwm_rfr_sfb .section}

1.  使用子账号登录阿里云管理控制台。
2.  将鼠标置于页面右上方的账号图标，然后单击**AccessKey管理**。
3.  在安全信息管理页面，单击**创建AccessKey**。
4.  在弹出的新建用户Accesskey窗口，单击保存**保存AK信息**。
5.  保存AK文件。

**说明：** 

-   在AK文件中，可以看到Access Key ID和Access Key Secret。
-   AK创建后，无法再通过控制台查看。请您妥善保存AK文件，谨防泄露。
-   如果AK丢失，您只能重新创建AK。新创建的AK与原来的AK都是代表相同的用户身份，同一个RAM用户的不同AK在使用上是完全等效的。

