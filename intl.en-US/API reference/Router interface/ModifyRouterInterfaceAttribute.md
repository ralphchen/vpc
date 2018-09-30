# ModifyRouterInterfaceAttribute {#refere8nce_i4w_xmt_ndb .reference}

Modify the configurations of a router interface.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 ModifyRouterInterfaceAttribute

 |
|RegionId|String|Yes| The region of the router interface.

 You can obtain the region ID by calling the DescribeRegions API.

 |
|RouterInterfaceId|String|Yes| The ID of the router interface.

 |
|AccessPointId|String|No| The ID of the access point to which the VBR belongs.

 You can obtain the region ID by calling the DescribeRegions API.

 **Note:** You must specify this parameter in the scenario of physical access.

 |
|RouterId|String|Yes| The ID of the VRouter associated with the router interface.

 |
|DeleteHealthCheckIp|Boolean|No| Whether to delete the health check IP configured on the router interface.  Valid value: 

 -   true: Delete the health check IP.

-   false\(Default\): Do not delete the health check IP.


 |
|OppositeRouterId|String|No| The ID of the peer router.

 |
|Oppositeinterfaceid|String|No| The ID of the peer router interface.

 |
|OppositeInterfaceOwnerId|String|No| The ID of the owner of the peer router interface.

 |
|HealthCheckSourceIp|String|No| The source IP address used to perform health check on the physical connection. It must be an unused IP address of the local VPC.

 **Note:** You can specify this parameter in the scenario of physical access.

 |
|HealthCheckTargetIp|String|No| The destination IP address of health check.

 **Note:** This parameter is required when the HealthCheckSourceIp parameter is specified.

 |
|Name|String|No| The name of the router interface.

 The name  can contain from 2 to 128 characters including a-z, A-Z, 0-9, underlines, and hyphens. The name must start with an English letter, but cannot start with `http://`  or `https://`.

 |
|Description|String|No| The description of the router interface.

 The description can contain from 2 to 256 characters. The description must start with English letters, but cannot start with `http://` or `https://`.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyRouterInterfaceAttribute
&Name=test
&RouterInterfaceId=ri-2ze7fbuohm7pc3ybei8nv
&RegionId=cn-hangzhou
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
                            <ModifyRouterInterfaceAttributeResponse>
        <RequestId>980960B0-2969-40BF-8542-EBB34FD358AB</RequestId>
    </ModifyRouterInterfaceAttributeResponse>
    ```

-   JSON format

    ```
     
        "RequestId": "980960B0-2969-40BF-8542-EBB34FD358AB"
    
    ```


