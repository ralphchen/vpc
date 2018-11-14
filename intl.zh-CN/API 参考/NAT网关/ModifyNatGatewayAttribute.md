# ModifyNatGatewayAttribute {#reference_i4w_xmt_ndb .reference}

修改NAT网关配置。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 ModifyNatGatewayAttribute

 |
|RegionId|String|是| NAT网关所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|NatGatewayId|String|是| NAT网关的ID。

 |
|Name|String|否| NAT网关的名称。

 长度为 2-128个字符，必须以字母或中文开头，可包含数字，点号（.），下划线（\_）和短横线（-）。但不能以`http://` 或`https://`开头。

 |
|Description|String|否| NAT网关的描述信息。

 长度为 2-256个字符，必须以字母或中文开头，但不能以`http://` 或`https://`开头。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=ModifyNatGatewayAttribute
&RegionId=cn-shanghai
&NatGatewayId=ngw-7mwb327j1
&Name=test
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8" ?>
    <ModifyNatGatewayAttributeResponse>
    	<RequestId>2315DEB7-5E92-423A-91F7-4C1EC9AD97C3</RequestId>
    </ModifyNatGatewayAttributeResponse>
    ```

-   JSON格式

    ```
    {
      "RequestId": "2315DEB7-5E92-423A-91F7-4C1EC9AD97C3"
    }
    ```


