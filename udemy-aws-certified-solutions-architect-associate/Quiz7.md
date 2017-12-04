### VPC (Virtual Private Cloud)
lets you provision a logically isolated section of the Amazon Web Services Cloud where you can launch AWS resources in a virtual network that you define. You have complete control over your virtual networking environment, including selection of your own IP address range, creation of subnets, and configuration of route tables and network gateways.

### Default VPC vs Custom VPC
- Default VPC is user friendly, allowing you to immediately deploy instances

- All subnets in Default VPC have an internet gateway attached

- Each EC2 instance has both a public and private IP address

- If you delete the default VPC, the only way to get it back is to contact AWS

### VPC Peering
- Allows you to connect one VPC with another via a direct network route using private IP addresses

- Instances behave as if they were on the same private network

- You can peer VPC with other AWS accounts as well as your other VPCs in the same account

- Peering is in a star configuration

### VPC Restrictions
5 Elastic IP address
5 Internet Gateways
5 VPCs per region (can be increased upon request)
50 VPN connections per region
50 Customer Gateways per region
200 Route tables per region
100 Security Groups per VPC
50 Rules per security group

### CIDR block
classless inter domain routing, basically subnetting. i.e 10.0.0.0/16

### Tenancy
Dedicated = instances launched in this VPC are dedicated tenancy instances, regardless of the tenancy attribute specified at launch. This cost $$

Default = free

### Subnet Availability Zone
subnet are always mapped to 1 Availability Zone, it can't cross multiple zones.

### Internet Gateway
by default, it's detached. You need to attach it to a VPC. You can have only 1 Internet Gateway per VPC.

### Route Tables
To allow all traffic, type 0.0.0.0/0 in Destination

A default route table is created when creating a VPC

### Security Groups
Can stretch across different availability zones, subnets cannot.

### NAT
When using a NAT, if bottleneck, use better instance type instead of Micro 

Must disable Source/Destination Check

### Security Groups - cross security group
VPC > Security Group > Inbound Rules > add group ID of other security group