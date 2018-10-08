# 云数据库MongoDB版网络切换 {#concept_okq_mbv_sdb .concept}

本文档介绍了如何通过控制台和API将云数据库MongoDB版的网络类型切换至专有网络，同时保留经典网络的访问地址。经典网络的访问地址有保留时间限制，您可以根据需要指定保留期限。到期后，经典网络地址会自动被系统删除。

## 前提条件 {#section_vcx_2w5_sdb .section}

在开始切换前，确认当前实例是否具备以下切换条件：

-   确认当前网络类型是否为经典网络。

-   实例类型必须是MongoDB副本集。

-   确认在当前数据库实例可用区下是否有可用的VPC和交换机。详情参见[创建专有网络和交换机](../../../../intl.zh-CN/用户指南/管理专有网络.md#section_ufw_rhv_rdb)。


## 通过控制台切换网络类型 {#section_p5v_fw5_sdb .section}

1.  登录MongoDB管理控制台。
2.  找到目标实例，单击实例ID或单击目标实例**操作**列的**管理**。
3.  在左侧导航栏，单击数据库连接页签，然后单击**切换为专有网络**。
4.  在弹出的对话框中，执行以下操作：
    1.  选择切换的目标专有网络和交换机。
    2.  选择保留经典网络地址并选择保留时长。

        **说明：** 选择保留经典网络后，经典网络下的ECS仍可访问数据，对业务无影响。当经典网络地址到期后，系统会自动删除经典网络地址，您将无法通过经典网络地址访问数据库。

    3.  单击**确定**。
5.  在数据库连接页面，单击**刷新**查看专有网络和经典网的访问地址。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2463/1538981153844_zh-CN.png)


## 通过API切换网络类型 {#section_gyr_xw5_sdb .section}

1.  单击SDK链接下载相关SDK。
    -   [aliyun-python-sdk-dds.zip](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/57966/cn_zh/1502775994876/aliyun-python-sdk-dds.zip)
    -   [aliyun-java-sdk-dds.zip](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/57966/cn_zh/1502776029662/aliyun-java-sdk-dds.zip)
    -   [aliyun-php-sdk-dds.zip](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/57966/cn_zh/1502776047750/aliyun-php-sdk-dds.zip)
2.  调用ModifyDBInstanceNetworkType接口进行网络切换。

    **请求参数说明**

    |名称|类型|是否必须|说明|
    |:-|:-|:---|:-|
    |Action|String|是|系统规定参数，取值：ModifyDBInstanceNetworkType

|
    |DBInstanceId|String|是|实例 ID。|
    |NetworkType|String|是|实例的网络类型：    -   VPC：专有网络
    -   Classic：经典网络
|
    |VPCId|String|否|专有网络的ID。|
    |VSwitchId|String|否| 交换机的ID。

 如果指定了VPC ID，则该参数也必须指定。

 |
    |RetainClassic|String|否| 是否保留经典网络地址，默认False：

    -   True：保留
    -   False：不保留
 |
    |ClassicExpiredDays|String|否| 经典网络地址保留的天数，最短1天，最长120天，默认7天。

 若选择保留经典网络地址，则该参数必传。

 |

    **返回参数说明**

    |参数|类型|说明|
    |:-|:-|:-|
    |RequestId|String|请求ID。|
    |TaskId|String|任务ID。|

3.  调用DescribeReplicaSetRole接口查看经典网络和专有网络的访问地址。

    **请求参数**

    |名称|类型|是否必须|说明|
    |:-|:-|:---|:-|
    |Action|String|是|系统规定参数，取值：DescribeReplicaSetRole

|
    |DBInstanceId|String|是|实例ID。|

    **返回参数**

    |参数|类型|说明|
    |:-|:-|:-|
    |ReplicaSets|List|复制集角色列表。|
    |DBInstanceId|String|实例 ID。|

    **ReplicaSetRole数据结构**

    |参数|类型|说明|
    |:-|:-|:-|
    |ReplicaSetRole|String|复制集角色：Primary | Secondary|
    |ConnectionDomain|String|实例连接域名。|
    |ConnectionPort|String|实例连接端口。|
    |ExpiredTime|String|经典网络地址剩余时长，以秒为单位。|
    |NetworkType|String|实例的网络类型：    -   VPC：专有网络
    -   Classic：经典网络
|


