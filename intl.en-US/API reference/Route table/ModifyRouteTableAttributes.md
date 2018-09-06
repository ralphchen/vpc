# ModifyRouteTableAttributes {#reference_i4w_xmt_ndb .reference}

Modify the name and description of a route table.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String |Yes | The action to perform.  Valid value: 

 ModifyRouteTableAttributes

 |
|RegionId|String |Yes | The region ID of the VPC to which the route table belongs.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|RouteTableId|String |Yes |The ID of the route table.|
|RouteTableName|String| No| The name of the route table.

 The name can contain from 2 to 128 characters including a-z, A-Z, 0-9, periods, underlines, and hyphens, and must start with an English letter. The name cannot start with `http://` or `https://`.

 |
|Description|String| No| The description of the route table.

 The description can contain from 2 to 256 characters. The description must start with English letters, but cannot start with `http://` or `https://`.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyRouteTableAttributes
&RegionId=cn-qingdao
&RouteTableName=myRouteTable
&RouteTableId=vtb-m5evbtbptnxxxxxxx
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <ModifyRouteTableAttributesResponse>
        <RequestId>62172DD5-6BAC-45DF-8D44-xxxxxxx</RequestId>
    </ModifyRouteTableAttributesResponse>
    ```

-   JSON format

    ```
    {
      "RequestId": "62172DD5-6BAC-45DF-8D44-xxxxxxxx"
    }
    ```


