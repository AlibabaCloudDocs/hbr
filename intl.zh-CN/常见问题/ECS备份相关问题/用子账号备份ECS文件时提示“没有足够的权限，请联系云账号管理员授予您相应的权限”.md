# 用子账号备份ECS文件时提示“没有足够的权限，请联系云账号管理员授予您相应的权限” {#concept_yfp_zvn_mgb .concept}

出现该提示的原因是主账号没有授权AliyunHBRDefaultRole，AliyunECSAccessingHBRRole这两个角色。

使用主账号登录混合云备份控制台，选择**ECS备份** \> **文件备份**，同意授权创建这两个角色即可。您也可以赋予子账号AliyunRAMFullAccess，AliyunSTSAssumeRoleAccess的权限。

