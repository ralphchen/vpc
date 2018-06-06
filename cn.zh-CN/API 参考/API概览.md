# API概览 {#reference_lhp_jgh_qdb .reference}

本文档汇总了VPC所有可调用的API，具体接口信息请参阅相关文档。关于更多API资源，请访问[API Explorer](https://api.aliyun.com/)。

## 弹性公网IP接口 {#section_gzn_ty2_sdb .section}

|API|描述|
|:--|:-|
|AllocateEipAddress|申请弹性公网IP（EIP）。|
|AssociateEipAddress|将EIP绑定到同地域的云产品实例上。|
|UnassociateEipAddress|解除EIP与云产品实例的绑定关系。|
|DescribeEipAddresses|查询指定地域已创建的EIP。|
|ModifyEipAddressAttribute|修改指定EIP的名称、描述信息和带宽峰值。|
|ReleaseEipAddress|释放指定的EIP。|

## 专有网络接口 {#section_wqg_4cf_sdb .section}

|API|描述|
|:--|:-|
|CreateVpc|创建一个专有网络（VPC）。|
|DeleteVpc|删除一个专有网络（VPC）。|
|DescribeVpcs|查询已创建的VPC。|
|ModifyVpcAttribute|修改指定VPC的名称和描述信息。|

## 路由器接口 {#section_ryw_wcf_sdb .section}

|API|描述|
|:--|:-|
|DescribeVRouters|查询指定地域的路由器列表。|
|ModifyVRouterAttribute|修改路由器的名称和描述信息。|

## 交换机接口 {#section_nzg_fdf_sdb .section}

|API|描述|
|:--|:-|
|CreateVSwitch|创建一个交换机。|
|DeleteVSwitch|删除指定的交换机。|
|DescribeVSwitches|查询已创建的交换机。|
|ModifyVSwitchAttribute|修改指定交换机的名称和描述信息。|

## 路由表接口 {#section_gtv_qdf_sdb .section}

|API|描述|
|:--|:-|
|CreateRouteEntry|在VPC路由器或边界路由器（VBR）上创建自定义路由条目。|
|DeleteRouteEntry|删除VPC路由器或边界路由器的路由表中的路由条目。|
|DescribeRouteTables|查询路由表的路由条目。|

## NAT网关接口 {#section_gzy_wdf_sdb .section}

|API|描述|
|:--|:-|
|CreaeNatGateway|创建一个NAT网关。|
|DescribeNatGateways|查询已创建的NAT网关。|
|ModifyBandwidthPackageSpec|修改一个NAT网关。|
|ModifyNatGatewayAttribute|修改NAT网关配置。|
|DeleteNatGateway|删除指定的NAT网关。|
|CreateBandwidthPackage|创建NAT带宽包。|
|DescribeBandwidthPackages|查询指定地域的NAT带宽包。|
|ModifyBandwidthPackageSpec|修改指定NAT带宽包的带宽。|
|ModifyBandwidthPackageAttribute|修改指定NAT带宽包的名称和描述。|
|AddBandwidthPackageIps|修改NAT带宽包-增加公网IP。|
|RemoveBandwidthPackageIps|修改NAT带宽包-减少公网IP。|
|DeleteBandwidthPackage|删除NAT带宽包。|
|CreateForwardEntry|在DNAT列表中添加DNAT条目。|
|DescribeForwardTableEntries|查询已创建的DNAT条目。|
|ModifyForwardEntry|修改指定的DNAT条目。|
|DeleteForwardEntry|删除指定的DNAT条目。|
|CreateSnatEntry|在SNAT列表中添加SNAT条目。|
|DescribeSnatTableEntries|查查询已创建的SNAT条目。|
|ModifySnatEntry|修改指定的SNAT条目。|
|DeleteSnatEntry|删除指定的SNAT条目。|

## VPN接口 {#section_u2q_y2f_sdb .section}

|API|描述|
|:--|:-|
|CreateVpnGateway|创建一个VPN网关。|
|DescribeVpnGateways|查询已创建的VPN网关。|
|DescribeVpnGateway|查询指定VPN网关的详细信息。|
|ModifyVpnGatewayAttribute|修改VPN网关的名称和描述信息。|
|DeleteVpnGateway|删除指定的VPN网关。|
|CreateCustomerGateway|创建用户网关。|
|DescribeCustomerGateways|查询已创建的用户网关。|
|DescribeCustomerGateway|查询已创建的用户网关的详细信息。|
|DeleteCustomerGateway|删除指定的用户网关。|
|ModifyCustomerGatewayAttribute|修改用户网关的名称和描述信息。|
|CreateVpnConnection|创建IPsec连接。|
|DescribeVpnConnections|查询已创建的IPsec连接。|
|DescribeVpnConnection|查询已创建的IPsec连接的详细信息。|
|ModifyVpnConnectionAttribute|修改IPsec连接的配置信息。|
|DeleteVpnConnection|删除指定的IPsec连接。|
|DownloadVpnConnectionConfig|获取IPsec连接的配置信息。|
|CreateSslVpnServer|创建SSL-VPN服务端。|
|DescribeSslVpnServers|查询已创建的SSL-VPN服务端。|
|DeleteSslVpnServer|删除SSL-VPN服务端。|
|ModifySslVpnServer|修改SSL-VPN服务端的配置信息。|
|CreateSslVpnClientCert|创建SSL-VPN客户端证书。|
|DescribeSslVpnClientCerts|查询已创建的SSL-VPN客户端证书。|
|DeleteSslVpnClientCert|删除SSL-VPN客户端证书。|
|ModifySslVpnClientCert|修改SSL-VPN客户端证书的名称。|

## 地域接口 {#section_wny_1hf_sdb .section}

|API|描述|
|:--|:-|
|DescribeRegions|查询可用地域。|
|DescribeZones|查询可用区。|
|DescribeAccessPoints|查询指定地域中的物理专线接入点。|

## 监控接口 {#section_p3d_23f_sdb .section}

|API|描述|
|:--|:-|
|DescribeBandwidthPackagePublicIpMonitorData|查询NAT带宽包中指定公网IP的监控数据。|
|DescribeEipMonitorData|查看弹性公网 IP 的监控信息。|

## 物理专线接口 {#section_enz_bjf_sdb .section}

|API|描述|
|:--|:-|
|CreatePhysicalConnection|申请物理专线接入。|
|CancelPhysicalConnection|在物理专线开通前取消物理专线接入，取消后物理专线进入Canceled状态。|
|DescribePhysicalConnections|查询指定地域内的物理专线。|
|ModifyPhysicalConnectionAttribute|修改物理专线的配置。|
|TerminatePhysicalConnection|在物理专线开通后终止物理专线接入。调用本接口后物理专线进入Terminating状态，处理完成后进入Terminated状态。|
|EnablePhysicalConnection|开通处于Confirmed状态的物理专线，开通完成后物理专线进入Enabled状态。|
|DeletePhysicalConnection|删除物理专线。|

## 边界路由器接口 {#section_cyv_3kf_sdb .section}

|API|描述|
|:--|:-|
|CreateVirtualBorderRouter|新建虚拟边界路由器（VBR）。|
|DeleteVirtualBorderRouter|删除边界路由器（VBR）。|
|DescribeVirtualBorderRouters|查询已创建的边界路由器（VBR）。|
|DescribeVirtualBorderRoutersForPhysicalConnection|查询指定物理专线下的边界路由器（VBR），包括物理专线所有者的VBR和其他账号的VBR。|
|ModifyVirtualBorderRouterAttribute|修改边界路由器（VBR）的配置。|
|TerminateVirtualBorderRouter|终止边界路由器（VBR）。|
|RecoverVirtualBorderRouter|恢复被终止的边界路由器（VBR）。|

## 路由器接口接口 {#section_xq4_glf_sdb .section}

|API|描述|
|:--|:-|
|CreateRouterInterface|创建路由器接口。|
|DescribeRouterInterfaces|查询指定地域内的路由器接口。|
|ConnectRouterInterface|由发起端路由器接口向接收端发起连接。|
|ActivateRouterInterface|激活处于Inactive状态的路由器接口。|
|DeactivateRouterInterface|冻结路由器接口。|
|ModifyRouterInterfaceSpec|修改路由器接口规格。|
|ModifyRouterInterfaceAttribute|修改路由器接口的配置。|
|DeleteRouterInterface|删除路由器接口。|

## BGP接口 {#section_a25_yqx_sdb .section}

|API|描述|
|:--|:-|
|CreateBgpGroup|为指定的边界路由器（VBR）创建一个BGP组。|
|DescribeBgpGroups|查询指定地域下的BGP组。|
|ModifyBgpGroupAttribute|修改BGP组的配置。|
|DeleteBgpGroup|删除指定的BGP组。|
|CreateBgpPeer|向指定的BGP组中添加BGP邻居。|
|DescribeBgpPeers|查询指定地域下的BGP邻居。|
|DeleteBgpPeer|删除指定的BGP邻居。|
|AddBgpNetwork|宣告BGP网络。|
|DeleteBgpNetwork|删除已宣告的BGP网络。|
|DescribeBgpNetworks|查询已宣告的BGP网络。|

## 共享带宽接口 {#section_z53_51y_sdb .section}

|API|描述|
|:--|:-|
|AddCommonBandwidthPackageIp|添加EIP到共享带宽中。|
|CreateCommonBandwidthPackage|创建共享带宽。|
|DeleteCommonBandwidthPackage|删除共享带宽包。|
|DescribeCommonBandwidthPackages|查询指定地域中共享带宽的列表。|
|ModifyCommonBandwidthPackageAttribute|修改共享带宽的名称和描述信息。|
|ModifyCommonBandwidthPackagePayType|将共享带宽的付费类型从后付费转换为预付费。|
|ModifyCommonBandwidthPackageSpec|更改共享带宽的带宽峰值。|
|RemoveCommonBandwidthPackageIp|移除共享带宽中的EIP。|

## 全球加速接口 {#section_s2c_rby_sdb .section}

|API|描述|
|:--|:-|
|CreateGlobalAccelerationInstance|创建全球加速实例。|
|DescribeGlobalAccelerationInstances|查询已创建的全球加速实例的列表。|
|ModifyGlobalAccelerationInstanceAttributes|修改全球加速实例的名称和描述信息。|
|ModifyGlobalAccelerationInstanceSpec|修改全球加速实例的带宽。|
|DeleteGlobalAccelerationInstance|删除全球加速实例。|
|AssociateGlobalAccelerationInstance|绑定后端服务实例。|
|UnassociateGlobalAccelerationInstance|解绑与全球加速实例关联的后端服务实例。|
|DescribeServerRelatedGlobalAccelerationInstances|查询与指定后端服务实例关联的全球加速实例。|

