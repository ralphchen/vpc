# ModifyBandwidthPackageAttribute {#reference_i4w_xmt_ndb .reference}

修改指定NAT带宽包的名称和描述。

**说明：** 本接口仅支持在2017年11月3日之前账号下存在NAT带宽包的用户调用。2017年11月3日之前账号下不存在NAT带宽包的用户，请绑定EIP，详情参见[AssociateEipAddress](cn.zh-CN/API 参考/NAT网关/AssociateEipAddress.md#)。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyBandwidthPackageAttribute

 |
|RegionId|String|是| NAT带宽包所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|BandwidthPackageId|String|是| NAT带宽包的ID。

 |
|Name|String|否| NAT带宽包的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|Description|String|否| NAT带宽包的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com?Action=ModifyBandwidthPackageAttribute
&BandwidthPackageId=bwp-s6lmotmkk
&Name=modified
&RegionId=cn-shanghaie
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <ModifyBandwidthPackageAttributeResponse>
    	<RequestId>2315DEB7-5E92-423A-91F7-4C1EC9AD97C3</RequestId>
    </ModifyBandwidthPackageAttributeResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": "54ED4074-3F89-4F11-B166-837DD3E20FE3"
    }
    ```


