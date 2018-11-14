# ActivateRouterInterface {#reference_i4w_xmt_ndb .reference}

激活处于Inactive状态的路由器接口。

调用本接口后，路由器接口进入Activating状态，激活成功后进入Active状态。

**说明：** 无法激活处于欠费状态的路由器接口。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ActivateRouterInterface

 |
|RegionId|String|是| 路由器接口所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|RouterInterfaceId|String|是| 路由器接口的ID。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ActivateRouterInterface
&RegionId=cn-hangzhou
&RouterInterfaceId=ri-sf3rxsf
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <ActivateRouterInterfaceResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
    </ActivateRouterInterfaceResponse>
    ```

-   JSON格式

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    }
    ```


