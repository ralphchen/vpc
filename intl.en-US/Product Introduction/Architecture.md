# Architecture {#concept_ddt_l3z_ndb .concept}

Based on mainstream tunneling technologies,  VPCs isolate virtual networks. Each VPC has a unique tunnel ID, and a tunnel ID corresponds to only one VPC. 

## Background information {#section_b23_p3z_ndb .section}

With the continuous development of cloud computing, virtual network requirements are getting higher and higher, such as scalability, security, reliability, privacy, and higher requirements of connection performance. This gives a rise to a variety of network virtualization technologies.

The earlier solutions combined the virtual machine's network with the physical network to form a flat network architecture, such as the large layer-2 network.  With the increase of virtual network scalability, problems are getting more serious for the earlier solutions. These problems include ARP spoofing, broadcast storms, host scanning, and more.  Various network isolation technologies emerged to resolve these problems by completely isolating the physical networks from the virtual networks.  One technology isolates users with VLAN, but VLAN only supports up to 4096 nodes. It cannot support the huge amount of users in the cloud.

## VPC theory {#section_gtq_q3z_ndb .section}

Based on mainstream tunneling technologies,  VPCs isolate virtual networks. Each VPC has a unique tunnel ID, and a tunnel ID corresponds to only one VPC.  A tunnel encapsulation carrying a unique tunnel ID is added to each data packet transmitted between the ECS instances within a VPC.  Then, the data packet is transmitted over the physical network.  Because the tunnel IDs are different for ECS instances in different VPCs and the IDs are located on two different routing planes, the ECS instances from different VPCs cannot communicate with each other and are isolated by nature. 

Based on the tunneling and SDN technologies, the Alibaba Cloud research and development team has developed the VPC in the basis of hardware gateways and self-developed switch equipment.

## Logical architecture {#section_jz5_r3z_ndb .section}

As shown in the following figure, the VPC architecture contains three main components: VSwitches, gateway, and controller. VSwitches and gateways form the key data path. Controllers use the self-developed protocol to forward the forwarding table to the gateway and VSwitches, completing the key configuration path.  In the overall architecture, the configuration path and data path are separated from each other. VSwitches are distributed nodes, the gateway and controller are deployed in clusters, and all links have redundant disaster recovery. This improves the overall availability of the VPC. 

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/2428/15354347495013_en-US.png)

