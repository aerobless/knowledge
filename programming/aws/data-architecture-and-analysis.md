# Data Architecture & Analysis

## AWS Storage Gateway

Storage Gateway is a hybrid-cloud storage service for merging together local storage and storage in AWS. It integrated cloud storage into your local network.

Can be deployed as VM or specific hardware appliance that runs the storage gateway software.

Storage Gateway supports S3 and EBS.

There are 3 different gateway types:&#x20;

* **Tape Gateway: **Like a tape backup. Used for backups. (VTL = Virtual Tape Library)
* **Volume Gateway: **Provides cloud based iSCSI volumes to local applications
* **File Gateway**: Store files in S3, but have a local cache for fast access. (e.g. DropBox)

## AWS DataSync

DataSync is an automated data transfer service. Leverages the DataSync agent deployed as a VM on the local network. It provides greatly improved transfer speeds due to custom protocol and optimisations.

DataSync integrates with S3, EFS, FSx (Windows File Server).

Costs are calculated per GB transferred.

## AWS Glue

Glue is a managed extract, transfer and load (ETL) service. Glue supports data in Amazon RDS, DynamoDB, Redshift and S3. Glue is executed serverless, so no EC2 instances etc. need to be provisioned.

* **Extract**: get data from where it's stored
* **Transform**: e.g. normalize data, change structure, group things
* **Load**: put data in new location

## Amazon EMR

EMR (Elastic Map Reduce) is a big-data cloud processing service using popular tools. EMR uses EC2 and S3. It operated in a clustered environment without additional configuration.

EMR supports: Apache Spark, Apache Hive, Apache HBase, Apache Flink, Apache Hudi and Presto.

## AWS Data Pipeline

Data Pipeline is a data workflow orchestration service that can be used across AWS services. Data Pipeline is also a managed ETL service (like AWS Glue). It manages the data workflow through AWS services.&#x20;

It supports S3, EMR, Redshift, DynamoDB and RDS.

Data Pipeline can also integrate and on-premise data store.

## Amazon Athena

Athena lets you query data that is stored in S3. Athena is fully-managed and serverless. Athena is useful to query large sets of data. Queries can be written in SQL.

Athena charges based on the amount of data scanned for a query.

## Amazon Quicksight

Quicksight is a business intelligence (BI) service that enables the creation of data dashboards.

Charged on per-user and per-session pricing model. There are multiple versions provided based on your needs. (different costs)

## Amazon CloudSearch

CloudSearch is a managed search service for custom applications. It supports scaling of the search infrastructure to meet demand. (Like Google Search as a Service)

CloudSearch is charged per hour and instance type.

## Amazon Rekognition

Rekognition is a fully-managed image and video recognition deep learning service. It can identify objects within images. It can identify objects and actions from videos. It can also detect specific people using facial analysis. It also supports custom labels for business objects. E.g. pictures of products.

## Amazon Translate

Translate is a fully-managed service that supports 54 languages. It can perform language identification. Translate works in batch and real-time (with streamed data).

## Amazon Transcribe

Transcribe is a fully-managed speech recognition service. It works in real-time or batch mode. The recorded speech is converted into text in custom applications. It includes a specific sub-service for medical use. Transcribe supports 31 languages.
