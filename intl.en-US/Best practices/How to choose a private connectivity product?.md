# How to choose a private connectivity product? {#concept_yxq_zs5_sdb .concept}

Virtual Private Cloud \(VPC\) is a private network dedicated to you on Alibaba Cloud. Alibaba Cloud provides various products and services to connect and access VPC, such as Express Connect, VPN Gateway, CEN and Smart Access Gateway.

This document summarizes available private connectivity solutions for connecting VPCs.

|[Connect the VPCs](reseller.en-US/Best practices/How to choose a private connectivity product?.md#section_wbw_gt5_sdb)|
|**Product**|**Description**|**Benefit**|**Limit**|
|VPN Gateway|Connect two VPC networks using an Internet-based and encrypted IPsec-VPN tunnel.| Low cost

 Security

 Out-of-the-box service.

 |However, the network latency and availability depend on the Internet.|
|Cloud Enterprise Network \(CEN\)|Connect one or more VPC networks in different regions and different accounts to build an interconnected network.| Simple configuration, and automatic route learning and distribution.

 Low latency and high speed.

 The networks \(VPC/VBR\) attached to a CEN instance are all connected with each other.

 Connecting networks in the same region is free of charge.

 |—|
|[Connect to a local IDC](reseller.en-US/Best practices/How to choose a private connectivity product?.md#section_klv_ft5_sdb)|
|**Product**|**Description**|**Benefit**|**Limit**|
|VPN Gateway|Connect a local IDC and a VPC through an Internet-based and encrypted IPsec-VPN tunnel.| Low cost

 Security

 Configurations take effect immediately.

 |However, the network latency and availability depend on the Internet.|
|Cloud Enterprise Network \(CEN\)|Through automatic route learning and distribution, CEN can connect resources in the whole network. You only need to attach the VBR associated with the local data center to the CEN instance.| Simple configuration, and automatic route learning and distribution.

 Low latency and high speed.

 The networks \(VPC/VBR\) attached to a CEN instance are all connected with each other.

 Connecting networks in the same region is free of charge.

 |—|
|Smart Access Gateway|Connect a local data center to Alibaba Cloud.| Highly automatic and out-of-the-box service.

 The local branches and the Alibaba Cloud are connected through an encrypted private network and encryption authentication is implemented during the Internet transmission.

 Nearby access within the city through the Internet is supported. Additionally, multiple local branches can access Alibaba Cloud using the Smart Access Gateway devices with active/standby links.

 |—|
|Express Connect|Connect a local IDC and a VPC through the physical connection of Express Connect.| High network quality

 High bandwidth

 | High cost

 Long activation time

 |
|VPN software in Alibaba Cloud Marketplace|You can buy a VPN Gateway in Alibaba Cloud Marketplace and deploy it in the VPC, and connect a local data center to the VPC through an Internet-based and encrypted IPsec-VPN tunnel.| Security

 Various VPN software are available.

 Configurations take effect immediately.

 | You must build and maintain the VPN Gateway by yourself.

 The network latency and availability depend on the Internet.

 |
|[Connect multiple sites](reseller.en-US/Best practices/How to choose a private connectivity product?.md#section_ub1_r55_sdb)|
|**Product**|**Description**|**Benefit**|**Limit**|
|VPN Gateway \(VPN-Hub\)|Establish secure communication among multiple sites through the VPN Gateway. The VPN-Hub function not only enables each site to communicate with the VPC on the cloud, but also allows each site to communicate with each other.| Low cost

 Out-of-the-box service

 |—|
|Smart Access Gateway|Buy Smart Access Gateways for local branches to be connected and add the Smart Access Gateways to a Cloud Connect Network \(CCN\). Attach the CCN to a CEN instance to enable intranet connections among these local branches.| Out-of-the-box service

 The local branches and the Alibaba Cloud are connected through an encrypted private network and encryption authentication is implemented during the Internet transmission.

 Nearby access within the city through the Internet is supported. Additionally, multiple local branches can access Alibaba Cloud using the Smart Access Gateway devices with active/standby links.

 |—|
|VPN Gateway \(VPN-Hub\) + Express Connect|You can use VPN Gateway and Express Connect to connect application systems and office sites around the world.| High network quality

 Out-of-the-box service

 |The network latency and availability depend on the Internet.|
|[Remote access to a VPC](reseller.en-US/Best practices/How to choose a private connectivity product?.md#section_hdl_555_sdb)|
|**Product**|**Description**|**Benefit**|**Limit**|
|VPN Gateway \(SSL-VPN\)|Use the SSL-VPN function to securely and quickly access VPC from a remote client.| Low cost

 Reliable

 Easy to configure and deploy

 |—|
|SSL-VPN software in Alibaba Cloud Marketplace|Buy SSL-VPN software in Alibaba Cloud Marketplace, deploy it in VPC, and access the VPN server from a remote client.|Various SSL-VPN software is available.| High cost

 Low reliability

 Deploy and maintain the SSL-VPN software by yourself.

 |

## Connect the VPCs {#section_wbw_gt5_sdb .section}

You can deploy different applications in different VPC networks to build a service network across regions, so as to provide service from a nearby location, reduce network latency, achieve mutual backup and improve the reliability of the whole system.

Both Express Connect and VPN Gateway can connect VPCs in different regions or the same region.

-   Cloud Enterprise Network \(CEN\)

    CEN \(Cloud Enterprise Network\) helps you to build an Intranet communication channel between one or more VPCs. Through automatic route distribution and learning, it accelerates network convergence, improves the quality and security of cross-network communication, and connects resources in the whole network, thus helping you build an interconnected network with enterprise-grade scale and communication ability.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2448/1538214258834_en-US.png)

-   VPN Gateway

    VPN Gateway can connect a local data center, a local site, an Internet terminal to a VPC in a secure and reliable way through an Internet-based and encrypted channel. You can connect VPCs in different regions and different accounts through VPN Gateway. You need to create one VPN Gateway and one customer gateway for the VPCs respectively, and establish an IPsec encrypted tunnel between the VPC Gateway and the corresponding customer gateway to achieve intranet communication.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2448/1538214258835_en-US.png)


## Connect to a local IDC {#section_klv_ft5_sdb .section}

You can connect a VPC to a local IDC to build a hybrid cloud. With the secure and reliable connection between the VPC and IDC, and massive computing, storage, network, CND, and GBP resources on Alibaba Cloud, you can extend IDC local IT infrastructure seamlessly to Alibaba Cloud in real time in Pay-As-You-Go mode to deal with fluctuations in service.

You can connect a local IDC to a VPC through Express Connect, VPN Gateway or CEN.

-   Express Connect

    Express Connect provides the physical connection function. After a leased line is accessed to an Alibaba Cloud access point, you can create a peer connection between a VBR and a VPC to build a hybrid cloud.

    The intranet connection of leased line does not go through the Internet. Therefore, compared with the traditional Internet connection, the physical connection features higher security, reliability and speed and lower latency.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2448/1538214258836_en-US.png)

-   VPN Gateway

    VPN Gateway can connect a local data center, a local site, an Internet terminal to a VPC in a secure and reliable way through an Internet-based and encrypted channel. VPN Gateway contains two different gateway instances which provide active/standby hot backup. The traffic is automatically distributed to the standby node when the active node fails. You can use IPsec-VPN to connect a local data center to a VPC.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2448/1538214258837_en-US.png)

