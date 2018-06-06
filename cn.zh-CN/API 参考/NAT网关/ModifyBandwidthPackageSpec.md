# ModifyBandwidthPackageSpec {#reference_i4w_xmt_ndb .reference}

修改指定NAT带宽包的带宽。

**说明：** 本接口仅支持在2017年11月3日之前账号下存在NAT带宽包的用户调用。2017年11月3日之前账号下不存在NAT带宽包的用户，请绑定EIP，详情参见[AssociateEipAddress](cn.zh-CN/API 参考/NAT网关/AssociateEipAddress.md#)。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyBandwidthPackageSpec

 |
|RegionId|String|是| NAT带宽包所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|BandwidthPackageId|String|是| NAT带宽包的ID。

 |
|Bandwidth|Integer|是| NAT带宽包的带宽。取值范围：\[5,1000\]

 |
|ClientToken|String|否| 客户端token，用于保证请求的幂等性。

 由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyBandwidthPackageSpec
&BandwidthPackageId=bwp-11odxu2k7
&RegionId=cn-shanghai
&Bandwidth=200
&IpCount=1
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <ModifyBandwidthPackageSpecResponse>
    	<RequestId>2315DEB7-5E92-423A-91F7-4C1EC9AD97C3</RequestId>
    </ModifyBandwidthPackageSpecResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": "54ED4074-3F89-4F11-B166-837DD3E20FE3"
    }
    ```


