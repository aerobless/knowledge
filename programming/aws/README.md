---
description: Amazon Web Services
---

# AWS

## [Elastic Compute Cloud (EC2)](./#elastic-compute-cloud-ec2)

Used to run applications, virtual desktops, 3rd party software etc.

An EC2 instance runs an [AMI (**Amazon Machine Image**)](ec2/ami.md). This is basically a VM image in various flavours, e.g. different operating systems, web server stacks etc. Amazon updates the AMIs not someone's EC2 instance.

Storage for an EC2 instance is called EBS (**Elastic Block Storage**). They're independent of an EC2 instance. EBS is specific for using as file system with EC2.

**Security Groups** are IP-based communication rules for a single or group of EC2 instances. Basically little firewalls for EC2. They can be used to control who can SSH into an EC2 instance or which EC2 instances can talk to each other.

EC2 is priced per instance type (small, medium, large) and AMI (linux vs. windows).

## [Simple Storage Service (S3)](s3.md)

Service that stores files. It is used by a variety of other AWS services. It has a max file size of 5TB. The largest file that can be uploaded in a single put is 5GB.

S3 is structured in Buckets. A bucket contains objects. Buckets can be configured to trigger events when changes happen.

S3 can be used to host static websites or resources publicly.&#x20;

CloudFront can be used to cache content from S3 to other regions so that the access for end users is fast.

S3 Pricing is based on: Amount of data, number of requests and amount of data transferred.

## [Relational Database Service (RDS)](ec2/rds.md)

Is the AWS service for managed relational databases. AWS handles database backups, redundancy, software patches etc.

RDS databases run on EC2 instances. So when configuring a RDS you choose the instance type it runs on.

RDS controls access via Security Groups.

RDS is priced by type of database (license cost), region and EC2 instance type.

## Route 53

Service for DNS management. Configure domain names to resolve to internal AWS services.

Route 53 allows to setup health checks for a given URL.&#x20;

Route 53 costs 0.5$/month for each hosted zone and 0.4$ per 1M queries.

## [Elastic Beanstalk (EB)](ec2/eb.md)

Runs applications on EC2 instances. Here you don't have control over the OS or AMI running on the EC2 instance. Instead you're just providing the code/binaries of your own application.

It simplifies deployment and scaling of an application.

Application versions are stored in S3. Per default an application can have 1000 versions.

EB is free, you're just paying for the underlying EC2 instances, load balances and S3 storage.

## Lambda

Lambda provides Code Execution as a service. Here you're creating individual functions that are small and self-contained. There is almost no configuration required.

With Lambda you're paying per number of request and 100ms time increments when code is running. This can be very cost saving for infrequent activity.

Lambda is great for small, irregular tasks.

## [DynamoDB](dynamodb.md)

Is the AWS service for NoSQL databases. It supports both document and key-value storage.

You don't have to worry about EBS or EC2 instance types.

You pay for how much you store and how much it's queried.

Pricing is based on provisioned throughput capacity and the amount of data stored.

## [Virtual Private Cloud (VPC)](./#virtual-private-cloud-vpc)

## Cloud Watch

Is used for monitoring resources. When a predefined criteria is reached an alert can be sent.

Cloud Watch can be used to set an alarm for predefined metrics. E.g. S3 number of objects reached. Or Route 53 health check failed.

An action executed by an alarm could be an sms/email or triggering an autoscaling action on EC2 instances.

Cloud Watch can also consume, aggregate and monitor logs. To do this you install an awslogs agent on an EC2 instance.

&#x20;Cloud Watch pricing is per functionality. E.g. alarms, ingesting logs, archiving logs and dashboards.

### Simple Notification Service (SNS)

Notifications can be sent as Email, SMS or HTTP request. SNS notifications are sent to a topic (arn:aws:sns:..). You can then subscribe to a topic with a email or SMS receiver.

Topics are region specific and can only be notified by alarms in the same region.

#### CONSOLE: Creating a billing notification

1. Select desired region
2. Load SNS service
   1. Enter topic name (e.g. admin\_email)
   2. Create
   3. Create subscription
      1. Protocol: Email
      2. Endpoint: email@address.com
      3. Create subscription
3. Load CloudWatch service
   1. Alarms -> All alarms
   2. Create alarm
   3. Select metric
   4. Billing -> Total estimated charge -> USD -> Select metric
   5. Set condition -> Next
   6. Send a notification to ... -> chose SNS topic -> next
   7. Set alarm  name -> Next -> Create alarm

## [Cloud Front](./#cloud-front)

Helps reduce latency by serving content from locations closest to the incoming request. It's a CDN (content delivery network). It works with S3, EC2, Load Balancer and Route 53.

To setup Cloud Front you create a distribution. A distribution contains a location of the original content (e.g. S3 bucket).

Various things can be configured on a distribution. E.g. SSL cert, allowed HTTP methods and edge locations used.

Pricing differs per edge locations the user makes requests to.

## DocumentDB

Is the AWS service for MongoDB-compatible NoSQL databases.

## Resource identification

* IP Adresses (10.0.0.1)
* ARN (Amazon Resource Name), e.g. DynamoDB (arn:aws:dynamodb:...)

## Amazon Cognito

A managed service that enables you to handle of authentication and aspects of authorisation for your custom web and mobile applications through AWS.

It is a user directory service for custom applications. Basically IAM for your own custom applications.

It also provides UI components for many platforms.

Provides security capabilities to control account access and AWS resources. This can also work with social and enterprise identity providers.

## Notes

* [AWS CLI](https://aws.amazon.com/cli/)
* [AWS Free Tier (how much & which services)](https://aws.amazon.com/free/?all-free-tier.sort-by=item.additionalFields.SortRank\&all-free-tier.sort-order=asc\&awsf.Free%20Tier%20Types=\*all\&awsf.Free%20Tier%20Categories=\*all)





