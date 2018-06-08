# ConnectRouterInterface {#reference_i4w_xmt_ndb .reference}

由发起端路由器接口向接收端发起连接。

调用本接口后路由器接口进入Connecting状态，连接完成后进入Active状态。

调用该接口创建VPC时，请注意：

-   只能由状态为Idle的发起端路由器接口向接收端发起连接。

-   任意两个路由器之间，最多只能存在一对相互连接的路由器接口。

-   如果账号下存在处于欠费状态的路由器接口，无法进行发起连接。


## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ConnectRouterInterface

 |
|RegionId|String|是| 路由器接口所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|RouterInterfaceId|String|是| 发起端路由器接口的ID。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ConnectRouterInterface
&RegionId=cn-hangzhou
&RouterInterfaceId=ri-sf3rxsf
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <ConnectRouterInterfaceResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
    </ConnectRouterInterfaceResponse>
    ```

-   JSON格式

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    }
    ```


