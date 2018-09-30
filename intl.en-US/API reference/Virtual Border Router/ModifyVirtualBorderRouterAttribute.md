# ModifyVirtualBorderRouterAttribute {#re2ference_i4w_xmt_ndb .reference}

Modify the configurations of a VBR.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 ModifyVirtualBorderRouterAttribute

 |
|RegionId|String|Yes| The region of the VBR.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|VbrId|String|Yes| The ID of the VBR.

 |
|VlanId|String|Yes| The VLAN ID of the VBR. Valid value: \[1, 2999\].

 **Note:** Only the owner of the physical connection can specify this parameter. The VLAN IDs of two VBRs of the same physical connection must be different.

 |
|CircuitCode|String|Yes| The circuit code provided by the network operator for the physical connection.

 **Note:** This parameter can only be specified by the owner of the physical connection.

 |
|LocalGatewayIp|String|Yes| The Alibaba Cloud-Side IP address used as the gateway to connect to the local IDC.

 |
|PeerGatewayIps|String|Yes| The customer-side IP address used as the gateway to connect to VPC.

 |
|PeeringSubnetMask|String|No| The subnet mask of the Alibaba Cloud-side IP address and the customer-side IP address.

 The two IP addresses must be in the same subnet.

 |
|Name|String|No| The name of the VBR.

 The name can contain from 2 to 128 characters including a-z, A-Z, 0-9, underlines, and hyphens. The name must start with an English letter, but cannot start with `http://` or `https://`.

 |
|Description|String|No| The description of the VBR.

 The description can contain from 2 to 256 characters.  The description must start with English letters, but cannot start with `http://` or `https://`.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyVirtualBorderRouterAttribute
&VbrId=vbr-2zee2e2cwetx4k0tohakw
&Name=test
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version = "1.0" encoding = "utf-8 "? >
                            <ModifyVirtualBorderRouterAttributeResponse>
        <RequestId>980960B0-2969-40BF-8542-EBB34FD358AB</RequestId>
    </ModifyVirtualBorderRouterAttributeResponse>
    ```

-   JSON format

    ```
     
        "RequestId": "980960B0-2969-40BF-8542-EBB34FD358AB"
    
    ```


