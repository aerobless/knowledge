---
description: AWS NoSQL database service
---
NoSQL databases store data in table without much configuration. There is no schema. The main storage is a table that contains items. Items need to include the same primary key (PK). A PK can be a string, number or binary type.

**Provision Throughput Capacity**

The main configuration option for a DynamoDB is the **Provision Throughput Capacity**. This defines the read/write options per second provisioned for the DB. It tells AWS how much hardware is needed.

The read/write Throughput is based on a read/write Unit (4kb). If it is larger more units are consumed.

If the provisioned amount is exceeded AWS will throttle or deny requests.

To help with this there are two modes:

* On-demand Capacity Mode (AWS will provide whatever is needed, pay per request - more expensive, ok for prototype/analysis)
* Provisioned Capacity Auto Scaling (Increase or decrease configured capacity based on rules - better for production due to lower cost)

## RDS vs DynamoDB

Relational vs NoSQL. DynamoDB has strong storage flexibility. Querying data is easier with relational DBs. -> Storage vs Querying flexibility.

# Creating a table in DynamoDB

1. Navigate to DynamoDB
2. Create table
3. Chose name
4. Create



