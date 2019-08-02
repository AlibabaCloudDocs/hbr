# What should I do if an error occurs while installing the client because the AliyunECSAccessingHBRRolePolicy policy is not authorized for a RAM user? {#concept_jn1_yv2_ghb .concept}

You can perform the following steps to solve the issue.

1.  Log on to the [Resource Access Management \(RAM\) console](https://ram.console.aliyun.com/).
2.  In the left-side navigation bar, select RAM Roles and locate the RAM role that is authorized for the target ECS instance, and click **Add Permissions**.
3.  In the **Select Policy** field, enter AliyunECSAccessingHBRRolePolicy, and click **OK**.
4.  Go to the HBR console, uninstall and reinstall the client.

