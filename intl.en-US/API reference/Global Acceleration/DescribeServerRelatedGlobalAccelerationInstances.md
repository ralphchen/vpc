# DescribeServerRelatedGlobalAccelerationInstances {#reference_i4w_xmt_ndb .reference}

Query Global Acceleration instances bound to a backend server.

**Note:** This API only supports querying dedicated-bandwidth instances.

## Request parameters {#section_cch_pjg_mdb .section}

|Name |Type|Required|Description |
|:----|:---|:-------|:-----------|
|Action|String|Yes| The action to perform. Valid value: 

 DescribeServerRelatedGlobalAccelerationInstances

 |
|RegionId|String|Yes| The ID of the region where the Global Acceleration instance is located.

 Call the DescribeRegions API to obtain the region ID.

 |
|ServerType|String|No| The type of the backend server. Valid values:

 -   EcsInstance \(Default\): ECS instance.
-   SlbInstance: SLB instance.

 |
|ServerId|String|Yes| The ID of the backend server.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|DescribeServerRelatedGlobalAccelerationInstances|List|A list of Global Acceleration instances.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeServerRelatedGlobalAccelerationInstances
&RegionId=ap-northeast-1
&ServerId=i-6wefye51xxxxxxxxxx
&CommonRequestParameters
```

**Response example**

JSON format

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

XML format

```
<? xml version="1.0" encoding="UTF-8" ? >
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

