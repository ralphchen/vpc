# VPC connection {#concept_wyd_112_sdb .concept}

Alibaba Cloud provides a lot of connectivity options to you to connect a VPC to the Internet, other VPCs, or local data centers.

## Connect to the Internet {#section_jyt_lhj_w2b .section}

The following table lists the products or functions that you can use to connect a VPC to the Internet.

|Product|Feature|Benefit|
|:------|:------|:------|
|The public IP of an ECS instance of the VPC network| The public IP allocated by Alibaba Cloud when creating an ECS instance of the VPC network. With this public IP, the ECS instance can access the Internet \(SNAT\) and also can be accessed from the Internet \(DNAT\).

 | You can use Data Transfer Plan.

 After changing a public IP to an EIP, you can also use [Internet Shared Bandwidth](https://www.aliyun.com/product/cbwp).

 |
|Elastic IP Address \(EIP\)|With an EIP, the ECS instance can access the Internet \(SNAT\) and also can be accessed from the Internet \(DNAT\).| You can bind and unbind an EIP from an ECS instance at any time.

 You can use [Internet Shared Bandwidth](https://www.aliyun.com/product/cbwp) and [Data Transfer Plan](https://www.aliyun.com/product/flowbag) to reduce Internet cost.

 |
|NAT Gateway|NAT Gateway is an enterprise-class Internet gateway, supporting multiple ECS instances accessing the Internet with one EIP \(SNAT\) and being accessed from the Internet \(DNAT\).**Note:** Compared to Server Load Balancer, NAT Gateway itself does not provide the traffic balancing function.

| The core difference between NAT Gateway and EIP is that NAT Gateway supports Internet access of multiple ECS instances but EIP can only be used by an ECS instance.

 |
|Server Load Balancer| Port-based load balancing, Server Load Balancer provides Layer-4 \(TCP and UDP protocols\) and Layer-7 \(HTTP and HTTPS protocols\) load balancing. Server Load Balancer can forward the client requests from the Internet to the backend ECS instances.

 **Note:** The ECS instance without a public IP cannot access the Internet \(SNAT\) through Server Load Balancer.

 | In DNAT, Server Load Balancer supports forwarding an Internet request to multiple ECS instances.

 Server Load Balancer is a traffic distribution control service that distributes the incoming traffic among multiple ECS instances according to the configured forwarding rules. It expands application service capabilities and enhances application availability.

 After binding with an EIP, you can use [Internet Shared Bandwidth](https://www.aliyun.com/product/cbwp) and [Data Transfer Plan](https://www.aliyun.com/product/flowbag) to reduce the Internet cost.

 |

## Connect to a VPC {#section_lq3_mhj_w2b .section}

The following table lists the products or functions that you can use to connect a VPC to another VPC.

|Product|Feature|Benefit|
|:------|:------|:------|
|VPN Gateway| VPN Gateway allows you to create an IPsec-VPN connection to build an encrypted communication between two VPCs.

 For more information, see [配置VPC到VPC连接](../intl.en-US/IPsec-VPN Quick Start/Configure a VPC-to-VPC connection.md#). 

 | -   Low cost, secure and simple configuration. However, the quality of the network depends on the Internet.

-   IPsec-VPN supports IKEv1 and IKEv2 protocols. Any device that supports these two protocols can connect to Alibaba Cloud VPN Gateway. Supported devices include: Huawei, H3C, SANGFOR, Cisco ASA, Juniper, SonicWall, Nokia, IBM, and Ixia.


 |
|CEN| CEN allows you to connect VPCs in different regions and different accounts to build an interconnected network.

 For more information, see [教程概览](../intl.en-US/Quick Start/Tutorial overview.md#). 

 | -   Simple configuration, and automatic route learning and distribution.

-   Low latency and fast speed.

-   The networks \(VPCs/VBRs\) attached to a CEN instance are connected with each other.

-   The network connection in the same region is free of charge.


 |

## Connect a VPC to a local IDC {#section_s1d_4hj_w2b .section}

The following table lists the products or functions that you can use to connect a VPC to a local IDC.

|Product|Feature|Benefit|
|:------|:------|:------|
|Express Connect| Express Connect allows you to connect a VPC to a local data center.

 For more information, see [物理专线接入](../intl.en-US/Getting Started (New Console)/Connect a local data center to a VPC through a physical connection.md#). 

 | -   Based on the backbone network, low latency.

-   The leased line access features higher security and reliability, faster speed, and lower latency.


 |
|VPN Gateway| -   VPN Gateway allows you to create an IPsec-VPN connection to connect a VPC to a local IDC.

-   Connect multiple local IDCs

The VPN-Hub function of VPN Gateway allows you to connect multiple local sites to the VPC. The connected sites can communicate with the VPC, but also can communicate with one another.

-   Remote access

VPN Gateway allows you to create an SSL-VPN connection to let clients access the VPC from a remote computer.


 | -   Low cost, secure and simple configuration. However, the quality of the network depends on the Internet.

-   IPsec-VPN supports IKEv1 and IKEv2 protocols. Any device that supports these two protocols can connect to Alibaba Cloud VPN Gateway. Supported devices include: Huawei, H3C, SANGFOR, Cisco ASA, Juniper, SonicWall, Nokia, IBM, and Ixia.

-   SSL-VPN connection supports connecting a VPC from a remote computer using the Linux, Windows, and Mac operating systems.


 |
|CEN| -   Connect to a local data center

CEN allows you to attach the VBR associated with a local data center to a CEN instance to build an interconnected network.

-   Connect multiple VPCs with local IDCs

CEN allows you to attach multiple networks \(VPC/VBR\) to a CEN instance. All the attached networks are connected with one another.


 | -   Simple configuration, and automatic route learning and distribution.

-   Low latency and fast speed.

-   The networks \(VPCs/VBRs\) attached to a CEN instance are connected with one another.

-   The network connection in the same region is free of charge.


 |
|Smart Access Gateway| -   Smart Access Gateway allows you to connect local branches to the Alibaba Cloud to build a hybrid cloud for large organizations.

-   Connect local branches.


 | -   Highly automated configuration, out-of-box experience, and automatically and quickly adapts to network topology changes.

-   Access is provided from a nearby point within the city over the Internet. Additionally, multiple local branches can access Alibaba Cloud using the Smart Access Gateway devices with master-slave links.

-   The local branches and the Alibaba Cloud are connected through an encrypted private network and encryption authentication is implemented during the Internet transmission.


 |

