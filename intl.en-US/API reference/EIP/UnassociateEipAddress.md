# UnassociateEipAddress {#reference_i4w_xmt_ndb .reference}

Unbind an EIP from a cloud resource.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 UnassociateEipAddress

 |
|AllocationId|String|Yes| The ID of the EIP.

 |
|InstanceType|String|No| The type of the cloud resource to be unbound. Valid value:

 -   EcsInstance\(Default\): an ECS instance in a VPC

-   SlbInstance: an SLB instance in a VPC

-   Nat: NAT Gateway

-   HaVip: HAVIP


 |
|InstanceId|String| Yes| The ID of the cloud resource to be unbound.

 |
|Force|String| Yes| Whether to unbind the EIP from the cloud resource by force. Valid value:

-   False（默认值）

-   True


 **Note:** Only NAT Gateway supports force unbinding. The SNAT table or the DNAT table associated with the EIP will be deleted if the EIP is unbound by force.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=UnassociateEipAddress
&AllocationId=eip-25877c70x
&InstanceId=i-25skktcp4
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    	<UnassociateEipAddressResponse>
    	<RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
    </UnassociateEipAddressResponse>
    ```

-   JSON format

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    }
    ```


