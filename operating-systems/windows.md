# Windows

## Useful Shell Commands

### Kill gradle daemon

`WMIC PROCESS where "Name like 'java%' AND CommandLine like '%GradleDaemon%'" Call Terminate`

``
