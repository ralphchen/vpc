# CancelPhysicalConnection {#reference_smh_b4k_qdb .reference}

Cancel physical connection access. After the cancelling, the physical connection changes to the Canceled status.

You can only cancel physical connections that are not enabled, including physical connections in the Initial, Approved, Allocated, or Confirmed status.

## Request parameters {#section_vmh_b4k_qdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 CancelPhysicalConnection

 |
|RegionId|String|Yes.| The region of the physical connection.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|PhysicalConnectionId|String|Yes| The ID of the physical connection.

 |

## Response parameters {#section_nnh_b4k_qdb .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_qnh_b4k_qdb .section}

**Request example**

```
hhttp://vpc.aliyuncs.com/?Action=CancelPhysicalConnection
&PhysicalConnectionId=pc-2zeoaxkq3xxxxx
&RegionId=cn-beijing
&CommonParameters
```

**Response example**

JSON format

```

    "RequestId": "BE36E95A-F83E-4127-A29E-F2F35D4C999A"

```

