---
description: Elastic Cloud Compute
---

# EC2

## Creating an EC2 instance

1. Switch to EC2 service
2. Launch instance
3. Choose image, e.g. Amazon Linux 2
4. Choose instance type
5. Select network
6. Select subnet
7. Next
8. Select EBS type (default 8GB SSD)
9. Add a tag to better recognise the instance
10. Create new security group
    1. set name and description
    2. for production we would want to restrict ssh access
    3. Add rule to open port where application will be running on (e.g.  8080, 3000 etc.)
       1. Custom TCP
       2. Set desired port range
       3. Source: anywhere
11. Launch
    1. Create a new keypair to ssh into the instance.
    2. Set name & download keyfile

## Elastic IP

A public IP address that is independent of an EC2 instance. It can be assigned, unassigned and destroyed.

### Assign an elastic IP

1. EC2 service dashboard -> Elastic IPs
2. Allocate Elastic IP address
3. Add tag
4. Allocate
5. Actions -> Associate Elastic IP Address
   1. Instance: ec2 instance name
   2. Private ip: select IP of instance
   3. Associate

## SSH into EC2 instance and install nodeJS

1. Prepare PEM file: `chmod 400 <path-to-pem-file>`
2. SSH command: `ssh -i <pem-file> ec2-user@<public-ip>`
3. Update packages: `sudo yum update`
4. Install node
   1. `curl -sL https://rpm.nodesource.com/setup_16.x | sudo bash -`
   2. `sudo yum install -y nodejs`

## Copy files to EC2 via SCP

1. `scp -r -i <pem-file> <folder-to-copy> ec2-user@<public-ip>:/home/ec2-user`



