# AWS CodeCommit

CodeCommit is a managed git source code repository, like for example GitHub. Access can be controlled with IAM policies.

# AWS CodeBuild

Build / Continuous integration service, e.g. like Jenkins. The service is fully managed, so you're charged per minute for the used compute resources.

# AWS CodeDeploy

Takes care of deploying built artefacts to AWS services. Deploys to EC2, Fargate (container service), Lambda and on-premise servers. CodeDeploy provides a dashboard where you can see that status and also manually kick of deployments.

# AWS CodePipeline

Creates a pipeline of the above three services. Build, test and deploy. It also integrates with GitHub and other developer tools.

# AWS CodeStar

CodeStar is a workflow tool that automates the use of the services mentioned above. It creates a complete continuous delivery toolchain for custom applications.

It also provides custom dashboards and configurations in the AWS Console.

You are only charged for the leveraged services. CodeStar itself is free.

# 
