# 客户端安装失败，错误提示：“EcsRamRole上缺少AliyunECSAccessingHBRRolePolicy的策略” {#concept_jn1_yv2_ghb .concept}

您可以通过以下操作解决：

1.  登录 [RAM 控制台](https://ram.console.aliyun.com/)。
2.  在角色管理中找到目标ECS上授予的RAM角色，然后选择**授权**。
3.  在**精确授权**中输入“AliyunECSAccessingHBRRolePolicy”，单击**确定**。
4.  返回混合云备份控制台，卸载并重新安装客户端。

