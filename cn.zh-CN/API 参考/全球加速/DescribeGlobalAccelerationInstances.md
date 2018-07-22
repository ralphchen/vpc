# DescribeGlobalAccelerationInstances {#reference_i4w_xmt_ndb .reference}

查询已创建的全球加速实例列表。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeGlobalAccelerationInstances

 |
|RegionId|String|是| 全球加速实例所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|BandwidthType|String|否| 实例带宽类型，取值：

-   Sharing：创建带宽共享型实例
-   Exclusive（默认值）：创建带宽独享型实例

 |
|GlobalAccelerationInstanceId|String|否| 全球加速实例的ID。

 |
|Name|String|否| 全球加速实例的名称。

 |
|Status|String|否| 全球加速实例状态，取值：

-   Available：可用

-   Inuse：已分配

-   Associating：绑定中

-   Unassociating：解绑中


 |
|ServiceLocation|String|是| 被加速的服务的所属区域。取值：

-   china-mainland：中国大陆

-   north-america：北美

-   asia-pacific：亚太

-   europe：欧洲


 |
|PageNumber|Integer|否| 列表的页码，默认值为1。

 |
|PageSize|Integer|否| 分页查询时每页的行数，最大值为50，默认值为10。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|TotalCount|String|列表条条目数。|
|PageNumber|Integer|当前页码。|
|PageSize|String|每页包含多少条目。|
|GlobalAccelerationInstances|List|全球加速实例列表的详细信息。|

|名称|类型|描述|
|:-|:-|:-|
|RegionId|String|全球加速实例所在的地域。|
|GlobalAccelerationInstanceId|String|全球加速实例的ID。|
|IpAddress|Integer|独享型全球加速实例的公网IP。|
|Status|String|全球加速实例的状态。|
|Bandwidth|Integer|全球加速实例的带宽峰值。|
|ChargeType|String|全球加速实例的付费类型：-   PrePaid：预付费
-   PostPaid：后付费

|
|InternetChargeType|String|全球加速实例的计费方式。|
|ServiceLocation|String|全球加速实例的服务区域。|
|AccelerationLocation|String|全球加速实例的加速区域。|
|Name|String|全球加速实例的名称。|
|Description|String|全球加速实例的描述。|
|CreationTime|String|全球加速实例的创建时间，UTC时间。|
|OperationLocks|String|全球加速实例的被锁定原因：-   financial：因欠费被锁定。
-   security：因安全原因被锁定。

|
|BackendServers|List|全球加速实例的后端服务器的详细信息。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeGlobalAccelerationInstances
&RegionId=ap-southeast-1
&公共请求参数
```

**返回示例**

JSON格式

```
{
  "GlobalAccelerationInstances": {
    "GlobalAccelerationInstance": [
      {
        "AccelerationLocation": "china-mainland",
        "BackendServers": {
          "BackendServer": [
            {
              "RegionId": "cn-beijing",
              "ServerId": "lb-2222222333333333",
              "ServerIpAddress": "192.168.0.180",
              "ServerType": "SlbInstance"
            }
          ]
        },
        "Bandwidth": "10",
        "ChargeType": "PrePaid",
        "CreationTime": "2017-07-26T03:34:30Z",
        "Description": "",
        "ExpiredTime": "2017-08-26T16:00Z",
        "GlobalAccelerationInstanceId": "ga-aabbccddaabb",
        "InternetChargeType": "PayByBandwidth",
        "IpAddress": "12.34.56.78",
        "Name": "",
        "OperationLocks": {
          "LockReason": []
        },
        "RegionId": "cn-shanghai",
        "ServiceLocation": "asia-pacific",
        "Status": "InUse"
      }
    ]
  },
  "PageNumber": 1,
  "PageSize": 10,
  "RequestId": "0487FCA3-E152-4726-8A17-25F69E03ADB0",
  "TotalCount": 1
}
```

XML格式

```
<?xml version="1.0" encoding="UTF-8" ?>
<DescribeGlobalAccelerationInstancesResponse>
	<GlobalAccelerationInstances>
		<GlobalAccelerationInstance>
			<AccelerationLocation>china-mainland</AccelerationLocation>
			<BackendServers>
				<BackendServer>
					<RegionId>cn-beijing</RegionId>
					<ServerId>lb-2222222333333333</ServerId>
					<ServerIpAddress>192.168.0.180</ServerIpAddress>
					<ServerType>SlbInstance</ServerType>
				</BackendServer>
			</BackendServers>
			<Bandwidth>10</Bandwidth>
			<ChargeType>PrePaid</ChargeType>
			<CreationTime>2017-07-26T03:34:30Z</CreationTime>
			<Description></Description>
			<ExpiredTime>2017-08-26T16:00Z</ExpiredTime>
			<GlobalAccelerationInstanceId>ga-aabbccddaabb</GlobalAccelerationInstanceId>
			<InternetChargeType>PayByBandwidth</InternetChargeType>
			<IpAddress>12.34.56.78</IpAddress>
			<Name></Name>
			<OperationLocks></OperationLocks>
			<RegionId>cn-shanghai</RegionId>
			<ServiceLocation>asia-pacific</ServiceLocation>
			<Status>InUse</Status>
		</GlobalAccelerationInstance>
	</GlobalAccelerationInstances>
	<PageNumber>1</PageNumber>
	<PageSize>10</PageSize>
	<RequestId>0487FCA3-E152-4726-8A17-25F69E03ADB0</RequestId>
	<TotalCount>1</TotalCount>
</DescribeGlobalAccelerationInstancesResponse>
```

