# API overview {#reference_lhp_jgh_qdb .reference}

This document summarizes all callable VPC APIs. For detailed API information, see related documents. For more information, see [API Explorer](https://api.aliyun.com/).

## VPC {#section_wqg_4cf_sdb .section}

|API|Description|
|:--|:----------|
|CreateVpc|Create a VPC.|
|DeleteVpc|Delete a VPC.|
|DescribeVpcs|Query created VPCs.|
|ModifyVpcAttribute|Modify the name and description of a VPC.|

## Router interface {#section_ryw_wcf_sdb .section}

|API|Description|
|:--|:----------|
|DescribeVRouters|Query the list of VRouters in a region.|
|ModifyVRouterAttribute|Modify the name and description of a VRouter.|

## VSwitch {#section_nzg_fdf_sdb .section}

|API|Description|
|:--|:----------|
|CreateVSwitch|Create a VSwitch.|
|DeleteVSwitch|Delete a VSwitch.|
|DescribeVSwitches|Query created VSwitches.|
|ModifyVSwitchAttribute|Modify the name and description of a VSwitch.|

## Route table {#section_gtv_qdf_sdb .section}

|API|Description|
|:--|:----------|
|CreateRouteEntry|Create a custom route entry on a VRouter or VBR.|
|DeleteRouteEntry|Delete a route entry in the route table of a VRouter or VBR.|
|DescribeRouteTables|Query route entries in a route table.|

## EIP {#section_gzn_ty2_sdb .section}

|API|Description|
|:--|:----------|
|AllocateEipAddress|Create an EIP.|
|AssociateEipAddress|Bind an EIP to a cloud product instance in the same region.|
|UnassociateEipAddress|Unbind an EIP from a cloud product instance.|
|DescribeEipAddresses|Query created EIPs in a region.|
|ModifyEipAddressAttribute|Modify the name, description, and peak bandwidth of an EIP.|
|ReleaseEipAddress|Release an EIP.|

## NAT Gateway {#section_gzy_wdf_sdb .section}

|API|Description|
|:--|:----------|
|CreaeNatGateway|Create a NAT Gateway.|
|DescribeNatGateways|Query created NAT Gateways.|
|ModifyBandwidthPackageSpec|Modify a NAT Gateway.|
|ModifyNatGatewayAttribute|Modify the configurations of a NAT Gateway.|
|DeleteNatGateway|Delete a NAT Gateway.|
|CreateBandwidthPackage|Create a NAT bandwidth package.|
|DescribeBandwidthPackages|Query NAT bandwidth packages in a region.|
|ModifyBandwidthPackageSpec|Modify the bandwidth of a NAT bandwidth package.|
|ModifyBandwidthPackageAttribute|Modify the name and description of a NAT bandwidth package.|
|AddBandwidthPackageIps|Modify a NAT bandwidth package-Add public IPs.|
|RemoveBandwidthPackageIps|Modify a NAT bandwidth package-Remove public IPs.|
|DeleteBandwidthPackage|Delete a NAT bandwidth package.|
|CreateForwardEntry|Add a DNAT entry in a DNAT table.|
|DescribeForwardTableEntries|Query created DNAT entries.|
|ModifyForwardEntry|Modify a DNAT entry.|
|DeleteForwardEntry|Delete a DNAT entry.|
|CreateSnatEntry|Add an SNAT entry in a SNAT table.|
|DescribeSnatTableEntries|Query created SNAT entries in a SNAT table.|
|ModifySnatEntry|Modify an SNAT entry.|
|DeleteSnatEntry|Delete an SNAT entry.|

## VPN Gateways {#section_u2q_y2f_sdb .section}

|API|Description|
|:--|:----------|
|CreateVpnGateway|Create a VPN Gateways.|
|DescribeVpnGateways|Query created VPN Gatewayss.|
|DescribeVpnGateway|Query the detailed information of a VPN Gateways.|
|ModifyVpnGatewayAttribute|Modify the name and description of a VPN Gateways.|
|DeleteVpnGateway|Delete a VPN Gateways.|
|CreateCustomerGateway|Create a customer gateway.|
|DescribeCustomerGateways|Query created customer gateways.|
|DescribeCustomerGateway|Query the detailed information of a customer gateway.|
|DeleteCustomerGateway|Delete a customer gateway.|
|ModifyCustomerGatewayAttribute|Modify the name and description of a customer gateway.|
|CreateVpnConnection|Create an IPSec-VPN connection.|
|DescribeVpnConnections|Query created IPSec-VPN connections.|
|DescribeVpnConnection|Query the detailed information of an IPSec-VPN connection.|
|ModifyVpnConnectionAttribute|Modify the configurations of an IPSec-VPN connection.|
|DeleteVpnConnection|Delete an IPSec-VPN connection.|
|DownloadVpnConnectionConfig|Obtain the configurations of an IPSec-VPN connection.|
|CreateSslVpnServer|Create an SSL-VPN server.|
|DescribeSslVpnServers|Query created SSL-VPN servers.|
|DeleteSslVpnServer|Remove an SSL-VPN server.|
|ModifySslVpnServer|Modify the configurations of an SSL-VPN server.|
|CreateSslVpnClientCert|Create an SSL-VPN client certificate.|
|DescribeSslVpnClientCerts|Query created SSL-VPN client certificates.|
|DeleteSslVpnClientCert|Delete an SSL-VPN client certificate.|
|ModifySslVpnClientCert|Modify the name of an SSL-VPN client certificate.|

## Region {#section_wny_1hf_sdb .section}

|API|Description|
|:--|:----------|
|DescribeRegions|Query regions.|
|DescribeZones|Query zones.|
|DescribeAccessPoints|Query access points in a region.|

## Monitor {#section_p3d_23f_sdb .section}

|API|Description|
|:--|:----------|
|DescribeBandwidthPackagePublicIpMonitorData|Query the monitoring data of a public IP in the NAT bandwidth package.|
|DescribeEipMonitorData|Query the monitoring information of an EIP.|

## Physical connection {#section_enz_bjf_sdb .section}

|API|Description|
|:--|:----------|
|CreatePhysicalConnection|Create a physical connection. |
|CancelPhysicalConnection|Cancel physical connection access before the physical connection is enabled.|
|DescribePhysicalConnections|Query created physical connections in a region.|
|ModifyPhysicalConnectionAttribute|Modify the configurations of a physical connection.|
|TerminatePhysicalConnection|Terminate the access of the physical connection after the physical connection is enabled. The physical connection changes to the Terminating status after the API is called and changes to the Terminated status when the process is completed.|
|EnablePhysicalConnection|Enable the physical connection in the Confirmed status. Then the physical connection changes to the Enabled status.|
|DeletePhysicalConnection|Delete a physical connection.|

## VBR {#section_cyv_3kf_sdb .section}

|API|Description|
|:--|:----------|
|CreateVirtualBorderRouter|Create a Virtual Border Router \(VBR\).|
|DeleteVirtualBorderRouter|Delete a VBR.|
|DescribeVirtualBorderRouters|Query created Virtual Border Routers.|
|DescribeVirtualBorderRoutersForPhysicalConnection|Query the Virtual Border Routers created for a physical connection.|
|ModifyVirtualBorderRouterAttribute|Modify the configurations of a VBR.|
|TerminateVirtualBorderRouter|Terminate a Virtual Border Router \(VBR\).|
|RecoverVirtualBorderRouter|Recover a terminated VBR.|

## Router interface {#section_xq4_glf_sdb .section}

|API|Description|
|:--|:----------|
|CreateRouterInterface|Create a router interface.|
|DescribeRouterInterfaces|Query router interfaces in a region.|
|ConnectRouterInterface|The initiator router interface initiates a connection to the receiver router interface.|
|ActivateRouterInterface|Activate a router interface in the Inactive status.|
|DeactivateRouterInterface|Deactivate a router interface.|
|ModifyRouterInterfaceSpec|Modify the specification of a router interface.|
|ModifyRouterInterfaceAttribute|Modify the configurations of a router interface.|
|DeleteRouterInterface|Delete a router interface.|

## BGP {#section_a25_yqx_sdb .section}

|API|Description|
|:--|:----------|
|CreateBgpGroup|Create a BGP group for a VBR.|
|DescribeBgpGroups|Query created BGP groups in a region.|
|ModifyBgpGroupAttribute|Modify the configurations of a BGP group.|
|DeleteBgpGroup|Delete a BGP group.|
|CreateBgpPeer|Add a BGP peer to a BGP group.|
|DescribeBgpPeers|Query the BGP peers in a region.|
|DeleteBgpPeer|Delete a BGP peer.|
|AddBgpNetwork|Advertise a BGP network.|
|DeleteBgpNetwork|Delete an advertised BGP network.|
|DescribeBgpNetworks|Query advertised BGP networks.|

## Global Acceleration {#section_s2c_rby_sdb .section}

|API|Description|
|:--|:----------|
|CreateGlobalAccelerationInstance|Create a Global Acceleration instance.|
|DescribeGlobalAccelerationInstances|Query the list of created Global Acceleration instances.|
|ModifyGlobalAccelerationInstanceAttributes|Modify the name and description of a Global Acceleration instance.|
|ModifyGlobalAccelerationInstanceSpec|Modify the bandwidth of a Global Acceleration instance.|
|DeleteGlobalAccelerationInstance|Delete a Global Acceleration instance.|
|AssociateGlobalAccelerationInstance|Bind a Global Acceleration instance to a backend server.|
|UnassociateGlobalAccelerationInstance|Unbind a Global Acceleration instance from the associated backend server.|
|DescribeServerRelatedGlobalAccelerationInstances|Query Global Acceleration instances bound to a backend server.|

