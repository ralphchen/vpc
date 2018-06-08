# DeleteVpc {#reference_i4w_xmt_ndb .reference}

删除一个专有网络（VPC）。

调用该接口创建VPC时，请注意：

-   删除VPC之前，需要先释放或移走VPC内的所有资源，包括交换机，云产品实例，路由器接口，HAVIP等。

-   只有处于Available状态的VPC才可以被删除。


## 请求参数 {#section_cch_pjg_mdb .section}

|删除

名称|类型|是否必须|描述|
|:-----|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DeleteVpc

 |
|VpcId|String|是| 要删除的VPC的ID。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DeleteVpc
&VpcId=vpc-25eq58pl3
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DeleteVpcResponse>
        <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
    </DeleteVpcResponse>
    ```

-   JSON格式

    ```
    { 
        "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
    }
    ```


