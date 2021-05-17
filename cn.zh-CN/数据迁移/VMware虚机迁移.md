# VMware虚机迁移

本文介绍如何在混合云备份控制台将线下VMware虚拟机从一个主机或存储位置迁移上云。

## 前提条件

-   若您的Linux虚拟机使用LVM（Logical Volume Manager）卷作为系统盘，则虚拟机迁移服务暂时无法支持。
-   迁移前务必保证系统盘有至少1 GB的可用空间。待迁移虚拟机为Linux系统时，系统引导程序GRUB须为1.99及以上版本。

**说明：**

-   对于CentOS 5、Red Hat 5和Debian 7等低版本操作系统，需要更新GRUB至1.99及以上版本。
-   部分系统如Amazon Linux需要更新至2.02及以上版本。

## 背景信息

VMware虚拟机迁移服务主要针对VMware环境的虚拟机提供非侵入式的无代理整机迁移功能，其原理是基于VMware的快照以及磁盘级别的数据读取功能，将虚拟机整机全盘迁移到ECS上。

-   支持的地域

    混合云备份支持地域目前陆续开放，实际支持地域请以控制台为准。

-   支持的操作系统

    VMware虚拟机迁移服务支持如下操作系统：CentOS、Ubuntu、CoreOS、Aliyun、Debian、Gentoo、SUSE、OpenSUSE、FreeBSD、RedHat、Windows Server 2003、Windows Server 2008、Windows Server 2012、Windows Server 2016、Windows 7、Customized Linux、Mars以及NeoKylin。


## 步骤1：创建迁移网关

