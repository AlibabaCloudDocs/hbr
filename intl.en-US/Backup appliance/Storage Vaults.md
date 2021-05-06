# Storage Vaults

A backup vault is used to store data that is backed up in the cloud. Hybrid Backup Recovery \(HBR\) allows you to create a backup vault only when you create a backup plan. You can also select an existing backup vault to store data that is backed up. This topic provides the basic information of backup vaults.

## Overview

The Storage Vaults page of the HBR console displays all the existing backup vaults. You can view the type, number of backup plans, amount of data, and status of a backup vault. You can also view the time when the vault was created. In addition, on the Storage Vaults page, you can enable cross-region backup and set parameters for a backup vault. You can also configure the time when the vault expires and delete the vault.

![storagevaults](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2885620261/p270303.png)

## Back up files across regions

You can create a remote mirror vault for a backup vault and back up data in the backup vault to the mirror vault to meet disaster recovery requirements. Then, data in the backup vault is automatically copied to the mirror vault. For more information, see [Use a mirror vault to back up data across regions](/intl.en-US/Cross-region backup/Use a mirror vault to back up data across regions.md).

**Note:** A backup vault whose **Backup type** is **Archive** does not support the Remote Backup feature.

## Related operations

|Operation|Description|
|---------|-----------|
|**Modify a backup vault**|Configure the name and alert policy, and specify whether to enable the Search feature for a backup vault.|
|**Modify the time when a backup vault expires**|Modify the time when a backup vault expires. You can specify a retention period or permanently keep a vault. **Note:** If you specify a retention period for a backup vault, the vault is deleted after it expires. |
|**Delete a backup vault**|Delete a backup vault. **Note:** After a backup vault is deleted, it cannot be restored. Proceed with caution. |

