# VPC FAQs {#concept_lbv_4f4_tdb .concept}

## 1. What is the difference between the VPC and the classic network? {#section_d4z_hg4_tdb .section}

-   The cloud products created in the classic network are uniformly deployed in the public network infrastructure of Alibaba Cloud.  The classic network is managed by Alibaba Cloud, which is applicable for the users that have high demand on the usability.
-   VPC is an isolated private network that users create in Alibaba Cloud. Users have full control over the VPC.  Compared to the classic network, VPC is more applicable to the users with the network management capability who want to control their private networks.

## 2. How many network interface cards does an ECS instance have? {#section_fht_lg4_tdb .section}

The ECS instance created in the classic network has two NICs, one is the public NIC and the other one is the private NIC;  while the VPC ECS instance only has one private NIC.

## 3. How many VRouters does a VPC have? {#section_vl4_ng4_tdb .section}

Each VPC has only one VRouter and each VRouter maintains one route table.

## 4. How many custom route entries does a route table have? {#section_arm_pg4_tdb .section}

By default, you can add up to 48 custom route entries to a route table.  If you want to add more, submit a ticket.

## 5. How many VSwitches can a VPC have? {#section_gmy_qg4_tdb .section}

A VPC can contain 24 VSwitches at most.

## 6. How many cloud product instances can a VPC contain? {#section_c4h_sg4_tdb .section}

A VPC can contain 15,000 cloud product instances at most.

## 7. How many cloud product instances can a VSwitch contain? {#section_i3s_5g4_tdb .section}

The number of the cloud product instances in a VSwitch depends on the current number of cloud product instances in the VPC,  which is 15,000 minus the current amount of the cloud product instances in the VPC.

