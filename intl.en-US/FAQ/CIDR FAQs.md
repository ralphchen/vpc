# CIDR FAQs {#concept_b4l_pf4_tdb .concept}

## 1. What is CIDR? {#section_hlx_k34_tdb .section}

Classless Inter-Domain Routing \(CIDR\) Classless Inter-Domain Routing \(CIDR\) is a method for allocating IP addresses and IP routing.  Compared to the traditional Class A, B, or C addresses, CIDR block is more efficient in the IP address allocation.  For example, the IP 125.203.96.0 - 125.203.127.255 in the CIDR form is:

125.203.0110 0000.0000 0000 to 125.203.0111 1111.1111 1111, or 203.96.0/19.

You have to specify the IP address range for the VPC and VSwitch in the form of a CIDR block when creating them.

## 2. How to specify the IP address range for a VPC? {#section_p3q_n34_tdb .section}

You can use the standard private CIDR blocks \(192.168.0.0/16, 172.16.0.0/12, 10.0.0.0/8\) and their subsets as the IP address range of a VPC.  When creating a VPC using the API, the allowed block size of the VPC CIDR block is between a /8 netmask and /24 netmask.

For more information, see [Manage a VPC](../../../../reseller.en-US/User Guide/Manage a VPC.md#).

## 3. How to specify the IP address range for a VSwitch? {#section_qd5_2j4_tdb .section}

-   The VSwitch CIDR block must belong to the corresponding VPC CIDR block. If the CIDR block of the VSwitch is the same as that of the VPC, you can only create one VSwitch.
-   The allowed block size for a VSwitch is between a /16 netmask and /29 netmask, which can provide 8 to 65,536 IP addresses.
-   The VSwitch CIDR block cannot be the same as an existing VSwitch CIDR block, and the two cannot be each other's subset.
-   The CIDR block of the VSwitch cannot be the same as that of the destination CIDR block of an route entry in the VPC.
-   The CIDR block of the VSwitch cannot contain the destination CIDR block of an route entry in the VPC, but can be the subset of the VPC CIDR block.

For more information, see [Manage VSwitches](../../../../reseller.en-US/User Guide/Manage VSwitches.md#).

