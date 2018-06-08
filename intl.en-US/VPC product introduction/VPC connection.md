# VPC connection {#concept_wyd_112_sdb .concept}

Alibaba Cloud provides rich solutions to connect cloud product instances in a VPC with the Internet, other VPCs, or local data centers.

## Connect cloud product instances to the Internet {#section_brw_n12_sdb .section}

When cloud products in a VPC need to communicate with the Internet, you can use NAT Gateway, EIP, or SLB instances.

 

## Connect cloud product instances to other VPCs or local data centers {#section_jcr_l35_sdb .section}

When your VPC needs to communicate with other VPCs or local data centers, you can use VPN Gateway, Express Connect, CEN and so on or jointly use them to build a hybrid cloud environment.

The following table lists the functions and features of intranet products.

|Product|Function|Benefit|
|:------|:-------|:------|
|Express Connect| -   Connect VPCs

Support intranet communication between VPCs regardless of the region or account

-   Connect a VPC to a local data center

Enable a VPC to communicate with a local data center through physical access


 | -   Based on the backbone network, low latency.

-   The leased line access features higher security and reliability, faster speed, and lower latency.


 |
|VPN Gateway| -   Connect VPCs

Provide the IPsec-VPN function and build an encrypted communication channel by creating an IPsec connection between two VPCs

-   Connect a VPC to a local data center

Provide the IPsec-VPN function and connect a local data center to a VPC through the IPsec connection.

-   Connect multiple local data centers

VPN Gateway supports the VPN-Hub function and multi-site connection by default. The sites not only can communication with the VPC, but also can communicate with one another through VPN-Hub communication.

-   Client remote access

Remote access of the client to the VPC can be achieved by establishing SSL-VPN connection.


 | -   Low cost, secure and simple configuration, instantly available, however, the quality of the network depends on the Internet.

-   IPsec-VPN supports IKEv1 protocol and IKEv2 protocol. Any devices supporting the two protocols can connect to the VPN Gateway of Alibaba Cloud, such as Huawei, H3C, Hillstone, Sinfor, Cisco ASA, Juniper, SonicWall, Nokia, IBM, Ixia and so on.

-   SSL-VPN connection supports multiple-terminal access from operation systems such as Windows, Linux, Mac, IOS and Android.


 |
|CEN| -   Connect VPCs

Support connecting VPCs in different regions and under different accounts to build an interconnected network.

-   Connect a VPC to a local data center

Support attaching the VBR associated with the local data center to the created CEN instance to build an interconnected network.

-   Connect VPCs and local data centers

Support attaching networks \(VPCs and VBRs\) to the created CEN instance to build an enterprise-grade interconnected network.


 | -   Simple configuration, and automatic route learning and distribution.

-   Low latency and fast speed.

-   Connect all networks \(VPCs/VBRs\) attached to a CEN instance.

-   Connecting networks in the same region is free of charge.


 |
|Smart Access Gateway| -   Smart Access Gateway can connect multiple local branches to the Alibaba Cloud to quickly build a hybrid cloud for large organizations.

-   Connect on-premises organizations


 | -   Highly automated configuration, out-of-box experience, and fast and adaptive convergence of network topology changes.

-   Nearby access through the Internet is implemented to achieve access from within a city, and multiple local branches can access to the Alibaba Cloud using the Smart Access Gateway devices with master-slave links.

-   The local branches and the Alibaba Cloud are connected through an encrypted private network and encryption authentication is implemented during the Internet transmission.


 |

