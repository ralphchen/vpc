# DeleteVSwitch {#reference_i4w_xmt_ndb .reference}

Delete a VSwitch.

Note the following before deleting a VSwitch:

-   Before deleting a VSwitch, you must release or remove all cloud product instances and HAVIP instances under the VSwitch.

-   Only VSwitches in the available status can be deleted.

-   A VSwitch cannot be deleted when the VPC to which it belongs is creating or deleting a VSwitch or route entry.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Value:

 DeleteVSwitch

 |
|VSwitchId|String|Yes| The ID of the VSwitch to delete.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DeleteVSwitch
&VSwitchId=vsw-25naue4gz
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <DeleteVSwitchResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
    </DeleteVSwitchResponse>
    ```

-   JSON format

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    }
    ```


