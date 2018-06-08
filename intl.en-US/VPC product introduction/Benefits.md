# Benefits {#concept_ckn_y3z_ndb .concept}

VPC features high security and flexible configuration, and supports multiple connection methods.

## Security isolation {#section_as5_cxz_vdb .section}

-   The cloud servers of different users are located in different VPCs.
-   Different VPCs are isolated by tunnel IDs.  Using VSwitches and VRouters, you can segment your VPC into subnets as you would in the traditional network environment. Different cloud servers in the same subnet use the VSwitch to communicate with each other, while cloud servers in different subnets within a VPC use VRouters to communicate with each other.
-   The intranet between different VPCs is completely isolated and can only be interconnected by external mapping of IP \(Elastic IP and NAT IP\).
-   Because the IP packets of cloud servers are encapsulated with the tunneling ID, the data link layer \(two-layer MAC address\) of the cloud server will not transfer to the physical network. Therefore, the two-layer network of different cloud servers is isolated. That is, the two-layer networks between different VPCs are isolated.
-   ECS instances within a VPC use a security group firewall to control the network access. This is the third layer isolation.

## Access control {#section_elt_dxz_vdb .section}

-   Security groups provide flexible access control rules.
-   Compliant with security isolation rules of government and financial users.

## Software Defined Network \(SDN\) {#section_nls_2xz_vdb .section}

-   SDN provides customized network configurations.
-   Management operations take effect in real time.

## Various network connection methods {#section_d4p_fxz_vdb .section}

-   Software VPNs are supported.
-   Lease line connection is supported.

