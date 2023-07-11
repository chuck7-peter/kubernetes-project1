## What this does?
This repo along with https://github.com/chuck7-peter/kubernetes-project1-manifest.git creates a Jenkins pipeline with GitOps to deploy code into a Kubernetes cluster. CI part is done via Jenkins and CD part via ArgoCD (GitOps).

## Jenkins installation
Jenkins is installed on EC2. Follow the instructions on https://www.jenkins.io/doc/tutorials/tutorial-for-installing-jenkins-on-AWS/ . 

1. Install Docker on the EC2 after Jenkins is installed by following the below steps
Update the packages on your instance

[ec2-user ~]$ sudo yum update -y

Install Docker

[ec2-user ~]$ sudo yum install docker -y

Start the Docker Service

[ec2-user ~]$ sudo service docker start

Add the ec2-user to the docker group so you can execute Docker commands without using sudo.

[ec2-user ~]$ sudo usermod -a -G docker ec2-user

2. Install Git on the EC2 by running `sudo yum install git`

### Jenkins plugins

Install the following plugins for the project.
- Amazon EC2 plugin (No need to set up Configure Cloud after)
- Docker plugin  
- Docker Pipeline
- GitHub Integration Plugin
- Parameterized trigger Plugin

## ArgoCD installation 

Install ArgoCD in your Kubernetes cluster following this link - https://argo-cd.readthedocs.io/en/stable/getting_started/
