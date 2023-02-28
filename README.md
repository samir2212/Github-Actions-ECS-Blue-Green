# Github-Actions-Docker-ECS-Blue-Green-Deployment

## Goal

- Build a pipeline to build and push image to ECR with Blue-Green Deployment.

- Blue Green Deployment being able to roll back in case of any error.

## Requirements

- Enable Blue-Green deplyment on ECS cluster.

- Create codedeploy application and enter the codedeploy application and group in the pipeline.

## Logic Regarding Task Defination

- Need to fetch the most recent from aws (using aws cli).

- Modify the template image property - (IMAGE_NAME is already defined).

- From the task definition you need to delete the following properties taskDefinitionArn, revision, status, requiresAttributes and compatibilities.

- Create a new revision from the task definition.

- Use the new task definition arn in the appspec.yaml.
