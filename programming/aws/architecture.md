# Architecture

## Acceptable Use Policy

* Not allowed
  * Sending unsolicited mass emails
  * Hosting or distributing harmful content
* Allowed with restrictions
  * Penetration testing is allowed but only for a list of specific services

## Shared responsibility model

Security and compliance is a shared responsibility between AWS and the customer.

AWS is responsible for the security **OF** the cloud and the customer is responsible for security **IN** the cloud.

* **AWS Responsibility**
  * Access & Training of Amazon employees
  * Global datacenters and network
  * hardware
  * configuration management for infrastructure
  * patching of cloud infrastructure and services
* **Customer Responsibility**
  * individual access to cloud resources and training -> give least privileged access
  * data security and encryption (both in transit and at rest)
  * operating system, network and firewall configuration
  * all code deployed onto cloud infrastructure
  * patching guest OS and custom applications

## AWS Well-architected Framework

Best practices across five pillars for how to create systems that create business value.

* **Operational Excellence**: Running and monitoring systems for business value
* **Security**: Protecting information and business assets
* **Reliability**: Enabling infrastructure to recover from disruptions
  * High-availability: Keep the entire solution running despite issues
  * Fault tolerance: Support failure of components. Some services can be used to provide fault tolerance for custom applications:
    * SQS (Simple Queue Service)
    * Route 53
* **Performance Efficiency**: Using only the resources that are needed (efficiently)
* **Cost Optimisation**: Achieving minimal costs for the desired value

## Compliance

Examples for common compliance standards are PCI-DSS, HIPAA, SOC 1-3, etc.

**AWS Config** provides some conformance packs for standards.

**AWS Artifact** provides self-service access to reports.

**Amazon GuardDuty** provides intelligent threat detection.
