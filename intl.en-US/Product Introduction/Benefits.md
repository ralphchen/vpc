# Benefits {#concept_ckn_y3z_ndb .concept}

VPC features high security and flexible configuration, and supports multiple connection methods.

## Secure {#section_as5_cxz_vdb .section}

Each VPC has a unique tunnel ID, and each tunnel ID corresponds to a virtual network. Different VPCs are isolated by tunnel IDs:

-   Using VSwitches and VRouters, you can segment your VPC into subnets as you would in the traditional network environment. Different cloud resources in the same subnet use the VSwitch to communicate with each other, while cloud resources in different subnets within a VPC use VRouters to communicate with each other.
-   The intranet communication between different VPCs is completely isolated and can only be interconnected by mapping an external IP \(Elastic IP and NAT IP\).
-   The IP packets of ECS are encapsulated with the tunneling ID, the data link layer \(two-layer MAC address\) will not transfer to the physical network. Therefore, the two-layer network of different ECS is isolated. That is, the two-layer networks between different VPCs are isolated.
-   ECS instances in VPC use security groups as firewalls to control the traffic to and from ECS instances. This is the third-layer isolation.

## Controllable {#section_elt_dxz_vdb .section}

You can use security groups or whitelists to control the inbound and outbound traffic going through the cloud resources in a VPC.

## Ease of use {#section_nls_2xz_vdb .section}

You can quickly create and manage your private network on the VPC console. After a VPC is created, the system automatically creates a VRouter and a route table for it.

## Scalable {#section_d4p_fxz_vdb .section}

You can create multiple subnets in a VPC to deploy different services. Additionally, you can connect a VPC to a local data center or other VPCs to expand the network architecture.

