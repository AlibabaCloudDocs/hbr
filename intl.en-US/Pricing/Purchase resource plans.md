# Purchase resource plans

Subscription \(resource plans\) is a billing method that allows you to pay for resources before you use them. By purchasing resource plans, you can reserve resources in advance to reduce costs and take advantage of higher discount rates. This topic describes how to purchase Hybrid Backup Recovery \(HBR\) resource plans for different backup scenarios.

Take note of the following items when you purchase HBR resource plans:

-   In the following table, the ✓ mark indicates that you must purchase the resource plan in the scenario. The x mark indicates that resource plan is not required in the scenario.
-   Resource plans can be used in any applicable scenario. For example, you can purchase backup storage resource plans to deduct storage fees in all backup scenarios. You can also purchase file backup license resource plans to deduct the license fees in both local file backup and ECS file backup scenarios.
-   Traffic fees are billed in the pay-as-you-go method and cannot be deducted by resource plans. For more information, see[Hybrid Backup Recovery \(HBR\) Pricing](https://www.alibabacloud.com/product/hybrid-backup-recovery/pricing).

|Scenario|Backup storage resource plan|File backup license resource plan|VMware VM backup license resource plan|Application backup license resource plan|
|--------|----------------------------|---------------------------------|--------------------------------------|----------------------------------------|
|Local file backup|✓ You can use [Backup Storage Calculator](https://g.alicdn.com/aliyun/brs/2.7.1/calc.html) to estimate the required backup storage.

|✓ Purchase clients based on the number of servers to back up.

|x|x|
|Back up SQL Server databases|✓ We recommend that you purchase a storage resource plan with a capacity at least twice the size of the database to back up and upgrade the plan based on further requirements.

|x|x|✓ Purchase clients based on the number of SQL servers to back up. |
|Local VMware VM backup|✓ We recommend that you purchase a storage resource plan with a capacity at least 80% of the total disk size of the VMware VMs to back up and upgrade the plan based on further requirements.

|x|✓ Purchase clients based on the total disk size of VMware VMs to back up.

|x|
|ECS file backup|✓ You can use [Backup Storage Calculator](https://g.alicdn.com/aliyun/brs/2.7.1/calc.html) to estimate the required backup storage.

|✓ Purchase clients based on the number of ECS instances to back up.

|x|x|
|ECS SQL Server and ECS SAP HANA backup|✓ We recommend that you purchase a storage resource plan with a capacity at least twice the size of the database to back up and upgrade the plan based on further requirements.

|x|x|✓ Purchase clients based on the number of ECS instances to back up. |
|OSS backup|✓ You can use [Backup Storage Calculator](https://g.alicdn.com/aliyun/brs/2.7.1/calc.html) to estimate the required backup storage.

|x|x|x|
|NAS backup|✓ You can use [Backup Storage Calculator](https://g.alicdn.com/aliyun/brs/2.7.1/calc.html) to estimate the required backup storage.

|x|x|x|

