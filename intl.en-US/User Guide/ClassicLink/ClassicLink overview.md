# ClassicLink overview {#concept_q5z_kwb_sdb .concept}

VPC provides the ClassicLink function, allowing you to connect an ECS instance of the classic network to cloud resources in a VPC through the intranet.

## Limits {#section_bbp_dzl_g2b .section}

Note the following before using the ClassicLink function:

-   Up to 1,000 ECS instances of the classic network can be connected to the same VPC.

-   An ECS instance of the classic network can be connected to only one VPC \(belong to the same account and the same region\).

    For cross-account connection such as connecting an ECS instance of account A to a VPC of account B, the ECS instance can be transferred from account A to account B.

-   To enable the ClassicLink function of a VPC, the following conditions must be met:

|VPC CIDR block|Limitations|
|:-------------|:----------|
|172.16.0.0/12|There is no custom route entry destined for 10.0.0.0/8 in the VPC.|
|10.0.0.0/8| -   There is no custom route entry destined for 10.0.0.0/8 in the VPC.

-   Make sure that the CIDR block of the VSwitch to communicate with the ECS instance in the classic network is within 10.111.0.0/16.

 |
|192.168.0.0/16| -   There is no custom route entry destined for 10.0.0.0/8 in the VPC.

-   Add a route entry, of which the destination CIDR block is 192.168.0.0/16 and the next hop is the private NIC, to the ECS instance of the classic network. You can use the provided script to add the route. Click [Here](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/58095/cn_zh/1502878832385/route192.zip) to download the route script.

**Note:** Before running the script, read the readme file in the script carefully.

 |


## Connection scenarios {#section_mhc_gnt_g2b .section}

The following table lists the scenarios of connecting an ECS instance in the classic network to a VPC network.

|**Network type of the initiator**|**Region/account**|**Network type of the receiver/intranet communication**|
|Classic network|VPC|
|Classic network| Same region

 Same account

 |Add a same-account authorization rule in the security group.|Build a ClassicLink connection.|
| Same region

 Different accounts

 |Add an across-account authorization rule in the security group.| -   Solution A:
    1.  Migrate the ECS instance of the classic network to the VPC network
    2.  Connect the VPCs
-   Solution B:
    1.  Transfer the ECS instance of the classic network to the account of the VPC
    2.  Build a ClassicLink connection

 |
| Different regions

 Same account

 | 1.  Migrate both ECS instances to the VPC network.
2.  Connect the two VPCs.

 | 1.  Migrate the initiator ECS instance to the VPC network.
2.  Connect the two VPCs.

 |
| Different regions

 Different accounts

 |
|VPC| Same region

 Same account

 |Build a ClassicLink connection|Connect the VPCs|
| Same-region

 Cross-account

 | -   Solution A:
    1.  Migrate the ECS instance of the classic network to the VPC
    2.  Connect the VPCs
-   Solution B:
    1.  Migrate the ECS instance of the classic network to the account of the VPC.
    2.  Build a ClassicLink connection

 |
| Cross-region

 Same-account

 | 1.  Migrate the receiver ECS instance of the classic network to the VPC
2.  Connect the VPCs

 |
| Cross-region

 Cross-account

 |

## Introduction to ClassicLink {#section_jlf_pwb_sdb .section}

The bottom layer implementation of the intercommunication between a classic network and VPC is consistent with that of the intercommunication between two different classic networks. Therefore, the intranet latency and bandwidth limit remain unchanged. Operations like downtime migration, hot migration, stopping, starting, restarting, and system disk replacement will not change the established ClassicLink link.

The classic network and VPC are two different network planes. ClassicLink establishes a private communication channel between these two network planes through routing.  Therefore, to use the ClassicLink function, you must plan the network properly to avoid network conflicts.

The IP address range of the classic network in Alibaba Cloud is 10.0.0.0/8 \(excluding 10.111.0.0/16\). As long as the IP address range of the VPC does not conflict with 10.0.0.0/8, you can use ClassicLink to establish a private communication.  The IP address ranges of the VPC that can communicate with the classic network through ClassicLink are 172.16.0.0/12, 10.111.0.0/16 and 192.168.0.0/16.

## Principle of ClassicLink {#section_at5_swb_sdb .section}

After an ECS instance of the classic network is connected to a VPC through ClassicLink:

-   The ECS instance in the classic network can access the cloud resources in the VPC.

    For example, an ECS instance in the classic network is connected to a VPC of the IP address range 10.0.0.0/8, and the VPC has a VSwitch of the IP address range 10.111.1.0/24. If you have deployed cloud resources such as ECS instances and RDS in the VSwitch, then the ECS instance in the classic network can access these resources through ClassicLink.

-   After the ClassicLink connection is successfully established, ECS instances in the VPC can only access the ECS instances in the classic network that is connected to the VPC, and cannot access the ECS instances in the classic network that is not connected to the VPC or other cloud resources in the classic network.


