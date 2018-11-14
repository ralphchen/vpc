# DescribeServerRelatedGlobalAccelerationInstances {#reference_i4w_xmt_ndb .reference}

查询指定后端服务器绑定的全球加速实例。

**说明：** 该接口仅支持查询带宽独享型实例。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeServerRelatedGlobalAccelerationInstances

 |
|RegionId|String|是| 全球加速实例所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|ServerType|String|否| 后端服务实例的类型，取值：

 -   EcsInstance（默认值）：ECS实例
-   SlbInstance：负载均衡实例

 |
|ServerId|String|是| 后端服务实例的ID。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|ServerRelatedGlobalAccelerationInstances|List|全球加速实例的详细信息。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeServerRelatedGlobalAccelerationInstances
&RegionId=ap-northeast-1
&ServerId=i-6wefye51xxxxxxxxxx
&公共请求参数
```

**返回示例**

JSON格式

```
{
  "GlobalAccelerationInstances": {
    "GlobalAccelerationInstance": [
      {
        "GlobalAccelerationInstanceId": "ga-t4nku6vv9xxxxxxxxx",
        "IpAddress": "12.34.56.78",
        "RegionId": "ap-southeast-1",
        "ServerIpAddress": "172.24.52.234"
      }
    ]
  },
  "RequestId": "A8252014-D8DE-4D85-AF35-AFEXXXXXXX"
}
```

XML格式

```
<?xml version="1.0" encoding="UTF-8" ?>
<DescribeServerRelatedGlobalAccelerationInstancesResponse>
	<GlobalAccelerationInstances>
		<GlobalAccelerationInstance>
			<GlobalAccelerationInstanceId>ga-t4nku6vv9xxxxxxxxx</GlobalAccelerationInstanceId>
			<IpAddress>12.34.56.78</IpAddress>
			<RegionId>ap-southeast-1</RegionId>
			<ServerIpAddress>172.24.52.234</ServerIpAddress>
		</GlobalAccelerationInstance>
	</GlobalAccelerationInstances>
	<RequestId>A8252014-D8DE-4D85-AF35-AFEXXXXXXX</RequestId>
</DescribeServerRelatedGlobalAccelerationInstancesResponse>
```

