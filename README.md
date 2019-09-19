# ecs-nodejs-app-example
AWS ECS node.js app example for AWS Codepipeline

It is very simple node.js app example to configure AWS ECS service & task.
this app use dynamic port mapping of AWS ALB for ECS blue/green deployment.

# Environments

The node.js app example for these environments:

- AWS ECS Cluster : EC2 type, task container use dynamic port mapping
- AWS ECR Repositories : for task container image
- AWS Codebuild : for make ECR image
- AWS Codedeploy : for ECS blue/green deployment

# Configuration files

- Dockerfile : for AWS ECR
- appspec.yml : for AWS Codedeploy
- buildspec.yml : for AWS Codebuild
```
# Environment variables examples of AWS Codebuild

SERVICE_PORT	      20000
IMAGE_REPO_NAME	    ecs-app
AWS_ACCOUNT_ID	    111111111111
AWS_DEFAULT_REGION	us-east-1
IMAGE_TAG	          latest
MEMORY_RESV	        100
```
- taskdef.json : for ECS Task Definitions in deployment
