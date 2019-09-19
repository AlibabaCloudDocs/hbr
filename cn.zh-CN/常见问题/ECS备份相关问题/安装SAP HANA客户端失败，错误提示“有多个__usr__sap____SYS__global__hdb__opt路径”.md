# 安装SAP HANA客户端失败，错误提示“有多个/usr/sap/<SID\>/SYS/global/hdb/opt路径” {#concept_uvb_tw2_ghb .task}

## 解决方法 {#section_nif_jwg_jps .section}

1.  远程登录目标ECS实例。
2.  将不需要做备份的SAP HANA实例对应的`/usr/sap/<SID>/SYS/global/hdb/opt`重命名成`/usr/sap/<SID>/SYS/global/hdb/opt_backup`。
3.  返回混合云备份控制台，为该SAP HANA重新安装客户端。

