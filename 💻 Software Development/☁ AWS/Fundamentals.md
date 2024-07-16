---
description: Fundamental concepts of using cloud infrastructure and AWS
---
# IaaS vs. PaaS vs. SaaS

Infrastructure as a Service (IaaS) provides maximum control to the user. They're responsible for updating & maintaining the software on the infrastructure. The IaaS provider only takes care of the underlying "hardware". (EC2)

PaaS (Platform as a Service) is the middle ground between IaaS and SaaS. Here the provider takes care of the hardware and software platform but the user has to take care about everything built upon the platform. (Elastic Beanstalk)

SaaS (Software as a Service) is on the other end of the spectrum. The user is responsible for minimum maintenance because they're simply using a software. (e.g. Gmail, Gitbook etc.)

# Cloud Deployment models

## Public Cloud

Typical cloud providers like AWS, Google, etc.

## Private Cloud (on premises)

E.g. CloudFoundry hosted in the datacenter of the company using the cloud.

## Hybrid Cloud

Mix between public and private cloud.

# Global Infrastructure

## Region

* Region (22+ regions, e.g. us-east1, us-east2)
  * Availability zone (multiple per region, 69+ globally)
    * data center (1..n)

Naming: (Area)-(Sub Area)-(Number AZ), e.g. us-east-1

## Edge Locations (CDN)

Used by Amazon CloudFront and Route 53. There are over 200 edge locations. They're used to serve content closest to the user.

# Economics of the cloud

## CapEx (Capital expenditures)

Initial costs, e.g. to buy servers, build datacenter

## OpEx (Operational expenditures)

Operating costs per month/year. To pay for sysadmin, electricity or cloud provider.

## AWS Cost explorer

Provides breakdown by service, cost tag. Also provides predictions for next 3 months of cost and gives recommendations for cost optimisations. Can also be accessed via API.

## AWS Budgets

Utilises data from AWS Cost Explorer to plan and track usage cost across AWS services. You can set a budget on how much you want to spend per service. It will also track utilisation of reserved instances, saving plans etc.

## AWS TCO Calculator

Marketing tool, used to calculate how much could be saved by using cloud infrastructure instead of regular datacenter. (Total Cost of Ownership).

## AWS Simple Monthly Calculator (deprecated) -> AWS Pricing Calculator

Calculate the cost of running specific AWS infrastructure.

## AWS Resource Tags

Metadata assigned to AWS resources, used to help tracking costs e.g. by project, department, environment etc. You can then see the costs group by tag in the Cost Allocation Report. Tags can also be used in the AWS Cost Explorer.

## AWS Organization

Allows organisations to manage multiple AWS accounts under a master account. This is useful for consolidated billing. Consolidated billing may provide some discounts versus paying bills per account.

AWS Organisations are also useful for central logging and security standard across all accounts.



# AWS Support

## AWS Support

Support is provided in different tiers based on need and scope. It includes tools to provide automated answers and recommendations.

## Support Tiers

* **AWS Basic Support (free)**
  * Access to Trusted Advisor (7 core checks)
  * 24x7 customer service documentation, forums & whitepapers
  * Access to Personal Health Dashboard
* **AWS Developer Support (29$/month or more, tied to usage)**
  * all Basic features
  * Business hours email access to support engineers
  * limited to 1 primary contract
  * Response time
    * general guidance 24h
    * system impaired 12h
* **AWS Business Support (100$/month or more, tied to usage)**
  * all Developer & Basic features
  * all Trusted Advisor checks
  * 24x7 phone, email and chat access to support engineers
  * unlimited contacts
  * provides third-party software support
  * Response time
    * general guidance 24
    * system impaired 12h
    * production impaired 4h
    * production down 1h
* **AWS Enterprise Support (15'000$/month or more, tied to usage)**
  * all Basic, Dev and Business features
  * designated technical account manager (TAM)
  * concierge support team
  * Response time
    * general guidance 24
    * system impaired 12h
    * production impaired 4h
    * production down 1h
    * business critical system down 15min

## AWS Personal Health Dashboard

Provides alerts and remediations when AWS is experiencing outages, downtime etc. that might impact the customer.

## AWS Trusted advisor

Automated tool to check your usage of AWS against best practices. Different checks are applied based on the AWS Support tier. All customers get access to seven core checks.

These checks are divided into 5 categories:

* Cost Optimisation
* Performance
* Security
* Fault Tolerance
* Service Limits
