# ModifyVSwitchAttribute {#reference_i4w_xmt_ndb .reference}

Modifies the name and description of the specified switch.

## Request parameters {#section_cch_pjg_mdb .section}

|Name|Type|Required|Description|
|:---|:---|:-------|:----------|
|Action|String|Yes| The action to perform. Valid value:

 ModifyVSwitchAttribute

 |
|VSwitchId|String|Yes| The ID of the VSwitch.

 |
|VSwitchName|String|No| The name of the VSwitch.

 The name can contain from 2 to 128 characters including a-z, A-Z, 0-9, underlines, and hyphens. The name must start with an English letter, but cannot start with `http://`  or `https://`.

 |
|Description|String|No| The description of the VSwitch.

 The description can contain from 2 to 256 characters. The description must start with English letters, but cannot start with `http://` or `https://`.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Name|Type|Description|
|:---|:---|:----------|
|RequestId|String|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyVSwitchAttribute
&VSwitchId=vsw-25naue4gz
&VSwitchName=VS02
&CommonParameters
```

**Response example**

-   XML format

    ```
    <? xml version="1.0" encoding="UTF-8"? >
    <ModifyVSwitchAttributeResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
    </ModifyVSwitchAttributeResponse>
    ```

-   JSON format

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0", 
    }
    ```


