# CreateVSwitch {#reference_i4w_xmt_ndb .reference}

创建一个交换机。

调用该接口创建交换机时，请注意：

-   每个VPC内的交换机数量不能超过24个。

-   每个交换机网段的第1个和最后3个IP地址为系统保留地址。以192.168.1.0/24为例，192.168.1.0、192.168.1.253、192.168.1.254和192.168.1.255这些地址是系统保留地址。

-   交换机下的云产品实例数量不允许超过VPC剩余的可用云产品实例数量（15000减去当前云产品实例数量）。

-   一个云产品实例只能属于一个交换机。

-   交换机不支持组播和广播。 交换机创建成功后，网段无法修改。


## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 CreateVSwitch

 |
|RegionId|String|是| 交换机所属VPC所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|ZoneId|String|是| 交换机所属区的ID。

 您可以通过调用 DescribeZones接口获取地域ID。

 |
|CidrBlock|String|是| 交换机的网段。交换机网段要求如下：

 -   交换机网段的掩码长度范围为16-29位。
-   交换机的网段必须从属于所在VPC的网段。
-   交换机的网段不能与所在VPC中路由条目的目标网段相同，但可以是目标网段的子集 。
-   如果交换机的网段与所在VPC的网段相同时，VPC只能有一个交换机。

 |
|VpcId|String|是| 交换机所属的VPC ID。

 |
|VSwitchName|String|否| 交换机的名称。

 长度为 2-128个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |
|Description|String|否| 交换机的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |
|ClientToken|String|否| 客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |

## 返回参数 {#section_pkm_tyw_ndb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|VSwitchId|String|交换机的ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=CreateVSwitch
&CidrBlock=172.16.1.0/24
&VpcId=vpc-257gq642n
&ZoneId=cn-beijing-a
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <CreateVSwitchResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        <VSwitchId>vsw-25naue4gz</VSwitchId>
    </CreateVSwitchResponse>
    ```

-   JSON格式

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0", 
        "VSwitchId": "vsw-25naue4gz"
    }
    ```


