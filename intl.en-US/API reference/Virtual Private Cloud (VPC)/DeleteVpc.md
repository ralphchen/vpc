# DeleteVpc {#reference_i4w_xmt_ndb .reference}

Delete a VPC.

Note the following before deleting a VPC:

-   Before deleting a VPC, you must release or remove all resources in the VPC, including VSwitches, cloud product instances, router interfaces, HaVip, and so on.

-   Only VPCs in the available status can be deleted.


## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 DeleteVpc

 |
|VpcId|String|Yes| The ID of the VPC.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DeleteVpc
&VpcId=vpc-25eq58pl3
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <DeleteVpcResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
    </DeleteVpcResponse>
    ```

-   JSON format

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    }
    ```


