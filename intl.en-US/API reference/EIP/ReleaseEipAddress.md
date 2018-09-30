# ReleaseEipAddress {#reference_i4w_xmt_ndb .reference}

Release the specified EIP.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 ReleaseEipAddress

 |
|AllocationId|String|Yes| The ID of the EIP.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ReleaseEipAddress
&AllocationId=eip-25877c70x
&CommonParameters
```

**Response example**

-   XML format

    ```
    <<? xml version="1.0" encoding="UTF-8" ? >
    <ReleaseEipAddressResponse>
        <RequestId>748C38F6-9A3D-482E-83FB-DB6C39C68AEA</RequestId>
    </ReleaseEipAddressResponse>
    ```

-   JSON format

    ```
    {
      "RequestId": "748C38F6-9A3D-482E-83FB-DB6C39C68AEA"
    }
    ```


