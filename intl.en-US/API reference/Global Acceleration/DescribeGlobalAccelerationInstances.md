# DescribeGlobalAccelerationInstances {#reference_i4w_xmt_ndb .reference}

Query a list of created Global Acceleration instances.

## Request parameters {#section_cch_pjg_mdb .section}

|Name |Type|Required|Description |
|:----|:---|:-------|:-----------|
|Action|String|Yes| The action to perform. Valid value: 

 DescribeGlobalAccelerationInstances

 |
|RegionId|String|Yes| The ID of the region where the Global Acceleration instance is located.

 Call the DescribeRegions API to obtain the region ID.

 |
|BandwidthType|String|No| The type of the Global Acceleration instance. Valid values:

-   Sharing: Query shared-bandwidth instances.
-   Exclusive \(Default\): Query dedicated-bandwidth instances.

 |
|GlobalAccelerationInstanceId|String|No| The ID of the Global Acceleration instance.

 |
|Name|String|No| The name of the Global Acceleration instance.

 |
|Status|String|No| The status of the Global Acceleration instance. Valid values:

-   Available: Available

-   Inuse: Allocated

-   Associating: The EIP is being bound.

-   Unassociating: The EIP is being unbound.


 |
|ServiceLocation|String|Yes| The service area of the Global Acceleration instance. Valid values:

-   china-mainland: Mainland China

-   north-america: North America

-   asia-pacific: Asia Pacific

-   europe: Europe


 |
|PageNumber|Integer|No| The number of pages to return. The default value is 1.

 |
|PageSize |Integer|No| The number of rows per page. The maximum value is 50 and the default value is 10.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|
|TotalCount|String|The number of queried entries.|
|PageNumber|Integer|The current page number.|
|PageSize|String|The number of rows per page. |
|GlobalAccelerationInstances|List|A list of Global Acceleration instances.|

|Name|Type|Description|
|:---|:---|:----------|
|RegionId|String|The region of the Global Acceleration instance.|
|GlobalAccelerationInstanceId|String|The ID of the Global Acceleration instance.|
|IpAddress|Integer|The public IP of the dedicated-bandwidth Global Acceleration instance.|
|Status|String|The status of the Global Acceleration instance.|
|Bandwidth|Integer|The peak bandwidth of the Global Acceleration instance.|
|ChargeType|String|The payment method of the Global Acceleration instance. Valid values:-   Postpaid: Pay-As-You-Go

|
|InternetChargeType|String|The billing method of the instance.|
|ServiceLocation|String|The service area of the instance.|
|AccelerationLocation|String|The accelerated area of the instance.|
|Name|String|The name of the instance.|
|Description|String|The description of the instance.|
|CreationTime|String|The time in UTC at which the instance was created.|
|OperationLocks|String|The reason why the instance is locked:-   financial: The instance bill is overdue.
-   security: Security reasons.

|
|BackendServers|List|A list of backend servers bound to the Global Acceleration instance.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeGlobalAccelerationInstances
&RegionId=ap-southeast-1
&CommonRequestParameters
```

**Response example**

JSON format

```
{
  "GlobalAccelerationInstances": {
    "GlobalAccelerationInstance": [
      {
        "AccelerationLocation": "china-mainland",
        "BackendServers": {
          "BackendServer": [
            {
              "RegionId": "cn-beijing"
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
  "Pagesize": 10,
  "RequestId": "0487FCA3-E152-4726-8A17-25F69E03ADB0",
  "TotalCount": 1
}
```

XML format

```
<? xml version="1.0" encoding="UTF-8" ? >
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

