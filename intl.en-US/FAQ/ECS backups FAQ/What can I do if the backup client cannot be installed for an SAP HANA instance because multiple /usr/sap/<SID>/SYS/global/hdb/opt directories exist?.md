# What can I do if the backup client cannot be installed for an SAP HANA instance because multiple /usr/sap/<SID\>/SYS/global/hdb/opt directories exist?

## You can perform the following steps to fix the issue:

1.  Log on to the Elastic Compute Service \(ECS\) instance on which the backup client is installed.

2.  Modify the `/usr/sap/<SID>/SYS/global/hdb/opt` directory to `/usr/sap/<SID>/SYS/global/hdb/opt_backup` for the SAP HANA instances. This applies to the SAP HANA instances that you do not need to back up.

3.  Log on to the Hybrid Backup Recovery \(HBR\) console, and reinstall the backup client for the SAP HANA instance.