1.  登录[混合云备份管理控制台](https://hbr.console.aliyun.com)。

2.  在左侧导航栏，单击**迁移** \> **VMware虚机迁移**。

3.  单击右上角的**创建迁移网关**。

    **说明：** 单个地域仅支持创建一个迁移网关。

4.  在**创建迁移网关**页面，配置参数，然后单击**创建**。

    各参数说明如下：

    |参数|说明|
    |:-|:-|
    |网关名称|为此迁移网关命名。名称不得超过64个字节。|
    |软件平台|当前仅支持**vSphere**。|
    |网络类型|    -   **专有网络（VPC）**：网关通过专线（阿里云专有网络，VPC）传输迁移数据时，选择此项。
    -   **公网**：无法使用专有网络的场景下选择此项。 |
    |用HTTPS传输数据|数据加密存储到备份库后，您可以选择是否使用HTTPS传输数据。使用HTTPS会降低数据传输性能。如果修改了此项配置，在下一次迁移任务开始时生效。|

5.  单击**下载客户端**和**下载证书**。

    **说明：** 客户端安装包用于连接阿里云备份服务，证书用来激活该客户端。您也可以返回客户端列表，在任意时间选择下载。


## 步骤2：安装客户端

下载客户端和证书后，需要安装该客户端。安装后您可以在客户端上进行迁移任务。安装客户端的具体操作步骤如下：

1.  登录vSphere Web Client。

    **说明：** 混合云备份目前仅支持VCenter Server 5.5、6.0或6.5版本。

2.  在左侧导航栏，选中要进行部署的虚拟机，右键选择**部署OVF模板**。

    ![OVF](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6356449951/p35163.png)

    **说明：** 关于如何部署OVF模板，更多信息，请参见[部署OVF模板](https://docs.vmware.com/cn/VMware-vSphere/6.5/com.vmware.vsphere.vm_admin.doc/GUID-AFEDC48B-C96F-4088-9C1F-4F0A30E965DE.html?spm=a2c4g.11186623.2.20.37f4127dVeFZcm)。

3.  在部署OVF模板页面，选择**本地文件**。单击**浏览**选择下载好的客户端文件，然后单击**下一步**。

    ![选择模板](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6356449951/p35164.png)

4.  输入OVF的名称，选择部署位置，然后单击**下一步**。

    ![选择名称和位置](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3151409951/p68313.jpg)

5.  选择运行已部署模板的位置，然后单击**下一步**。

    ![选择资源](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6356449951/p35166.png)

6.  验证模板详细信息，然后单击**下一步**。

    ![查看详情](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6356449951/p35167.png)

7.  根据需要选择虚拟磁盘格式，选择存储已部署模板文件的位置，然后单击**下一步**。

    ![选择存储](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7356449951/p35168.png)

8.  为每个源网络选择目标网络，然后单击**下一步**。

    ![选择网络](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4151409951/p68314.jpg)

9.  自定义该软件解决方案的部署属性，然后单击**下一步**。

    ![自定义模板](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7356449951/p35170.png)

10. 查看配置数据，然后单击**完成**。

    ![配置数据](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7356449951/p35171.png)

11. 在近期任务中查看任务状态，等待任务完成。

    ![近期任务](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4151409951/p68331.jpg)

12. 部署完成后，启动使用OVF模板部署的虚拟机。

13. 打开浏览器，在地址栏输入`http://hostname:8011`。

    **说明：** `hostname`是您使用OVF模板部署的虚拟机的IP地址。

14. 在激活网关页面，输入所需参数，然后单击**注册**登录混合云备份网关。各参数说明如下：

    |参数|说明|
    |:-|:-|
    |AccessKey ID|在开通HBR服务的阿里云账户中下载AccessKey ID和AccessKey Secret。详情请参见[为RAM用户创建AccessKey](/cn.zh-CN/常见问题/一般性问题/为RAM用户创建AccessKey.md)。|
    |AccessKey Secret|
    |证书文件|选择在控制台下载的证书。证书激活后如果虚拟机关机超过5天，证书会失效，需要重新下载证书并激活。|

    激活成功后，单击**确定**将跳转至混合云备份HBR控制台。


## 步骤3：添加vCenter

1.  在**迁移网关**页签，单击操作栏下的**查看**。

    ![查看](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4151409951/p68353.jpg)

2.  单击右上角的**添加vCenter服务器**。

3.  在**添加vCenter服务器**页面，填写**服务器网络地址**、**用户名**和**密码**，然后单击**创建**。

    密码中若包含以下特殊字符，可能会导致无法添加vCenter服务器：

    \` ^ ~ = ; ! / \( \[ \] \{ \} @ $ \\ & \# % +

    **说明：** 建议您新建一个专门用于备份的VCenter服务器账号（具备Administrator权限），密码中的特殊字符建议使用英文句号（.）。


## 步骤4：迁移VMware虚拟机

1.  单击操作栏下的**迁移**。

    ![vCenter](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4151409951/p68364.jpg)

2.  在**迁移计划**页签，按照以下说明填写各项参数，然后单击**下一步**。

    ![plan](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4151409951/p84834.jpg)

    |参数|说明|
    |--|--|
    |**迁移计划名称**|为该迁移计划命名。可不填，默认名字随机分配。|
    |**迁移计划**|选择**立即迁移**或**指定时间迁移**。 选择**指定时间迁移**时，需指定**迁移开始时间**，精确到秒。 |
    |**强制使用静默快照**|    -   选中：强制使用静默快照备份，如果无法使用静默快照，则备份失败。
    -   未选中（默认）：首先尝试使用静默快照备份，如果无法使用静默快照，则使用普通快照。 |
    |**是否使用增量迁移**|您可以选择是否使用增量迁移。 使用增量迁移时，需要指定**增量同步频率间隔**，单位为小时、天、周。

**说明：**

    -   如果虚拟机禁止了数据块修改跟踪技术（CBT），增量迁移将强制转为全量迁移。
    -   增量迁移模式下，HBR将自动创建镜像以支持测试拉起，会产生一定的镜像费用，镜像费用由ECS收取。详情请参见[计费概述](/cn.zh-CN/产品计费/计费概述.md)。 |

3.  选择**待迁移虚机**，单击**下一步**。

    ![待迁移虚机](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4151409951/p68369.jpg)

4.  在**配置云上ECS**页签，选择**专有网络**、**交换机**、**实例类型**、**实例规格**、**存储类型**、**安全组**、**IP地址类型**、是否**分配公网IP**、是否**恢复后启动系统**，是否**创建系统镜像**，选择**复制配置到所有虚机**或**保存配置到当前虚机**。

    **说明：** 选择安全组时，请确保允许出方向的TCP 80、443端口以及UDP 53端口。

    ![创建迁移计划](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4151409951/p68373.jpg)

5.  单击**创建**后，即可启动当前迁移任务。在迁移状态页面，您可以查看迁移进度。

    ![syn](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4151409951/p84851.jpg)

    如果使用了增量迁移，待虚拟机迁移完成后，您可以执行以下操作。

    -   单击**同步记录**，您可以查看增量迁移的数据大小、迁移的状态等信息。

        ![syn](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4151409951/p85372.jpg)

    -   单击**创建ECS**，在弹出框中选择**迁移验证**或**完成迁移**。

        ![verification](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4151409951/p85370.jpg)

        -   单击**迁移验证**，即将以最近一次同步（例如，2020-02-21 20:21:31）的数据创建ECS，用于验证迁移到ECS的虚拟机是否工作正常。每台虚拟机最多可以做3次验证，验证不会中断预设的增量同步。确认进行迁移认证，请单击**确定**，开始创建ECS，待ECS创建完成后，您可以单击**继续迁移**，将清除已经创建的ECS并继续迁移。

            ![continue](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4151409951/p85373.png)

        -   单击**完成迁移**，即将以最近一次同步（例如，2020-02-21 20:21:31）的数据创建迁移完成的ECS，并不再进行同步。您也可以选择**完成迁移之前做最后一次增量同步**来将上次同步之后的数据更新到迁移完成的ECS中。
        **说明：**

        -   最后一次增量同步会增加完成迁移操作所需要的时间。
        -   首次迁移验证或完成迁移操作成功立即收取该虚拟机的迁移费用，同一台虚拟机重复验证和完成迁移不再额外计费。如需获取更多费用信息，请参见[价格详情](https://www.aliyun.com/price/detail/hbr)。
    -   单击**取消迁移**，即取消本次迁移任务。

## 收集日志方法

收集日志的具体操作方法，请参见[VMware虚机备份客户端日志收集](/cn.zh-CN/本地服务器备份教程/虚拟机备份/日志收集及网络诊断.md)。

