---
description: Managed service for in-memory cache datastore
---

# ElastiCache

The service takes care of maintenance, upgrades, etc. and provides automatic read replicas.

Scaling up and down is made is easy by adding/removing nodes.

ElastiCache is structured in a cluster consisting of multiple nodes. There are some differences based on whether you're using Memcached or Redis.

* Memcached
  * 1-20 nodes (nodes are EC2 instances running the caching software)
* Redis
  * 1 cluster contains 1 node
  * up to 6 read replicas can be added to create a replica group

#### Redis vs Memcached

Redis is almost always the better choice. It's also the industry leader. Memcached does have better memory management with small datasets. But Redis provides more features and works better at scale.

