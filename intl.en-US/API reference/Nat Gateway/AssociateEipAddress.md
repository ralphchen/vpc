# AssociateEipAddress {#reference_i4w_xmt_ndb0 .reference}

Bind an EIP to a cloud product instance in the same region.

**Note:** 

-   You can bind an EIP to an ECS instance of the VPC network, an SLB instance of the VPC network, or a NAT gateway. This document introduces how to use this API to bind an EIP to a NAT gateway. For more information, see [AssociateEipAddress](intl.en-US/API reference/EIP/AssociateEipAddress.md#).

-   This API can only be called if your account did not include a NAT bandwidth package before January 26, 2018. If your account included a NAT bandwidth package before January 26, 2018, submit a ticket.


## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value: 

 AssociateEipAddress

 |
|AllocationId|String|Yes| The ID of the EIP.

 |
|InstanceType|String|No| The cloud resource to bind. Valid value: Nat

 |
|InstanceId|String|Yes| The ID of the NAT gateway instance.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=AssociateEipAddress
&AllocationId=eip-25877c70x
&InstanceId=ngw-bp1tcx67xuox8ogre7onm
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
                            <AssociateEipAddressResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        </AssociateEipAddressResponse>
    ```

-   JSON format

    ```
     
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    
    ```


