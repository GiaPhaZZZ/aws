---
title: "Week 10 Worklog"
date: 2025-11-16
weight: 10
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives:

* Understand the process of containerizing applications with Docker and deploying them on AWS Cloud.
* Get familiar with ECS, CDK, and CodePipeline to automate infrastructure and application deployment.

### Tasks to be carried out this week:

| Day | Task                                                                                                                                                                                                                      | Start Date | Completion Date   | Reference                                                              |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | ---------- | ---------------------------------------------------------------------- |
| 2   | - Learn the concepts of containers and Docker <br>  + Docker Engine, Dockerfile, Docker Image, Container                                                                                                                  | 10/11/2025 | 10/11/2025 | [https://000201.awsstudygroup.com/](https://000201.awsstudygroup.com/) |
| 3   | - Learn how to push/pull images to Docker Hub and Amazon ECR <br> - Configure VPC, EC2, and RDS to deploy containerized applications on AWS                                                                               | 11/11/2025 | 11/11/2025 | [https://000202.awsstudygroup.com/](https://000202.awsstudygroup.com/) |
| 4   | - Learn about Amazon ECS and launch types (Fargate, EC2) <br>  + Configure ECS Cluster, Task Definition, and Service <br>  + Deploy frontend and backend on ECS                                                           | 12/11/2025 | 12/11/2025 | [https://000203.awsstudygroup.com/](https://000203.awsstudygroup.com/) |
| 5   | - Deploy ECS using AWS CDK (IaC) <br>  + Create VPC, NAT Gateway, and ECS Cluster using CDK <br>  + Build ECS Service and connect to DynamoDB, API Gateway                                                                | 13/11/2025 | 13/11/2025 | [https://000204.awsstudygroup.com/](https://000204.awsstudygroup.com/) |
| 6   | - Set up CI/CD pipeline using CodePipeline, CodeBuild, and CodeDeploy <br>  + Create repository and build pipeline from GitHub or CodeCommit <br>  + Automatically build and deploy the application to ECS Fargate or EC2 | 14/11/2025 | 15/11/2025 | [https://000205.awsstudygroup.com/](https://000205.awsstudygroup.com/) |


### Week 10 Achievements :

* A - Containerization with Docker

    * Understood the full process of deploying containerized applications with Docker, from local environment to AWS Cloud.
    * Successfully configured and operated AWS services such as VPC, EC2, RDS, and ECR for containerized deployment.
    * Practiced deploying applications using Docker Images, comparing manual deployment vs Docker Compose.
    * Built and managed a container network enabling stable communication between frontend, backend, and database.
    * Pushed and managed images on Docker Hub and Amazon ECR for reuse and automated deployment.
    * Gained a clear understanding of Nginx’s role in routing and load balancing across containers.
    * Optimized development and deployment workflows by separating development and production environments.
    * Improved troubleshooting and application monitoring skills in cloud environments.

* B - Container Orchestration with Amazon ECS

    * Mastered the process of deploying containerized applications on Amazon ECS with both Fargate and EC2 launch types.
    * Successfully created and configured ECS Clusters and Task Definitions for frontend and backend services, ensuring stability and isolation.
    * Applied AWS Cloud Map Service Discovery to connect internal containers via DNS names.
    * Set up Application Load Balancer, Target Groups, and Listeners to achieve load balancing and scalability.
    * Practiced backend Blue/Green Deployment to ensure zero-downtime updates.
    * Performed Rolling Deployment for frontend to enable continuous version updates without downtime.
    * Managed and monitored containers via ECS Console and CloudWatch Logs to understand task activity within clusters.
    * Tested and verified smooth application operation across frontend, backend, and database.
    * Optimized CI/CD workflow by integrating ECR, ECS, and CodeDeploy, building a foundation for automated deployment in future projects.

* C - Infrastructure as Code for ECS with CDK

    * Understood how to deploy a Spring Boot application on AWS ECS Fargate using AWS CDK.
    * Learned the principles of Infrastructure as Code (IaC) and the benefits of using AWS CDK v2 to automate resource creation.
    * Successfully created and configured an Amazon ECR Repository for Docker image storage.
    * Deployed VPC and NAT Gateway using AWS CDK to establish a secure and isolated network environment.
    * Built ECS Cluster, Task Definitions, and ECS Service for backend microservices.
    * Created API Gateway to manage REST endpoints and connect directly to ECS Service.
    * Designed and deployed a DynamoDB Table for product data storage using AWS SDK v2 for Java.
    * Implemented application logging via CloudWatch Logs and configured AWS X-Ray for tracing and analysis.
    * Enhanced AWS infrastructure management, configuration, and deployment skills with automated and reusable IaC.

* D - CI/CD Pipeline with AWS CodePipeline

    * Understood the concepts and workflows of CI/CD (Continuous Integration / Continuous Deployment) for container deployment on AWS ECS.
    * Successfully set up CI/CD pipelines using GitLab, GitHub Actions, and AWS CodeBuild integrated with ECR, ECS, and CodeDeploy.
    * Automated the full process of building, testing, and deploying applications from source code to ECS Fargate.
    * Learned how to create and manage GitLab Runners and define pipelines using .gitlab-ci.yml and .github/workflows.
    * Integrated AWS services including CodeBuild, CodePipeline, and CodeDeploy into a seamless deployment process.
    * Used CloudWatch Container Insights to monitor container performance (CPU, memory, network, and ECS task status).
    * Configured FireLens in ECS to collect and route container logs to Amazon S3 for analysis and tracking.
    * Practiced log management, issue detection, and performance optimization via CloudWatch and FireLens.
    * Completed AWS resource cleanup (ECS, ECR, RDS, EC2, IAM, S3, VPC, NAT Gateway) to maintain a clean environment and reduce costs.
    * Strengthened DevOps knowledge, particularly in implementing modern CI/CD on a cloud-native AWS environment.

* E - Automated Deployments with AWS CodePipeline
    * Understood the end-to-end automated CI/CD deployment process for applications on EC2 using AWS CodePipeline.
    * Learned the roles and coordination among services within a pipeline — CodeCommit, CodeBuild, CodeDeploy, and CodePipeline.
    * Created an S3 bucket to store build and deployment artifacts.
    * Installed and configured the CodeDeploy Agent on EC2 via Session Manager or User Data.
    * Practiced creating repositories in CodeCommit (or GitHub as an alternative) and performing source code cloning, mirroring, and migration.
    * Set up a build project using AWS CodeBuild, configured GitHub as the source, established a Linux build environment, and stored output artifacts in S3.
    * Created an application and Deployment Group in AWS CodeDeploy, configured in-place deployment, and grouped EC2 instances by tags for automated deployment.
    * Successfully deployed a Node.js application on EC2 using CodeDeploy and verified functionality via instance DNS.
    * Built a complete CodePipeline with Source – Build – Deploy stages to automate the deployment process on code updates.
    * Tested the pipeline by committing code changes and observing the automatic execution of build and deployment steps.
    * Gained a clear understanding of the closed-loop CI/CD process on AWS — from source commit to build, test, deploy, and real-world verification.