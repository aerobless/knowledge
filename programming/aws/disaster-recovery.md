---
description: >-
  Disaster Recovery is about preparing for any event that has a negative impact
  on a company's business.
---

# Disaster Recovery

## Strategy: Backup & Restore

Create a backup and restore the entire backup by starting up a new infrastructure.

## Pilot Light

Create a backup and keep downscaled core services running for a faster startup.

## Warm Standby

Create a backup and keep a downscaled version of the entire environment running. In the event of a disaster the environment is scaled up.

## Multi Site

The entire environment is deployed into multiple locations. If a disaster occurs a failover to the other location happens. This has the shortest time to recovery but is the most expensive.

## How to choose

*   **RTO: Recovery Time Objective**

    The time it takes to get the systems back up and running to their ideal state.
*   **RPO: Recovery Point Objective**

    The amount of data loss (in terms of time) for a prod system during the disaster event.
