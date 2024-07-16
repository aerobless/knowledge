---
description: Relational Database Service
---
RDS is deployed on a EC2 instance. You choose which DB engine (PostgreSQL, mySQL, MS SQL, Oracle, MariaDB, Amazon Aurora etc.) It takes over the following tasks:

* software upgrades
* nightly db backups (window can be chosen by user, stored between 1-35 days)
* system health monitoring

RDS support multi-AZ (availability zone) deployments. If enabled a DB will be replicated to a different AZ.

RDS also supports the creation of a Read Replica of the database. It is eventually consistent with the source db.

# Creating a database

1. Navigate to RDS
2. Create database
3. Choose engine & version
4. Chose template (prod, dev/test, free)
5. Choose VPC
6. Public access: in prod this should be no
7. Create new security group
8. Create

# Notes

* [PostgreSQL: pgAdmin](https://www.postgresql.org)



