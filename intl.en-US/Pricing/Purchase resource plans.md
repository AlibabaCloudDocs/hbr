# Purchase resource plans

Subscription \(resource plans\) is a billing method that allows you to pay for resources before you use these resource plans. After you purchase resource plans, you can reserve resources that can be used at a later point in time. Also, the resource plans allow you to save costs through higher discount rates. This topic describes how to purchase Hybrid Backup Recovery \(HBR\) resource plans for different backup scenarios.

Before you purchase HBR resource plans, take note of the following information:

-   Resource plans can be used in all the applicable scenarios. For example, you can purchase resource plans for backup storage to deduct storage fees in all backup scenarios. You can also purchase resource plans for file backup license. This can be used to deduct the license fees in both local file backup and ECS file backup scenarios.
-   You cannot deduct traffic fees from the resource plans that you purchase. For more information about pay-as-you-go billing method, see [Hybrid Backup Recovery \(HBR\) Pricing](https://www.alibabacloud.com/product/hybrid-backup-recovery/pricing).

HBR resource plans are divided into two categories. One category is used to back up ECS-hosted databases. The other category is used in other scenarios. The following table provides further details.

**Note:** In the following table, the ✓ indicates that you must purchase the resource plan in the scenario. In the following table, the x indicates that you do not need to purchase resource plans in the scenario.

-   Scenarios where ECS-hosted databases are backed up

    The scenarios include the backup of ECS self-managed MySQL instances, Oracle instances, and SQL Server instances. The backup of SAP HANA is not included.

    |Scenario|Resource plan of warehouse rental for database backup|Storage resource plan for database backup|Storage resource plan for continuous log backup|
    |--------|-----------------------------------------------------|-----------------------------------------|-----------------------------------------------|
    |Back up ECS-hosted databases|✓ Purchase only one resource plan for each region where the database that you want to back up resides.

|✓ Purchase the resource plan based on the capacity of the database. The capacity of the resource plan is 1.5 times the capacity of the database. If the backup storage you use exceeds the capacity of your resource plan, you can purchase a new resource plan to cover the excess.

|xYou are not required to purchase a resource plan for continuous log backup. If you require a resource plan for continuous log backup, purchase a resource plan based on the result of the following formula: Incremental data per day × Retention period. |

-   Other scenarios

    |Scenario|Resource plan of backup storage|Resource plan of file backup license|Resource plan of VMware VM backup license|Resource plan of application backup license|
    |--------|-------------------------------|------------------------------------|-----------------------------------------|-------------------------------------------|
    |Back up local files|✓ You can use [Backup Storage Calculator](https://g.alicdn.com/aliyun/brs/2.7.1/calc.html) to estimate the required backup storage.

|✓ Purchase clients based on the number of servers that you want to back up.

|x|x|
    |Back up on-premises VMware VMs|✓ We recommend that you purchase a storage resource plan based on 80% of the total disk size of the VMware VMs. Then, you can increase the capacity of the VMware VMs as required.

|x|✓Purchase clients based on the total disk size of VMware VMs that you want to back up.

|x|
    |Back up ECS file backup|✓ You can use [Backup Storage Calculator](https://g.alicdn.com/aliyun/brs/2.7.1/calc.html) to estimate the required backup storage.

|✓ Purchase clients based on the number of ECS instances that you want to back up.

|x|x|
    |Back up an SAP HANA database deployed on an ECS instance|✓ We recommend that you purchase a storage resource plan that is at least twice the size of the database. You can upgrade the plan later based on your business requirements.

|x|x|✓ Purchase clients based on the number of ECS instances that you want to back up. |
    |Back up OSS backup|✓ You can use [Backup Storage Calculator](https://g.alicdn.com/aliyun/brs/2.7.1/calc.html) to estimate the required backup storage.

|x|x|x|
    |Back up Apsara File Storage NAS file systems|✓ You can use [Backup Storage Calculator](https://g.alicdn.com/aliyun/brs/2.7.1/calc.html) to estimate the required backup storage.

|x|x|x|


