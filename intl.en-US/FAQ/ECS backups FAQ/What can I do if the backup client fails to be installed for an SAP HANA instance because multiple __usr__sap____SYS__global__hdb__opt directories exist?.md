# What can I do if the backup client fails to be installed for an SAP HANA instance because multiple /usr/sap/<SID\>/SYS/global/hdb/opt directories exist? {#concept_uvb_tw2_ghb .concept}

You can perform the following operations to resolve the issue:

1.  Log on to the target Elastic Compute Service \(ECS\) instance remotely.
2.  Modify the `/usr/sap/<SID>/SYS/global/hdb/opt` directory of SAP HANA instances that do not require backup to `/usr/sap/<SID>/SYS/global/hdb/opt_backup`.
3.  Go back to the Hybrid Backup Recovery \(HBR\) console, and reinstall the backup client for the SAP HANA instance.

