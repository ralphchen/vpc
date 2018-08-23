# DeleteGlobalAccelerationInstance {#reference_i4w_xmt_ndb .reference}

Delete a Global Acceleration instance.

Note the following before calling this API:

-   Only Pay-As-You-Go instances are supported.
-   If you want to delete a dedicated-bandwidth instance, unbind the backend server before deleting the instance.
-   If you want to delete a shared-bandwidth instance, remove the EIPs before deleting the instance.

## Request parameters {#section_cch_pjg_mdb .section}

|Name |Type|Required|Description |
|:----|:---|:-------|:-----------|
|Action|String|Yes| The action to perform.  Valid value: 

 DeleteGlobalAccelerationInstance

 |
|RegionId|String|Yes| The ID of the region where the Global Acceleration instance is located.

 Call the DescribeRegions API to obtain the region ID.

 |
|GlobalAccelerationInstanceId|String|Yes| The ID of the Global Acceleration instance.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DeleteGlobalAccelerationInstance 
&amp;RegionId=ap-southeast-1
&amp;GlobalAccelerationInstanceId=ga-aabbccddaabb
&amp;CommonRequestParameters
```

**Response example**

JSON format

```
{
    "RequestId": "E6E63B2A-9820-44A8-A359-9BB2DAEE6424"
}
```

XML format

```
&lt;? xml version="1.0" encoding="UTF-8" ? >
&lt;DeleteGlobalAccelerationInstanceResponse>
    &lt;RequestId>BD5BCEE8-F62C-40C2-9AC3-89XXXXXXXXX&lt;/RequestId>
&lt;/DeleteGlobalAccelerationInstanceResponse>
```