-   Cloud Enterprise Network \(CEN\)

    Through automatic route distribution and learning, CEN enables you to build a secure, private, and enterprise-class interconnected network between VPCs in different regions and your local data centers. You only need to attach the VBR associated with the local IDC to a CEN instance, then the local IDC can communicate with all networks \(VPCs or VBRs\) attached to the CEN instance.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2448/15382142589794_en-US.png)

-   Smart Access Gateway

    Smart Access Gateway is a one-stop solution for connecting local organizations to the Alibaba Cloud. With Smart Access Gateway, enterprises can access Alibaba cloud through the Internet in an encrypted way, and get a more intelligent, more reliable, and more secure experience in accessing the Alibaba Cloud.

    You can buy a Smart Access Gateway device for the local data center, and attach the CCN instance associated with the Smart Access Gateway to a CEN instance to connect the local IDC to Alibaba Cloud.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2448/15382142589796_en-US.png)

-   VPN software in Alibaba Cloud Marketplace

    Alibaba Cloud Marketplace provides various VPN software or images. You can buy VPN software in Alibaba Cloud Marketplace and deploy it on your ECS instance. Then you can use an EIP to connect the VPC to the customer gateway of your local IDC through the Internet.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2448/1538214259838_en-US.png)


## Connect multiple sites {#section_ub1_r55_sdb .section}

