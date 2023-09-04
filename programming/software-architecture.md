# 📐 Software Architecture

## Zühlke Camp Architecture Workshop (04.09.23)

### Setup

The idea is to create a software architecture for a fictional java backend application. In order to get different NFRs for all workshop participants chatGPT is used with the following prompt:

{% code overflow="wrap" %}
```
Create me a list of non-functional software requirements for a webapplication backend written in java. Limit the list to 10 entries. The requirements should be in the categories "performance", "reliability", "scalability", "automation", "availability".
```
{% endcode %}

for me this resulted in the following NFRs:

**Performance**

1. **Response Time**: All API endpoints must respond within 200 milliseconds under peak load.
2. **Throughput**: System should handle 10,000 simultaneous API requests per second.

**Reliability**

3. **Fault Tolerance**: Automatic failover to secondary server in less than 30 seconds in case of primary server failure.
4. **Data Backup**: Incremental backups every 6 hours, with full backups weekly.

**Scalability**

5. **Horizontal Scalability**: Able to add additional nodes without system downtime.
6. **Database Sharding**: Support for database sharding to distribute the load.

**Automation**

7. **Deployment Automation**: Zero-downtime deployment using CI/CD pipelines.
8. **Monitoring Automation**: Automated real-time system monitoring and alerting.

**Availability**

9. **Uptime**: 99.9% service availability, not counting scheduled maintenance.
10. **Geo-Redundancy**: Availability zones in at least 3 geographic regions for data and application failover.

### Example architecture

tbd
