# DescribePhysicalConnections {#reference_i4w_xmt_ndb .reference}

查询指定地域内的物理专线。

## 请求参数 {#section_cch_pjg_mdb .section}

|名称|类型|是否必须|描述|
|:-|:-|:---|:-|
|Action|String|是| 要执行的操作。 取值：

 DescribePhysicalConnections

 |
|RegionId|String|是| 物理专线所在的地域。

 您可以通过调用 DescribeRegions接口获取地域ID。

 |
|Filter.n.Key|String|否| 过滤条件，最多可提供5个过滤条件。n的取值范围为\[1,5\]。

 每个过滤条件（filter key）可以提供多个值，多个值之间是“or”关系，即只要与其中一个值符合则视为符合参数的过滤条件。

 各个过滤条件（filter key）之间为“and”逻辑关系，即符合所有参数的过滤条件，才会被查询出来。

 支持的过滤条件如下：

-   PhysicalConnectionId：物理专线ID。

-   AccessPointId：接入点ID。

-   Type：物理专线的类型，默认值是VPC。

-   LineOperator：物理线路的运营商。

-   Status：物理专线的状态。

-   Spec：物理专线的规格。

-   Name：物理专线的名称。


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
|PhysicalConnectionSet|JSON String|物理专线的详细信息。|
|PhysicalConnectionSet元素|
|PhysicalConnectionId|String|物理专线的ID。|
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
|CreationTime|String|物理专线的创建时间。|
|EnabledTime|String|物理专线的开通时间。|
|LineOperator|String| 提供接入物理线路的运营商：

-   CT：中国电信

-   CU：中国联通

-   CM：中国移动

-   CO：中国其他

-   Equinix：Equinix

-   Other：境外其他


 |
|Spec|String|物理专线的规格。|
|PeerLocation|String|本地数据中心的地理位置。|
|PortType|String|物理专线接入端口类型：-   100Base-T：百兆电口

-   1000Base-T（默认值）：千兆电口

-   1000Base-LX：千兆单模光口（10千米）

-   10GBase-T：万兆电口

-   10GBase-LR：万兆单模光口（10千米）


|
|RedundantPhysicalConnectionId|String|冗余物理专线的ID。|
|Name|String|物理专线的名称。|
|Description|String|物理专线的描述。|
|ADLocation|String|专线接入设备所在的位置。|
|PortNumber|String|专线接入设备的端口号。|
|CircuitCode|String|运营商为物理专线提供的电路编码。|
|Bandwidth|String|物理专线的带宽。|

## 示例 {#section_ix5_h1g_cz .section}

**请求示例**

``` {#createVPCpub}
https://vpc.aliyuncs.com/?Action=DescribePhysicalConnections
&RegionId=cn-beijing
&公共请求参数
```

**返回示例**

-   XML格式

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <DescribePhysicalConnectionsResponse>
    	<PageNumber>1</PageNumber>
    	<TotalCount>1</TotalCount>
    	<PageSize>10</PageSize>
    	<RequestId>7C07B0AF-4FC0-4BB2-9667-F75812824BCD</RequestId>
    	<PhysicalConnectionSet>
    		<PhysicalConnectionType>
    			<Type>VPC</Type>
    			<PhysicalConnectionId>pc-2zeoaxkq3jot5p71qcnuy</PhysicalConnectionId>
    			<PeerLocation>XXX-XX区--XXX路</PeerLocation>
    			<CreationTime>2017-12-13T02:28:42Z</CreationTime>
    			<Name>TEST</Name>
    			<Status>Enabled</Status>
    			<AdLocation>XXX--XX-XXX机房XX机柜XXU</AdLocation>
    			<EnabledTime>2017-12-18T04:01:30Z</EnabledTime>
    			<BusinessStatus>Normal</BusinessStatus>
    			<LineOperator>CT</LineOperator>
    			<PortNumber>1/1/4</PortNumber>
    			<AccessPointId>ap-cn-beijing-dx-A</AccessPointId>
    			<PortType>100Base-T</PortType>
    			<Bandwidth>2</Bandwidth>
    		</PhysicalConnectionType>
    	</PhysicalConnectionSet>	
    </DescribePhysicalConnectionsResponse>
    ```

-   JSON格式

    ```
    {
      "PageNumber": 1,
      "TotalCount": 1,
      "PageSize": 10,
      "RequestId": "7C07B0AF-4FC0-4BB2-9667-F75812824BCD",
      "PhysicalConnectionSet": {
        "PhysicalConnectionType": [
          {
            "Type": "VPC",
            "PhysicalConnectionId": "pc-2zeoaxkq3jot5p71qcnuy",
            "PeerLocation": "XXX-XX区--XXX路",
            "CreationTime": "2017-12-13T02:28:42Z",
            "Name": "TEST",
            "Status": "Enabled",
            "AdLocation": "XXX--XX-XXX机房XX机柜XXU",
            "EnabledTime": "2017-12-18T04:01:30Z",
            "BusinessStatus": "Normal",
            "LineOperator": "CT",
            "PortNumber": "1/1/4",
            "AccessPointId": "ap-cn-beijing-dx-A",
            "PortType": "100Base-T",
            "Bandwidth": 2
          }
        ]
      }
    }
    ```


