# AddBgpNetwork {#reference_i4w_xmt_ndb .reference}

宣告BGP网络。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 AddBgpNetwork

 |
|RegionId|String|是| VBR组所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|DstCidrBlock|String|是| 需要和本地IDC互连的VPC或交换机的网段。

 |
|RouterId|String|是| VBR的ID。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=AddBgpNetwork
&RegionId=cn-beijing
&RouterId=vbr-2zeff11o2sqhnp1u7ci93
&DstCidrBlock=10.0.0.0/24
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <AddBgpNetworkResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
    </AddBgpNetworkResponse>
    ```

-   JSON格式

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    }
    ```


