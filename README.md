# ceg3120-p4-Baileywyan
ceg3120-p4-Baileywyan created by GitHub Classroom
## Part 1: Milestone due 4/9
Setup public repo via link in pilot
Dockerize your website and test locally 
Add site and Dockerfile to repo

## Part 2: Milestone due 4/16
Set up AWS CodeBuild, have return status be used whether or not Dockerfile could be built

## Part 3: Milestone due 4/23
If success, get AWS AMI credentials(Github secrets) and upload container to ECR

## Extra Credit
Dockerize your python bot
Will require use of Github Secrets to protect API key


## Project Overview:

Run Project Locally:
  installed docker using the help guide and some assistance after the initial download I had to uninstall and reinstall for proper function and connection using WSL2, as my dependency on my newest Ubuntu version. 
  you can build a docker container with the docker build command
  using the docker run command allows you to run your docker image. This had a specific format style here: docker run -dit --name <namehere> -p 5001:80 -v "$PWD":/usr/local/apache2/htdocs/httpd:2.4

Configure AWS CLI
AWS IAM user with admin credentials:
aws_access_key_id=AKIATMNUEADG7H6GCRLY
aws_secret_access_key=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
how you installed: installation following the guide "Install the AWS CLI version 2 on Linux" had me use a handful of commands such as curl, then unzip, then finally install.
how to configure: this configuration also had a guide walkthrough, showing off Access ID and secret access, and then the region defined.

Create ECR  
  command to create: aws ecr create-repository --repository-name ceg3120/w167bxw --region us-east-1, this is for my personal repository.

Configure GitHub Secrets
AWS IAM user with admin credentials
aws_access_key_id=AKIATMNUEADG7H6GCRLY
aws_secret_access_key=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
  set secrets and secret names
  secrets: AWS_ACCESS_KEY_ID
           AWS_SECRET_ACCESS_KEY

Configure GitHub Workflow
  variables to change: AWS_REGION, ECR_REPOSITORY, ECS_SERVICE, ECS_CLUSTER, ECS_TASK_DEFINITION, CONTAINER_NAME

How to pull image with docker pull, what repo is the image in, requirements of the repo (public vs. private): To pull a docker image you would run docker pull base image
from a docker file. This would build a docker image from a Dockerfile and a context, the build's context being a set of files specified using a path or url. The image is in a git repo, and the requirements of this repo need to be private. 
Run the pulled image locally, using your system or a system on AWS as the host.
Running the pulled image locally using the docker run command after killing off other running instances of docker images.
