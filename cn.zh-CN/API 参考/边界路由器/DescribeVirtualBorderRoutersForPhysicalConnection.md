# DescribeVirtualBorderRoutersForPhysicalConnection {#reference_i4w_xmt_ndb .reference}

查询指定物理专线下的边界路由器（VBR），包括物理专线所有者的VBR和其他账号的VBR。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeVirtualBorderRoutersForPhysicalConnection

 |
|RegionId|String|是| 物理专线所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|PhysicalConnectionId|String|否| 物理专线的ID。

 |
|PageNumber|Integer|否| 列表的页码，默认值为1。

 |
|PageSize|Integer|否| 分页查询时每页的行数，最大值为50，默认值为10。

 |

## 返回参数 {#section_ugs_f1g_cz .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|请求ID。|
|TotalCount|String|列表条条目数。|
|PageNumber|Integer|当前页码。|
|PageSize|String|每页包含多少条目。|
|VirtualBorderRouterForPhysicalConnectionSet|List|查询到的VBR合集 。|

|名称|类型|描述|
|:-|:-|:-|
|VbrId|String|VBR的ID。|
|VbrOwnerUid|String|VBR所有者的账号ID，VBR和物理专线的所有者相同时该参数为空。|
|CreationTime|Integer|VBR的创建时间。|
|ActivationTime|String|VBR第一次激活的时间。|
|TerminationTime|String|VBR最近一次被终止的时间。|
|RecoveryTime|String|VBR最近一次从Terminated状态恢复到Active状态的时间。|
|VlanId|String|VBR的VLAN ID。|
|CircuitCode|String|运营商为物理专线提供的电路编码。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeVirtualBorderRoutersForPhysicalConnection
&RegionId=cn-beijing
&PhysicalConnectionId=pc-2zeoaxkq3joxxxx
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DescribeVirtualBorderRoutersForPhysicalConnectionResponse>
    	<RequestId>03E8CB87-5876-4034-BBB2-6E0851281C37</RequestId>
    	<PageNumber>1</PageNumber>
    	<TotalCount>2</TotalCount>
    	<PageSize>10</PageSize>
    	<VirtualBorderRouterForPhysicalConnectionSet>
    		<VirtualBorderRouterForPhysicalConnectionType>
    			<ActivationTime>2018-03-06T11:16:34Z</ActivationTime>
    			<CreationTime>2018-03-06T11:16:34Z</CreationTime>
    			<CircuitCode></CircuitCode>
    			<VlanId>10</VlanId>
    			<RecoveryTime></RecoveryTime>
    			<VbrOwnerUxxx231579085529123</VbrOwnerUid>
    			<TerminationTime></TerminationTime>
    			<VbrId>Vbrxxxxx-2zecmmvg5gvu8i4telkhw</VbrId>
    		</VirtualBorderRouterForPhysicalConnectionType>
    		<VirtualBorderRouterForPhysicalConnectionType>
    			<ActivationTime>2018-01-04T13:34:18Z</ActivationTime>
    			<CreationTime>2018-01-04T13:34:18Z</CreationTime>
    			<CircuitCode></CircuitCode>
    			<VlanId>100</VlanId>
    			<RecoveryTime></RecoveryTime>
    			<VxxxbrOwnerUid>1231579085529123</VbrOwnerUid>
    			<TerminationTime></TerminationTime>
    			<VbrId>vbr-2zee2e2cwetx4k0tohakw</VbrId>
    		</VirtualBorderRouterForPhysicalConnectionType>
    </DescribeVirtualBorderRoutersForPhysicalConnectionResponse>
    ```

-   JSON格式

    ```
    {
        "PageNumber": 1, 
        "TotalCount": 2, 
        "PageSize": 10, 
        "RequestId": "03E8CB87-5876-4034-BBB2-6E0851281C37", 
        "VirtualBorderRouterForPhysicalConnectionSet": {
            "VirtualBorderRouterForPhysicalConnectionType": [
                {
                    "ActivationTime": "2018-03-06T11:16:34Z", 
                    "CreationTime": "2018-03-06T11:16:34Z", 
                    "CircuitCode": "", 
                    "VlanId": 10, 
                    "RecoveryTime": "", 
                    "VbrOwnerUid": "1231579085xxxxxx529123", 
                    "TerminationTime": "", 
                    "VbrId": "vbr-2zecmmvg5gvu8xxxxw"
                }, 
                {
                    "ActivationTime": "2018-01-04T13:34:18Z", 
                    "CreationTime": "2018-01-04T13:34:18Z", 
                    "CircuitCode": "", 
                    "VlanId": 100, 
                    "RecoveryTime": "", 
                    "VbrOwnerUid": "1231579085xxx", 
                    "TerminationTime": "", 
                    "VbrId": "vbr-2zee2e2cwetx4k0txxxxakw"
                }
            ]
        }
    }
    ```


