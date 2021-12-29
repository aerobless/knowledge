---
description: Elastic Cloud Compute
---

# EC2

## File system

There are 3 types of file systems that can be used with EC2:

* **Instance Store:** Physically connected to the EC2 instance. They can't be re-used for other EC2 instances and if an EC2 instance is deleted the data on these is deleted as well.
* **Elastic Block Storage (EBS)**: Independent networked volumes. They can be re-used across EC2 instances. They live on even if the EC2 instance is terminated
* **Elastic File System (EFS):** Scaleable, independent networked volumes. Compared to EBS these can be accessed by multiple EC2 instances at the same time (1-1000) from multiple AZs. They're similar to a network drive.

## Launching AMIs

When launching an AMI you need to decide between instance volume backed AMIs and EBS backed AMIs. Instance backed AMIs cannot be stopped, only terminated or restarted. Whereas EBS backed AMIs can be stopped and the data is persisted on the EBS volume.

A stopped EC2 instance does not cost money, so by using EBS you can essentially free up the EC2 resources while keeping your data. Instance backed EC2 instances can only be freed up by terminating them, and you're losing the data on the instance volume in this case.

| Instance volume backed                            | EBS volume backed                        |
| ------------------------------------------------- | ---------------------------------------- |
| restart, terminate                                | restart, stop, terminate                 |
| slower boot, data needs to be transferred from S3 | faster boot time, data is already on EBS |



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
    3. Add rule to open port where application will be running on (e.g. 8080, 3000 etc.)
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

## Scaling EC2 Infrastructure

There are two types of scaling

* **Vertical Scaling:** The instance is "scaled up", e.g. more RAM, CPU or in the context of AWS simply a larger instance type.
* **Horizontal Scaling:** You "scale out", this means adding additional instances to handle the workload.

### Auto Scaling Group (ASG)

A launch template defines the instance configuration for the auto scaling group. E.g. what OS, instance type etc.

You also define the min, max and desired number of instances in the group.

The Auto Scaling Group performs health check on each instance by visiting an URL.

An auto scaling group exists in 1 or more availability zone of a single region.

ASGs work with on-demand and spot instances.

An ASG on its own is useless, it needs a Load Balancer to balance the incoming traffic between instances. The ASG communicates with the application load balancer to route traffic. E.g. in case a instance becomes unhealthy the ASG lets the load balancer know.

### AWS Secrets Manager

The secrets manager in respect to auto scaling is needed so tokens, credentials etc. can be securely accessed by a freshly started instance. Secrets Manager can automatically rotate credentials.

## Securing access to EC2 instances

### Security Groups

SGs serve as a firewall for EC2 instances. They control inbound and outbound traffic at the instance level. EC2 instances can belong to multiple security groups.&#x20;

VPCs have a default security group, but other than that you always have to explicitly associate an EC2 instance with a security group.

By default on a security group all outbound traffic is allowed.

### Network ACLs

Network ACLs work at the subnet level within a [VPC](../vpc.md). A network ACL enables you to allow and deny traffic. Each VPC comes with a default ACL that allows all inbound and outbound traffic.

New custom ACL's deny all traffic until rules are added.

### AWS VPN

With AWS VPN you can create an encrypted tunnel into you VPC. This can be used to connect a data center or individual client machines to the VPC.&#x20;

There are two versions of AWS VPN:

*   **Site-to-site VPN**

    A fixed VPN connection between a data center and the VPC. Differs from Direct Connect because this traffic goes over the internet (encrypted) whereas Direct Connect traffic goes over the AWS global infrastructure and not the public internet.&#x20;
*   **Client VPN**

    Connecting with a client computer to the VPC.

## Protecting the infrastructure from attacks

### AWS Shield

Shield is a managed DDoS protection service for apps on AWS. It enables on-going threat detection and mitigation.

It has 2 service levels (standard and advanced).

### AWS Macie

Utilises machine learning to analyse the data in S3. It can detect personal information and intellectual property data stored in S3.&#x20;

It continually watches and categorises data. And provides dashboards that show how the data is being stored and accessed.

It can also provide alerts if the detects anything unusual about data access.

### Amazon Inspector

Inspector enables scanning of EC2 instances for security vulnerabilities.&#x20;

Inspector charges per instance, per assessment run.

There are 2 types of rules packages:

*   **Network reachability assessment**

    What is available to the internet from our servers
*   **Host assessment**

    Checks servers for critical vulnerabilities to make sure everything has been patched.

