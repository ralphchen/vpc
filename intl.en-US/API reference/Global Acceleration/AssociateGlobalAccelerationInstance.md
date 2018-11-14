# AssociateGlobalAccelerationInstance {#reference_i4w_xmt_ndb .reference}

Bind a backend server to a dedicated-bandwidth Global Acceleration instance.

Note the following before calling the API:

-   Only an ECS instance or SLB instance of the VPC network can be bound to a dedicated-bandwidth instance.

-   Only one backend server can be bound to a dedicated-bandwidth instance.

-   A backend server can be bound to multiple dedicated-bandwidth instances.

-   The backend server and the dedicated-bandwidth instance must belong to the same account.

-   The region of the backend server to bind must be in the server area of the dedicated-bandwidth instance.
-   Only dedicated-bandwidth instances support using this API to bind a backend server.

## Request parameters {#section_cch_pjg_mdb .section}

|Name |Type|Required|Description |
|:----|:---|:-------|:-----------|
|Action|String|Yes| The action to perform.  Valid value: 

 AssociateGlobalAccelerationInstance

 |
|RegionId|String|Yes| The ID of the region where the dedicated-bandwidth instance is located.

 Call the DescribeRegions API to obtain the region ID.

 |
|GlobalAccelerationInstanceId|String|Yes| The ID of the dedicated-bandwidth instance.

 |
|BackendServerRegionId|String|Yes| The region of the backend server, which must belong to the server area of the dedicated-bandwidth instance.

 |
|BackendServerType|String|No| The type of the backend server. Valid values:

 -   EcsInstance \(Default\): ECS instance
-   SlbInstance: SLB instance

 |
|BackendServerId|String|Yes| The ID of the backend server.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=AssociateGlobalAccelerationInstance 
&amp;RegionId=ap-southeast-1
&amp;GlobalAccelerationInstanceId=ga-aabbccddaabb
&amp;BackendServerRegionId=ap-northeast-1
&amp;BackendServerId=i-6we1ge5qfxxxxxx
&amp;BackendServerType=EcsInstance
&amp;CommonReuqestParameters
```

**Response example**

JSON format

```
{
    "RequestId": "DDF2CC38-76C7-4000-909D-B2088158AEDA"
}
```

XML format

```
&lt;? xml version="1.0" encoding="UTF-8" ? >
&lt;AssociateGlobalAccelerationInstanceResponse>
    &lt;RequestId>DDF2CC38-76C7-4000-909D-B2088158AEDA&lt;/RequestId>
&lt;/AssociateGlobalAccelerationInstanceResponse>
```

