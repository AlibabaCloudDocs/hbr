# 批量添加ECS备份客户端 {#concept_rlm_1lm_qfb .concept}

ECS备份客户端可以帮助您备份和恢复ECS实例中的文件。如果您需要一次为多个ECS实例添加客户端，可以批量添加客户端。

**说明：** 目前HBR仅支持华东1（杭州）、华东2（上海）、华北2（北京）、华南1（深圳）地域下的ECS文件备份。

## 准备工作 {#section_ek5_l3n_qfb .section}

-   使用混合云备份服务来备份ECS文件时需要您同意授权创建两个角色：AliyunHBRDefaultRole，AliyunECSAccessingHBRRole。
-   ECS备份客户端需要和阿里云云助手配合使用。2017年12月01日之后创建的ECS实例，默认预装了云助手客户端。如果需要备份的ECS实例是2017年12月01日之前购买的，需要您自行[安装云助手客户端](../../../../intl.zh-CN/用户指南/云助手/云助手客户端.md)。
-   已经安装好云助手的经典网络ECS实例需要按照以下步骤配置云助手。
    -   Windows系统：
        1.  远程连接该ECS实例，在C:\\ProgramData\\aliyun\\assist\\目录下创建`region-id`文件。
        2.  根据ECS所在地域，在文件中填写相应的`region id`。

            |地域|ID|
            |:-|:-|
            |华东1（杭州）|cn-hangzhou|
            |华东2（上海）|cn-shanghai|
            |华北2（北京）|cn-beijing|
            |华南1（深圳）|cn-shenzhen|

        3.  在任务管理器重启AliyunService服务。
    -   Linux系统：
        1.  远程连接该ECS实例，在/usr/local/share/aliyun-assist/目录下创建`region-id`文件。
        2.  根据ECS所在地域，在文件中填写相应的`region id`。

            |地域|ID|
            |:-|:-|
            |华东1（杭州）|cn-hangzhou|
            |华东2（上海）|cn-shanghai|
            |华北2（北京）|cn-beijing|
            |华南1（深圳）|cn-shenzhen|

        3.  重启云助手服务systemctl restart aliyun。

## 操作步骤 { .section}

1.  登录[混合云备份管理控制台](https://hbr.console.aliyun.com)。
2.  选择要备份的ECS实例所在的区域。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/40784/154529612034482_zh-CN.png)

3.  在左侧导航栏，选择**ECS备份** \> **文件备份**。
4.  在页面右上角，选择**批量操作** \> **批量添加ECS实例**。
5.  在批量添加ECS实例页面，输入**备份仓库名称**来新建一个备份仓库，然后添加仓库描述。

    **说明：** 仓库名称不得超过32个字节。

6.  单击**下载模板**。
7.  打开下载的模板文件。填写Access Key ID及Access Key Secret（VPC网络类型的实例无需填写），然后保存文件。

    **说明：** 

    -   关于如何获取Access Key ID和Access Key Secret，参见[RAM用户如何获取AccessKey](../../../../intl.zh-CN/常见问题/RAM用户如何获取AccessKey.md)。
    -   如果您不需要在某个ECS上安装客户端，请删除该ECS所在一整行。
    -   请不要修改模板文件中的Instance Id，Instance Name，以及Network Type。
    -   为了您的账号安全，在成功上传模版之后，删除本地模版文件。
8.  单击**上传文件**，上传填写好的模板。

    **说明：** 上传后，页面会显示已选择的各类型的ECS实例数量以及总数量。


**说明：** 

-   您可以在ECS备份 / 文件备份页面，单击**ECS实例**页签，查看客户端的安装状态。安装成功后，客户端状态会显示为已激活。
-   如状态为安装失败，请根据错误信息提示进行操作，然后在操作栏中选择**更多** \> **重新安装**。

