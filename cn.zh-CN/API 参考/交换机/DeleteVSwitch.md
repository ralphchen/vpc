# DeleteVSwitch {#reference_i4w_xmt_ndb .reference}

删除交换机。

调用该接口删除交换机时，请注意：

-   删除交换机之前，需要先释放或移走VPC内的所有资源，包括交换机，云产品实例，路由器接口，HAVIP等。

-   只有处于Available状态的交换机可以被删除。

-   交换机所在的VPC正在创建/删除交换机或路由条目时，无法删除交换机。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|Yes| 要执行的操作。 取值：

 DeleteVSwitch

 |
|VSwitchId|String|Yes| 要删除的交换机的ID。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|The ID of the request.|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DeleteVSwitch
&VSwitchId=vsw-25naue4gz
&CommonParameters
```

**返回示例**

-   XML 格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DeleteVSwitchResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
    </DeleteVSwitchResponse>
    ```

-   JSON 格式

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    }
    ```


