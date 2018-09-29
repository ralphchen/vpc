# Change the network type of ApsaraDB for MongoDB {#concept_okq_mbv_sdb .concept}

This document introduces how to change the network type of ApsaraDB for MongoDB to VPC on the console or through the API, and retain the classic network endpoint. The classic network endpoint will be reserved for a period of the time. You can specify the reservation time according to your needs. When the reservation time is reached, the classic network endpoint is automatically deleted by the system.

## Prerequisites {#section_vcx_2w5_sdb .section}

Before changing the network type, make sure that the following conditions are met:

-   Make sure the network type is the classic network.

-   The instance type must be MongoDB replica set.

-   Make sure there are available VPC and VSwitches in the zone of the database instance. For more information, see [Create a VPC and a VSwitch](../../../../reseller.en-US/User Guide/Manage a VPC.md#section_ufw_rhv_rdb). 


## Change the network type on the console {#section_p5v_fw5_sdb .section}

1.  Log on to MongoDB console.
2.  Find the target instance and click the instance ID or click **Manage** in the **Actions** column.
3.  In the left-side navigation pane, click the Database Connection tab and then click **Switch to VPC**.
4.  In the displayed dialog box, complete these steps:
    1.  Select the target VPC and VSwitches.
    2.  Select to retain the classic network endpoint and select the retention time.

        **Note:** After you select to retain the classic network endpoint, ECS instances of the classic network can still access data and there is no impact on the service. When the classic network endpoint expires, the system automatically deletes the classic network endpoint and you cannot access the database through the classic network endpoint.

    3.  Click **OK**.
5.  On the Database Connection page, Click **Refresh** to view the VPC endpoint and the classic network endpoint.

## Change the network type through API {#section_gyr_xw5_sdb .section}

1.  Click the SDK link to download the SDK.
    -   [aliyun-python-sdk-dds.zip](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/57966/cn_zh/1502775994876/aliyun-python-sdk-dds.zip)
    -   [aliyun-java-sdk-dds.zip](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/57966/cn_zh/1502776029662/aliyun-java-sdk-dds.zip)
    -   [aliyun-php-sdk-dds.zip](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/57966/cn_zh/1502776047750/aliyun-php-sdk-dds.zip)
2.  Call the ModifyDBInstanceNetworkType API to change the network type.

    **Request parameters**

    |Name|Type|Required|Description|
    |:---|:---|:-------|:----------|
    |Action|String |Yes|The action to perform. Valid value:ModifyDBInstanceNetworkType

|
    |DBInstanceId|String |Yes|The ID of the instance.|
    |NetworkType|String |Yes|The network type of the instance.    -   VPC: VPC
    -   Classic: Classic network
|
    |VPCId| String|No|The ID of the VPC.|
    |VSwitchId| String|No| The ID of the VSwitch.

 This parameter must be specified if VPC ID is specified.

 |
    |RetainClassic| String|No| Whether to retain the classic network endpoint. The default value is False:

    -   True: Retain
    -   False: Do not retain
 |
    |ClassicExpiredDays| String|No| The retention time of the classic network endpoint. The shortest time is 1 day, the longest time is 120 days, and the default value is 7 days.

 This parameter must be specified if RetainClassic is set to True.

 |

    **Response parameters**

    |Name|Type|Description|
    |:---|:---|:----------|
    |RequestId|String|The ID of the request.|
    |TaskId|String|The ID of the task.|

3.  Call the DescribeReplicaSetRole API to view the classic network endpoint and the VPC endpoint.

    **Request parameters**

    |Name|Type|Required|Description|
    |:---|:---|:-------|:----------|
    |Action|String |Yes|The action to perform. Valid value:DescribeReplicaSetRole

|
    |DBInstanceId|String |Yes|The ID of the instance.|

    **Response parameters**

    |Name|Type |Description|
    |:---|:----|:----------|
    |ReplicaSets|List|The list of replica set roles.|
    |DBInstanceId|String|The ID of the instance.|

    **ReplicaSetRole**

    |Name|Type|Description|
    |:---|:---|:----------|
    |ReplicaSetRole|String|Replica set role: Primary | Secondary|
    |ConnectionDomain|String|The connection information of the instance.|
    |ConnectionPort|String|The connection port of the instance.|
    |ExpiredTime|String|The remaining retention time in seconds of the classic network endpoint.|
    |NetworkType|String|The network type of the instance.    -   VPC: VPC
    -   Classic: Classic network
|


