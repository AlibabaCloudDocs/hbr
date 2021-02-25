# Monitor hardware components

This topic describes how to use CloudOps to monitor the status of hardware components in the Hybrid Backup Recovery \(HBR\) console. CloudOps is a free feature that is provided by Alibaba Cloud. It monitors the status of hardware components and sends alert notifications when errors occur. This prevents business interruptions that are caused by hardware failure.

## Prerequisites

-   The backup appliance is installed and activated.

    The CloudOps feature is applicable to disaster recovery storage systems A, C, and S. The CloudOps feature supports appliance types of DR208 and DR408.

-   HBR is activated.
-   The AliyunHBRFullAccess permission policy is attached to the RAM identity that is used to log on to the HBR console.

## Panel

To view the status of the front panel and back panel, perform the following steps:

1.  Log on to the [HBR console](https://hbr.console.aliyun.com).

2.  In the left-side navigation pane, choose **Backup Appliance** \> **CloudOps** .

3.  In the **Panel** section of the Overview page, you can view the real-time status of the front panel and back panel.

    |Panel|Icon|Description|
    |-----|----|-----------|
    |Front panel|![image5](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9683330061/p161076.jpg)|The hard drive is installed and is in the normal state.|
    |![image6](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9683330061/p161077.jpg)|The hard drive is not installed.We recommend that you reinstall the hard drive. |
    |![image7](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9683330061/p161078.jpg)|The hard drive cannot be detected.We recommend that you replace the hard drive. |
    |Back panel|![image6](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9683330061/p161077.jpg)|The hard drive is not installed.We recommend that you reinstall the hard drive. |
    |![image1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9683330061/p161052.jpg)|The network cable is connected.|
    |![image2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9683330061/p161055.jpg)|The network cable is not connected.We recommend that you reconnect the network cable. |
    |![image3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9683330061/p161056.jpg)|Power supply is normal.|


## Storage, CPU, memory, and network

You can view the statistics of the storage, CPU, memory, and network over the last 1 hour, 6 hours, 12 hours, 1 day, 1 week, or 1 month. In this example, the statistics over the last 1 hour is displayed.

-   Storage

    The following figure shows the storage usage \(bytes\) of the logical volumes over the last 1 hour.

    ![storage](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9683330061/p161103.jpg)

-   CPU and memory

    The following figure shows the CPU usage \(%\), memory usage \(%\), and CPU temperature \(°C\) over the last 1 hour.

    ![system](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9683330061/p161106.jpg)

-   Network

    The following figure shows the network bandwidth \(bit/s\) and packet loss rate \(%\) over the last 1 hour.

    ![network](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9683330061/p161107.jpg)


## Alerting

The alerting feature allows developers and operators to develop a monitoring and alerting system on Alibaba Cloud. After you set alert rules for key metrics, you can receive alert notifications when errors occur and fix the errors at the earliest opportunity. For more information about the alerting feature, see [t6227.md\#](/intl.en-US/Alarm service/Enable the initiative alert feature.md).

After you enable the alerting feature, the preconfigured alert rules are applied to all backup appliances in your Alibaba Cloud account. To enable the alarm service, perform the following steps:

1.  Turn on the **Alarm Service** switch in the upper-right corner of the page.

2.  Click **Edit** next to Alarm Contact.

    You are redirected to the Cloud Monitor console to create a notification contact. For more information about how to create a notification contact or group, see [Create an alert contact or alert group](/intl.en-US/Alarm service/Alert contacts/Create an alert contact or alert group.md).


