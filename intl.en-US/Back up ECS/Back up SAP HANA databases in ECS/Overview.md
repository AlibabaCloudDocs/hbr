# Overview

Hybrid Backup Recovery \(HBR\) is a fully managed online backup service that allows you to back up data to the cloud in an efficient, secure, and cost-effective way. HBR is compatible with SAP HANA 1.0 and 2.0 and integrated with the SAP HANA API to back up and restore data. You can use HBR backup clients for Elastic Compute Service \(ECS\) to back up SAP HANA instances that are hosted on ECS. You can then restore these instances if needed.

**Note:** HBR uses the Backint API for SAP HANA to back up and restore data. Backup data is not stored in files. HBR calls the Backint API for SAP HANA to directly read data from or write data to SAP HANA instances.

You can use the following procedure to back up an SAP HANA instance:

-   [Prepare for backup](/intl.en-US/Back up ECS/Back up SAP HANA databases in ECS/Preparations.md).
-   [Back up an SAP HANA instance](/intl.en-US/Back up ECS/Back up SAP HANA databases in ECS/Back up an SAP HANA database.md).
-   [Restore an SAP HANA instance](/intl.en-US/Back up ECS/Back up SAP HANA databases in ECS/Restore databases of an SAP HANA instance.md).

For information about other features of SAP HANA backup, see the following topics:

-   [Set a backup policy](/intl.en-US/Back up ECS/Back up SAP HANA databases in ECS/Set backup parameters.md)
-   [Set alert notification methods](/intl.en-US/Back up ECS/Back up SAP HANA databases in ECS/Configure alert notifications.md)

**Note:** For information about how to back up an on-premises SAP HANA instance, see [Back up a database based on workflows](/intl.en-US/Back up on-premises severs/Workflow-based backup/Overview.md).

