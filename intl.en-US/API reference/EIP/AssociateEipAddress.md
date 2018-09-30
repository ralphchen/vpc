# AssociateEipAddress {#reference_i4w_xmt_ndb .reference}

Bind an EIP to a cloud product instance in the same region.

Note the following before binding an EIP:

-   Only the EIP in the available status can be bound.

-   An EIP can only be bound to one cloud resource.


## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 AssociateEipAddress

 |
|AllocationId|String|Yes| The ID of the EIP.

 |
|InstanceType|String|No| The cloud resource to bind. Valid value:

 -   EcsInstance\(Default\): an ECS instance of the VPC network.

Only the ECS instance in the running or stopped status can be bound.

-   SlbInstance: An SLB instance of the VPC network

After binding, the SLB instance can forward requests from the Internet.

-   Nat: NAT Gateway

If the NAT Gateway has associated with a bandwidth package, submit a ticket to bind an EIP to a NAT Gateway.

-   HaVip: HAVIP

Only the HAVIP in the available or InUse status can be bound.


 Each ECS instance, SLB instance and HAVIP can only be bound with one EIP. However, NAT Gateway can be bound with multiple EIPs.

 |
|InstanceId|String|Yes| The ID of the cloud resource to bind.

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
&InstanceId=i-25skktcp4
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
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    }
    ```


