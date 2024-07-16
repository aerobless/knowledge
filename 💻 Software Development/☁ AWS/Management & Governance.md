# Cloud Trail

Used to log and continuously monitor and retain account activity related to actions across AWS infrastructure. Cloud Trail provides event history of AWS account activity.

Cloud Trail stores the audit trail into an S3 bucket or CloudWatch logs.

Events are logged in the regions they occur.

# AWS Cloud Watch

Provides metrics, logs and alarms for infrastructure. It collects logs, metrics and events from most AWS services. Based on those logs alarms can be configured that send alerts, e.g. via SNS, when thresholds are reached.

It can also provide visualisation of metrics and custom dashboards. (like Kibana, Grafana etc.)

# AWS Config

Continually evaluates infrastructure against a set of rules. Provides configuration history for infrastructure.&#x20;

Works against a set of rules, some are provided but you can also setup your own.

It includes conformance packs for compliance standards, e.g. PCI-DSS.

It also provides insight on how to fix things when they don't meet criteria.

# AWS Systems Manager

Provides operational data and automation across infrastructure.

It can automate tasks for common maintenance actions. E.g. update EC2 apps with new version of library.

Gives secure way to access servers using only AWS credentials.

Store commonly used parameters securely for operational use. E.g. provide app passwords.

# AWS OpsWorks

OpsWorks is a configuration management service. It provides managed instances of Chef and Puppet.&#x20;

Configuration is defined as code for servers. Chef and Puppet manages the lifecycle of those configuration changes with servers.

OpsWorks works in a hybrid cloud architecture as well. So it can be used both for on-prem and aws servers.

* OpsWorks for Chef Automate
* OpsWorks for Puppet Enterprise
* OpsWorks Stacks

# AWS Organisations with Control Tower

A service to create a multi-account environment on AWS that follows the recommended best practices in operational efficiency, security, and governance.

**Short**: Best practises for multi-account enterprise AWS setup.

It centralises users across all AWS accounts

It provides a way to create new AWS accounts based on templates

Guardrails can be enabled to prevent certain settings from being changed on child accounts.

Includes a dashboard to gain insights from all accounts.
