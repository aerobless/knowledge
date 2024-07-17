---
description: Virtual Private Cloud
---
Used to control and secure access to EC2 instances. VPCs secure groups of instances.

VPC also provides control over routing tables. Configuring NAT gateways for outbound traffic and internal ip address allocation.

A VPC is made up of one or more subnets. You can have both private and public subnets. Typically you could have a private and public subnet. Where the private subnet has no access to the internet at all.

VPCs provide security by configuring Routing Tables and Network ACLs (Access Control List).

ACLs act as subnet level firewalls.

VPC is free to use, but there is a limit of 5 VPCs per account.

# Structure

* VPC
  * Subnet 1
    * Routing Table
    * NACL
  * Subnet 2..\*
    * Routing Table
    * NACL

# Creating a VPC

1. Load VPC service
2. Launch VPC wizard
   1. Select type (single public, private public, with vpn, private with vpn)
   2. Select CIDR block (Classless inter-domain routing, used to assign ip addresses)
   3. Enter vpc and subnet names
   4. Create
3. Create internet gateway
   1. Select VPC in list -> Click on ID
   2. Main route table
   3. Routes
      1. Edit routes
      2. Add route
         1. Destination: 0.0.0.0/0 (anywhere)
         2. Target: Internet Gateway
         3. Save

# Creating a second subnet for auto-scaling

1. Select Subnets -> Add new
2. Choose existing VPC
3. Give name and choose availability zone
4. Set different CIDR block, e.g. 10.0.**1**.0/24
5. Create

# Assigning public IPs to subnets

By default there are no public IPs assigned.  This is more secure. In order to access the internet one would use a NAT gateway. However NAT gateways are quite expensive so the tradeoff to assign public IPs regardless can be made.

1. Select subnet
2. Actions -> Modify auto-assign IP settings
3. Enable auto-assign public IPv4 address

