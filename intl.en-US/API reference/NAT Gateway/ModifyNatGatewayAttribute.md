# ModifyNatGatewayAttribute {#reference_i4w_xm3t_ndb .reference}

Modify the name and description of a NAT gateway.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 ModifyNatGatewayAttribute

 |
|RegionId|String|Yes|  The region of the NAT gateway.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|NatGatewayId|String|Yes| The ID of the NAT gateway.

 |
|Name|String|No| The name of the NAT gateway.

 The name  can contain from 2 to 128 characters including a-z, A-Z, 0-9, underlines, and hyphens. The name must start with an English letter, but cannot start with `http://` or `https://`.

 |
|Description|String|No| The description of the NAT gateway.

 The description can contain from 2 to 256 characters. The description must start with English letters, but cannot start with `http://` or `https://`.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyNatGatewayAttribute
&RegionId=cn-shanghai
&NatGatewayId=ngw-7mwb327j1
&Name=test
&CommonParameters
```

**Response example **

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8" ? >
    <ModifyNatGatewayAttributeResponse>
    	<RequestId>2315DEB7-5E92-423A-91F7-4C1EC9AD97C3</RequestId>
    </ModifyNatGatewayAttributeResponse>
    ```

-   JSON format

    ```
    
      "RequestId": "2315DEB7-5E92-423A-91F7-4C1EC9AD97C3"
    
    ```


