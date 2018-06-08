# ModifyRouterInterfaceSpec {#reference_i4w_xmt_ndb .reference}

修改路由器接口的规格。

调用本接口后，路由器接口进入Activating状态，激活成功后进入Active状态。

**说明：** 无法修改处于欠费状态的路由器接口的规格。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyRouterInterfaceSpec

 |
|RegionId|String|是| 路由器接口所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|RouterInterfaceId|String|是| 路由器接口的ID。

 |
|Spec|String|是| 路由器接口的规格。

 |
|ClientToken|String|否| 客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|Spec|String|路由器接口的规格。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyRouterInterfaceSpec
&RegionId=cn-hangzhou
&Spec=Middle.2
&RouterInterfaceId=ri-2ze7fbuohm7pcxxxxxx
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <ModifyRouterInterfaceSpecResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
        <Spec>Middle.2</Spec>
    </ModifyRouterInterfaceSpecResponse>
    ```

-   JSON格式

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0",
        "Spec":"Middle.2" 
    }
    ```


