# 备份VMware虚拟机 {#concept_72766_zh .concept}

混合云备份服务（HBR）可以帮助您备份本地虚拟机的镜像，并在需要时快速恢复备份镜像。本文主要为您介绍如何备份VMware虚拟机的镜像。

如未开通混合云备份服务，您需要登录到[混合云备份控制台](https://hbr.console.aliyun.com)开通服务。

## 步骤一 添加客户端 { .section}

配置客户端并将客户端下载到部署vSphere Client的服务器中。客户端可以帮助您进行备份和恢复任务。具体操作步骤如下：

1.  在需要备份文件的服务器或虚拟机上登录[混合云备份管理控制台](https://hbr.console.aliyun.com)。

    **说明：** 若服务器或虚拟机使用的是未安装图形化界面的Linux系统，需要在有图形化界面的机器（中转机）上登录阿里云混合云备份管理控制台。

2.  在左侧导航栏，选择**本地备份** \> **虚机客户端**。
3.  在页面右上角，单击**添加客户端**。
4.  在添加客户端页面，配置参数，然后单击**创建**。各参数说明如下。

    |参数|说明|
    |:-|:-|
    |备份仓库名称|备份仓库是混合云备份的云上存储仓库，用于保存备份的数据。多个客户端可以备份到同一个仓库。    -   如您之前已经创建过备份仓库

在下拉列表中选择希望使用的仓库即可。

    -   如您之前没有创建过备份仓库

单击**新建仓库**。然后输入**仓库名称**和**描述**即可创建一个新仓库。仓库名称不得超过32个字节。

 |
    |客户端名称|为此客户端命名。名称不得超过32个字节。|
    |软件平台|默认选择vSphere。|
    |网络类型|     -   专有网络：备份源使用阿里云专有网络（VPC），且和备份仓库在同一个地域时选择此项。
    -   经典网络：无法使用专有网络的场景下选择此项。
 |
    |备份报警|开启后，如果计划备份失败或客户端与服务器连接断开，系统会向您设置的报警联系人发邮件通知。|

5.  单击**下载客户端**和**下载证书**。

    **说明：** 客户端安装包用于连接阿里云备份服务，证书用来激活该客户端。您也可以返回客户端列表，在任意时间选择下载。


## 步骤二 安装客户端 {#section_ggt_jb2_qfb .section}

将客户端和证书下载到部署vSphere Client的服务器上后，需要安装部署该客户端。安装好后您可以在客户端上进行备份和恢复任务。

1.  登录vSphere Web Client。

    **说明：** 混合云备份目前仅支持VCenter Server 5.5/6.0/6.5版本。

2.  在左侧导航栏，选中要进行部署的虚拟机，右键选择**部署OVF模板**。

    **说明：** 更多关于如何部署OVF模板，参见[部署OVF模板](https://docs.vmware.com/cn/VMware-vSphere/6.5/com.vmware.vsphere.vm_admin.doc/GUID-AFEDC48B-C96F-4088-9C1F-4F0A30E965DE.html?spm=a2c4g.11186623.2.20.37f4127dVeFZcm)。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40338/154529606021128_zh-CN.png)

3.  在部署OVF模板页面，选择**本地文件**。单击**浏览**选择下载好的客户端文件，然后单击**下一步**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40338/154529606021129_zh-CN.png)

4.  输入OVF的名称，然后选择部署位置，然后单击**下一步**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40338/154529606021130_zh-CN.png)

5.  选择运行已部署模板的位置，然后单击**下一步**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40338/154529606021131_zh-CN.png)

6.  验证模板详细信息，然后单击**下一步**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40338/154529606021132_zh-CN.png)

7.  根据需要选择虚拟磁盘格式，选择存储已部署模板文件的位置，然后单击**下一步**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40338/154529606021133_zh-CN.png)

8.  为每个源网络选择目标网络，然后单击**下一步**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40338/154529606021134_zh-CN.png)

9.  自定义该软件解决方案的部署属性，然后单击**下一步**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40338/154529606021135_zh-CN.png)

10. 查看配置数据，然后单击**完成**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40338/154529606021136_zh-CN.png)

11. 在近期任务中查看任务状态，等待任务完成。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40338/154529606021137_zh-CN.png)

12. 部署完成后，启动使用OVF模板部署的虚拟机。
13. 打开浏览器，在地址栏输入`https://hostname:8443`。

    **说明：** `hostname`是您使用OVF模板部署的虚拟一体机的IP地址。

14. 在激活网关页面，输入所需参数，然后单击**注册**登录混合云备份网关。各参数说明如下：

    |参数|说明|
    |:-|:-|
    |Access Key ID和Access Key Secret|在开通HBR服务的阿里云账户中下载Access Key ID和Access Key Secret。详情参见[AccessKey](../../../../intl.zh-CN/通用参考/创建AccessKey.md)。|
    |密码|设置此客户端登录密码，登录密码至少为6位。|
    |证书文件|选择在控制台下载的证书。每个证书的生命周期为2天。超过此周期，请重启虚机，然后重新激活网关。|

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40338/154529606021124_zh-CN.png)


## 步骤三 备份 {#section_jlf_vb2_qfb .section}

混合云虚机备份有两种备份模式：立即备份， [策略备份](../../../../intl.zh-CN/用户指南/虚拟机备份/创建策略备份.md)。本文主要介绍立即备份。立即备份模式只进行一次全量备份。具体操作如下：

1.  登录混合云备份网关，在上方导航栏中，单击**备份**。
2.  单击**添加服务器**或者选择**操作** \> **添加服务器** ，添加备份目标。
3.  在添加服务器窗口，输入需备份服务器类型、服务器地址、用户名、密码，然后单击**确定**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40338/154529606121125_zh-CN.png)

4.  在页面右上角，单击**创建备份计划**。
5.  输入备份计划名称，选择保留时间，单击**立即执行**。单击**下一步**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40338/154529606121126_zh-CN.png)

6.  选择一个或多个虚机，单击**下一步**。
7.  确认备份配置信息和虚机信息，单击**创建**。

**说明：** 备份创建完成后，您可以在备份计划列表中查看相关信息。

## 相关操作 {#section_kv2_bqd_2gb .section}

[恢复VMware虚拟机](../../../../intl.zh-CN/用户指南/虚拟机备份/恢复VMware虚拟机.md)

[设置报警通知](../../../../intl.zh-CN/用户指南/虚拟机备份/设置报警通知.md)

