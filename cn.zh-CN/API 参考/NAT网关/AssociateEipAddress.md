# AssociateEipAddress {#reference_i4w_xmt_ndb .reference}

将EIP绑定到同地域的云产品实例上。

**说明：** 

-   EIP可绑定到同地域的专有网络ECS实例、专有网络的SLB实例和NAT网关上。本文档介绍如何使用该接口将EIP绑定到NAT网关上，关于该接口的详细信息，参见[AssociateEipAddress](cn.zh-CN/API 参考/弹性公网IP/AssociateEipAddress.md#)。

-   本接口仅支持在2017年11月3日之前账号下不存在NAT带宽包的用户调用。2017年11月3日之前账户下存在NAT带宽包的用户，请提交工单。


## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 AssociateEipAddress

 |
|AllocationId|String|是| EIP的ID。

 |
|InstanceType|String|否| 要绑定的云产品实例的类型，取值：Nat

 |
|InstanceId|String|是| NAT网关的实例ID。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=AssociateEipAddress
&AllocationId=eip-25877c70x
&InstanceId=ngw-bp1tcx67xuox8ogre7onm
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <AssociateEipAddressResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
    </AssociateEipAddressResponse>
    ```

-   JSON格式

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    }
    ```


