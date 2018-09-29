# ModifyVRouterAttribute {#reference_i4w_xmt_ndb .reference}

Modify the name and description of a VRouter.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 ModifyVRouterAttribute

 |
|VRouterId|String|Yes| The ID of the VRouter.

 |
|VRouterName|String|No| The name of the VRouter.

 The name can contain 2-128 characters including a-z, A-Z, 0-9, underlines, and hyphens. but cannot start with `http://` or `https://`.

 |
|Description|String|No| The description of the VRouter.

 The description can contain 2-256 characters, and must start with English letters but cannot start with `http://` or `https://`.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String| The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyVRouterAttribute
&VRouterId=vrt-25bezkd03
&VRouterName=VRouter
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <ModifyVRouterAttributeResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
    </ModifyVRouterAttributeResponse>
    ```

-   JSON format

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0", 
        "RouteTableId": "vtb-bp145q7glnuzdvzu21pom", 
        "VRouterId": "vrt-bp1lhl0taikrteen80oxx", 
        "VpcId": "vpc-bp15zckdt37pq72zvw30k"
    }
    ```