You can connect multiple sites through Smart Access Gateway or the VPN-Hub function of VPN Gateway.

-   Smart Access Gateway

    Smart Access Gateway is a one-stop solution for connecting local organizations to the Alibaba Cloud. With Smart Access Gateway, enterprises can access Alibaba cloud through the Internet in an encrypted way, and get a more intelligent, more reliable, and more secure experience in accessing the Alibaba Cloud.

    You can buy Smart Access Gateway devices for local branches and connect the devices through CEN so that the local branches can communicate with one another.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2448/15382142599795_en-US.png)

-   Connect multiple sites

    The IPsec-VPN function of VPN Gateway provides site-to-site VPN connection. Each VPN Gateway supports 10 IPsec-VPN connections. Therefore, you can buy a VPN Gateway to connect 10 IDCs or local sites in different areas.

    You can establish secure communication among multiple sites through the VPN-Hub function. The sites cannot only communicate with the connected VPC but also can communicate with each another. VPN-Hub meets the needs of large enterprises to establish intranet communication among different sites.

    The VPN-Hub function is enabled by default. You only need to configure the IPsec-VPN connection between each office site and Alibaba Cloud, and no additional charges are billed. A VPN Gateway supports up to 10 IPsec connections. Therefore, you can connect up to 10 office sites with one VPN Gateway. As shown in the following figure, to connect the three office sites \(Shanghai, Hangzhou, and Ningbo\), you only need to create a VPN Gateway and three customer gateways and establish three IPsec connections.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2448/1538214259839_en-US.png)

-   Build a high-speed global network

    You can connect application systems and office sites around the world through VPN Gateway and Express Connect. This method features high security, high network quality and low cost.

    As shown in the following figure, to connect office sites in US \(Virginia\) and office sites in Shanghai, you can deploy application systems in the VPC in US East and the VPC in Shanghai respectively, connect the VPCs through Express Connect and connect office sites in the two regions to the two VPCs through IPsec-VPN.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2448/1538214259840_en-US.png)


## Remote access to a VPC {#section_hdl_555_sdb .section}

The SSL-VPN function of VPN Gateway provides site-to-site VPN connection. Terminals can directly access a VPC without configuring customer gateways. You can deploy local internal applications in a VPC, and internal staff access the internal system through SSL-VPN. For example, local IT staff access the VPC through intranet to perform operation and maintenance, and staff on a business trip can access local applications in the VPC from remote sites.

Both VPN Gateway or VPN software/image in Alibaba Cloud Marketplace can achieve remote access to the VPC.

-   VPN Gateway \(SSL-VPN\)

    You can create an SSL-VPN connection to connect a remote client to applications deployed in a VPC. When the deployment is complete, you only need to load the certificate in the client to initiate the connection. VPN Gateway contains two different gateway instances which provide active-standby hot backup. The traffic is automatically distributed to the standby node when the active node fails.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2448/1538214259841_en-US.png)

-   Purchase SSL-VPN software in Alibaba Cloud Marketplace

    You can buy an SSL-VPN software or image in Alibaba Cloud Marketplace and deploy SSL-VPN on an ECS instance bound with EIP in the VPC, then you can access the Internet from a remote client.


