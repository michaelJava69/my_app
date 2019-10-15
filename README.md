# my_app Demo  Rails project

DevOps Demo is a demonstration of a simple CI/CD Pipeline. RAILS Project

Tools such as Github, Ansible, Docker Hub,Docker , Kubernetes/Kops, Maven, Terraform and Jenkins and AWS Cloud's EC2 instances,
AWS : S3 buckets and Route 53.

## What will happen

```bash
1. Jenkins job 1 will create an AWS kubernetes master2 and 2 nodes using KOPs and Terraform with one click of a button : duration 4 mins: wait time 5 mins 
	DevOps_Build_Terraform_Kubernetes  [run under root user or equivalent]
	DevOps_Destroy_Terraform_Kubernetes [run under root user or equivalent]
2. Jenkins Job 2 (vcs triggered) will compile/test RAILS project   ( not done)
   Push create a modified Tomcat docker container from the war file   : 
   	i. This job will run a Docker-Compose to create web tier and Database tier
   	ii. onvertert the docker compose file into Kubernetes yml files using Kubernetes-Kompose
   Push the modified container to Docker Hub
        Devops_Ansible_DockerHub_Deploy]  Part 2 Push   can be used here   
   Pull the modified container from Docker hub and deploy onto a AWS Docker Container
        Devops_Ansible_DockerHub_Deploy]  Pull     [ to be tested] 
   Pull the modified container from Docker hub and deploy onto the AWS Kubernetes cluster.
   	Devops_Ansible_Kubernetes_Deploy]  Pull    [to be done ..ran into some frustrating issues]
   
3. Jenkins kobs are declarative and stored in Github


 
##
  Note
  ```bash
      All code for application and infrastructure is stored in Github and with minimal setup will run on any Jenkins CI.
      Both infra and application code is sourced together
      Ansible and Jenkins are hosted on prem whilst Docker Contsainer and Kubernetes are hosted on AWS. AWS S3 bucket version manages the Kops cluster code.
      
  ```
  Code storage
  ```bash
     https://github.com/michaelJava69/my_app
  ```
## To be done
  ```bash
      more work on Rails in terms with Kubernetes
  ```    
 
