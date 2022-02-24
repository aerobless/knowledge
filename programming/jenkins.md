# Jenkins

## Pipelines Best Practices

* **Use separate stages**\
  When working with a project that deploys & undeploys something, e.g. a JBoss application server, it's recommended to have the deployment and undeployment in a separate pipeline stages. This is necessary because it can lead to weird errors e.g. when gradle parallel task execution and similar options are enabled and the build/test process is simultaneously testing and undeploying an application.
