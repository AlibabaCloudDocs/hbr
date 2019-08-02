# What should I do if an error occurs while using a RAM user to back up data from an ECS instance because the user has insufficient permissions? {#concept_yfp_zvn_mgb .concept}

This issue occurs when you do not grant the RAM user the AliyunHBRDefaultRole and AliyunECSAccessingHBRRole roles by using an Alibaba Cloud account.

Log on to the Hybrid Backup Recovery console with an Alibaba Cloud account, choose **ECS Backup** \> **ECS File Backup**, and grant the RAM user the roles. You can also grant the AliyunRAMFullAccess and AliyunSTSAssumeRoleAccess permissions to a RAM user.

