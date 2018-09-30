# VPC FAQs {#concept_bxf_qf4_tdb .concept}

## 1. Can different VSwitches in a VPC communicate with one another? {#section_ppc_2l5_vdb .section}

As long as the security group rules permit, ECS instances in the same VPC can communicate with one another, no matter whether they are the same or not.

## 2. Can different VPCs communicate with one another through the Intranet? {#section_qpc_2l5_vdb .section}

Different VPCs are logically isolated from one another. You can use Express Connect, VPN Gateway and CEN instances to enable communication among the VPCs. For more information, see [How to choose a private connectivity product?](../../../../reseller.en-US/Best practices/How to choose a private connectivity product?.md#).

## 3. Does VPC support physical access? {#section_rpc_2l5_vdb .section}

VPC supports the access of local data centers through physical connection. For more information, see the document of Express Connect.

## 4. Does VPC provide the VPN function? {#section_spc_2l5_vdb .section}

VPC provides the VPN function. For more information, see the document of VPN Gateway.

## 5. Can VPC access Internet services? {#section_tpc_2l5_vdb .section}

You can enable a VPC to access Internet services through the following methods:

-   Allocate a public IP
-   Bind an EIP
-   Configure a NAT Gateway

For more information, see [How to choose an Internet-facing product?](../../../../reseller.en-US/Best practices/How to choose an Internet-facing product?.md#).

## 6. Can cloud services in a VPC be accessed from the Internet? {#section_vpc_2l5_vdb .section}

You can access cloud services in a VPC from the Internet through the following methods:

-   Allocate a public IP
-   Bind an EIP
-   Port mapping 
-   Configure an Internet SLB instance

For more information, see [How to choose an Internet-facing product?](../../../../reseller.en-US/Best practices/How to choose an Internet-facing product?.md#).

## 7. Can a VPC directly communicate with the classic network? {#section_xpc_2l5_vdb .section}

VPC can't directly communicate with the classic network. You can configure a public IP for the ECS instance in the VPC through the following methods to enable the ECS instance to communicate with cloud product instances in the classic network through the Internet.

For more information, see [How to choose an Internet-facing product?](../../../../reseller.en-US/Best practices/How to choose an Internet-facing product?.md#).

