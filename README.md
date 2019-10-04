# ecs-nodejs-app-example
![GitHub](https://img.shields.io/github/license/gnokoheat/ecs-nodejs-app-example) ![GitHub package.json version](https://img.shields.io/github/package-json/v/gnokoheat/ecs-nodejs-app-example) ![GitHub repo size](https://img.shields.io/github/repo-size/gnokoheat/ecs-nodejs-app-example) ![Docker Pulls](https://img.shields.io/docker/pulls/gnokoheat/ecs-nodejs-initial) ![GitHub top language](https://img.shields.io/github/languages/top/gnokoheat/ecs-nodejs-app-example) ![GitHub last commit](https://img.shields.io/github/last-commit/gnokoheat/ecs-nodejs-app-example)

AWS ECS node.js app example for AWS Codepipeline

It is very simple node.js app example to configure AWS ECS service & task.
this app use dynamic port mapping of AWS ALB for ECS blue/green deployment.

## Environments

The node.js app example for these environments:

- AWS ECS Cluster : EC2 type, task container use dynamic port mapping
- AWS ECR Repositories : for task container image
- AWS Codebuild : for make ECR image
- AWS Codedeploy : for ECS blue/green deployment

## Configuration files

- Dockerfile : for AWS Codebuild, AWS ECR
- appspec.yml : for AWS Codedeploy
- buildspec.yml : for AWS Codebuild, AWS ECR
- taskdef.json : for ECS Task Definitions in deployment

## Environment variables examples of AWS Codebuild
```
SERVICE_PORT        20000
IMAGE_REPO_NAME     ecs-app
AWS_ACCOUNT_ID      111111111111
AWS_DEFAULT_REGION  us-east-1
IMAGE_TAG           latest
MEMORY_RESV         100
```

## Related

- ECS reverse proxy : https://github.com/gnokoheat/ecs-reverse-proxy
- Infra code (Terraform) for this app : https://github.com/gnokoheat/ecs-with-codepipeline-example-by-terraform
- Get the docker hub image
```
docker pull gnokoheat/ecs-nodejs-initial:latest
```
