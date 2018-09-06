# CreateRouteTable {#reference_i4w_xmt_ndb .reference}

Create a custom route table.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String |Yes | The action to perform.  Valid value: 

 CreateRouteTable

 |
|RegionId|String |Yes | The region ID of the VPC to which the route table belongs.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|VpcId|String |Yes |The ID of the VPC to which the custom route table belongs.|
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
|RouteTableId|String|The ID of the route table.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=CreateRouteTable
&RegionId=cn-qingdao
&RouteTableName=myRouteTable
&VpcId=vpc-m5epxxxxxxxxxxxxx
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <CreateRouteTableResponse>
        <RequestId>62172DD5-6BAC-45DF-8D44-xxxxxxx</RequestId>
        <RouteTableId> "vtb-m5evbtbptxxxxxxxxxx</RouteTableId>
    </CreateRouteTableResponse>
    ```

-   JSON format

    ```
    {
      "RequestId": "62172DD5-6BAC-45DF-8D44-xxxxxxxx",
      "RouteTableId": "vtb-m5evbtbptxxxxxxxxxxxx"
    }
    ```


