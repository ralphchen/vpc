# DeleteRouteTable {#reference_i4w_xmt_ndb .reference}

Delete a custom route table.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String |Yes | The action to perform.  Valid value: 

 DeleteRouteTable

 |
|RegionId|String |Yes | The region ID of the VPC to which the VRouter belongs.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|RouteTableId|String |Yes|The ID of the route table.|

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DeleteRouteTable
&RegionId=cn-qingdao
&RouteTableId=vtb-m5evbtbptnxxxxxxx
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <DeleteRouteTableResponse>
        <RequestId>62172DD5-6BAC-45DF-8D44-xxxxxxx</RequestId>
    </DeleteRouteTableResponse>
    ```

-   JSON format

    ```
    {
      "RequestId": "62172DD5-6BAC-45DF-8D44-xxxxxxxx"
    }
    ```


