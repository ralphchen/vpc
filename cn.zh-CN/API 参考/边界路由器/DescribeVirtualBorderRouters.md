# DescribeVirtualBorderRouters {#reference_i4w_xmt_ndb .reference}

查询已创建的边界路由器（VBR）。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribeVirtualBorderRouters

 |
|RegionId|String|是| VBR所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|Filter.n.Key|String|否| 过滤条件，最多可提供5个过滤条件。n的取值范围为\[1,5\]。

 每个过滤条件（filter key）可以提供多个值，多个值之间是“or”关系，即只要与其中一个值符合则视为符合参数的过滤条件。

 各个过滤条件（filter key）之间为“and”逻辑关系，即符合所有参数的过滤条件，才会被查询出来。

 支持的过滤条件如下：

-   PhysicalConnectionId：物理专线ID。

-   VbrId：VBR ID。

-   Status：VBR的状态。

-   AccessPointId：关联的物理专线的接入点ID。

-   Name：VBR的名称。


 |
|Filter.n.Value.m|String|否| 指定的过滤条件对应的值。m的取值范围为\[1，5\]。

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
|VirtualBorderRouterSet|List|查询到的VBR合集，每个VBR的详细信息参见[表 1](#table_px2_zbt_4db) 。|

|名称|类型|描述|
|:-|:-|:-|
|VbrId|String|VBR的ID。|
|VbrOwnerUid|String|VBR所有者的账号ID，VBR和物理专线的所有者相同时该参数为空。|
|CreationTime|Integer|VBR的创建时间。|
|ActivationTime|String|VBR第一次激活的时间。|
|TerminationTime|String|VBR最近一次被终止的时间。|
|RecoveryTime|String|VBR最近一次从Terminated状态恢复到Active状态的时间。|
|Status|String|VBR的状态。|
|VlanId|String|VBR的VLAN ID。|
|CircuitCode|String|运营商为物理专线提供的电路编码。|
|RouteTableId|String|VBR的路由表的ID。|
|VlanInterfaceId|String|VBR的路由器接口的ID。|
|LocalGatewayIp|String|阿里云侧互联IP。|
|PeerGatewayIp|String|客户侧互联IP。|
|PeeringSubnetMask|String|阿里云侧互联IP和客户侧互联IP的子网掩码。|
|Name|String|VBR的名称。|
|Description|String|VBR的描述信息。|
|PhysicalConnectionId|String|VBR所属的物理专线的ID。|
|AccessPointId|String|物理专线接入点的ID。|
|Status|String|物理专线状态：-   Initial：申请中

-   Approved：审批通过

-   Allocating：正在分配资源

-   Allocated：接入施工中。

-   Confirmed：等待用户确认

-   Enabled：已开通

-   Rejected：申请被拒绝

-   Canceled：已取消

-   Allocation Failed：资源分配失败

-   Terminated：已终止


|
|BusinessStatus|String|物理专线的付费状态：-   Normal：正常

-   FinancialLocked：欠费锁定

-   SecurityLocked：因安全原因被锁定


|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribeVirtualBorderRouters
&RegionId=cn-beijing
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DescribeVirtualBorderRoutersResponse>
    	<RequestId>AE65530E-8436-4FB1-8217-DCD35712AC89</RequestId>
    	<PageNumber>1</PageNumber>
    	<VirtualBorderRouterSet>
    		<VirtualBorderRouterType>
    			<LocalGatewayIp>10.1.1.1</LocalGatewayIp>
    			<PeerGatewayIp>10.2.2.2</PeerGatewayIp>
    			<Description></Description>
    			<PhysicalConnectionOwnerUid>1231579085529123</PhysicalConnectionOwnerUid>
    			<VlanId>10</VlanId>
    			<RecoveryTime></RecoveryTime>
    			<PhysicalConnectionStatus>Enabled</PhysicalConnectionStatus>
    			<PhysicalConnectionId>pc-2zeoaxkq3jot5p71qcnuy</PhysicalConnectionId>
    			<RouteTableId>vtb-2ze9hmd6yofwvb1dd79j9</RouteTableId>
    			<PeeringSubnetMask>255.0.0.0</PeeringSubnetMask>
    			<TerminationTime></TerminationTime>
    			<Name></Name>
    			<CreationTime>2018-03-06T11:16:34Z</CreationTime>
    			<ActivationTime>2018-03-06T11:16:34Z</ActivationTime>
    			<CircuitCode></CircuitCode>
    			<Status>active</Status>
    			<PhysicalConnectionBusinessStatus>Normal</PhysicalConnectionBusinessStatus>
    			<VlanInterfaceId>ri-2zeum6rgu0586gjrocikm</VlanInterfaceId>
    			<AccessPointId>ap-cn-beijing-dx-A</AccessPointId>
    			<VbrId>vbr-2zecmmvg5gvu8i4telkhw</VbrId>
    		</VirtualBorderRouterType>
    	</VirtualBorderRouterSet>
    	<TotalCount>1</TotalCount>
    	<PageSize>10</PageSize>
    </DescribeVirtualBorderRoutersResponse>
    ```

-   JSON格式

    ```
    {
      "PageNumber": 1,
      "VirtualBorderRouterSet": {
        "VirtualBorderRouterType": [
          {
            "LocalGatewayIp": "10.1.1.1",
            "PeerGatewayIp": "10.2.2.2",
            "Description": "",
            "PhysicalConnectionOwnerUid": "1231579085xxxx",
            "VlanId": 10,
            "RecoveryTime": "",
            "PhysicalConnectionStatus": "Enabled",
            "PhysicalConnectionId": "pc-2zeoaxkq3jotxxxxx",
            "RouteTableId": "vtb-2ze9hmd6yofwxxxxxx",
            "PeeringSubnetMask": "255.0.0.0",
            "TerminationTime": "",
            "Name": "",
            "CreationTime": "2018-03-06T11:16:34Z",
            "ActivationTime": "2018-03-06T11:16:34Z",
            "CircuitCode": "",
            "Status": "active",
            "PhysicalConnectionBusinessStatus": "Normal",
            "VlanInterfaceId": "ri-2zeum6rgu058xxxxxx",
            "AccessPointId": "ap-cn-beijing-dx-A",
            "VbrId": "vbr-2zecmmvg5gvuxxxxxx"
          }
      "TotalCount": 1,
      "PageSize": 10,
      "RequestId": "98B24329-ADC9-4725-A5F8-6C1B282DA17D"
    }
    ```


