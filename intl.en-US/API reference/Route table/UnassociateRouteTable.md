# UnassociateRouteTable {#reference_i4w_xmt_ndb .reference}

Unbind a route table from a VSwitch.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String |Yes | The action to perform.  Valid value: 

 UnassociateRouteTable

 |
|RegionId|String |Yes | The region ID of the VPC to which the route table belongs.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|RouteTableId|String |Yes |The ID of the route table.|
|VSwitchId|String| No|The ID of the VSwitch.|

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=UnassociateRouteTable
&RegionId=cn-qingdao
&RouteTableId=vtb-m5evbtbptnxxxxxxx
&VSwitchId=vsw-m5e3r57pxxxxxxxxxxxxxx
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <UnassociateRouteTableResponse>
        <RequestId>62172DD5-6BAC-45DF-8D44-xxxxxxx</RequestId>
    </UnassociateRouteTableResponse>
    ```

-   JSON format

    ```
    {
      "RequestId": "62172DD5-6BAC-45DF-8D44-xxxxxxxx"
    }
    ```


