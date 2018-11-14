# What is VPC? {#concept_kbk_cpz_ndb .concept}

Virtual Private Cloud \(VPC\) is a private network established in Alibaba Cloud. VPCs are logically isolated from other virtual networks in Alibaba Cloud.

VPC is a private network dedicated to you in Alibaba Cloud. You have full control over your VPC, such as specifying its IP address range, and configuring route tables and network gateways. You can also use Alibaba Cloud resources such as ECS, RDS, and SLB in your own VPC.

Additionally, you can connect VPCs with a local network using a dedicated connection or VPN Gateway to form an on-demand customizable network environment. This allows you to smoothly migrate applications to the cloud with little effort.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2427/1538212527805_en-US.png)

## Components {#section_w1b_tvz_ndb .section}

Each VPC consists of a private CIDR block, a VRouter and at least a VSwitch.

-   CIDR block

    When creating a VPC or a VSwitch, you must specify the private IP address range in the form of Classless Inter-Domain Routing \(CIDR\) block. For more information, see [Classless Inter-Domain Routing](https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing).

    You can use any of the following standard CIDR blocks and their subnets as the IP address range of the VPC. For more information, see [Plan and design VPC](../../../../reseller.en-US/Best practices/Plan and design VPC.md#).

    **Note:** To use a subnet of a standard CIDR block, you must use the [CreateVpc](../../../../reseller.en-US/API reference/Virtual Private Cloud (VPC)/CreateVpc.md#) API to create a VPC.

    |CIDR block|Number of available private IPs \(system reserved ones not included\)|
    |:---------|:--------------------------------------------------------------------|
    |192.168.0.0/16|65,532|
    |172.16.0.0/12|1,048,572|
    |10.0.0.0/8|16,777,212|

-   VRouter

    VRouter is the hub of a VPC. As an important component of a VPC, it connects VSwitches in a VPC and serves as the gateway connecting the VPC with other networks. Alibaba Cloud automatically creates VRouter after you create a VPC. A VRouter associates with a route table by default. For more information, see [Routing](../../../../reseller.en-US/User Guide/Routing.md#).

-   VSwitch

    VSwitch is a basic network module in a VPC to connect different cloud product instances. After creating a VPC, you can further segment your virtual private network to one or more subnets by creating VSwitches. The VSwitches within a VPC are interconnected by default. Therefore, you can deploy different applications to VSwitches that are located in different zones to improve the service availability. For more information, see [Manage VSwitches](../../../../reseller.en-US/User Guide/Manage VSwitches.md#).

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2427/15382125272749_en-US.png)


