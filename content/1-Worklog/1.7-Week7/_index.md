---
title: "Week 7 Worklog"
date: 2025-10-26
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives:

* Continue learning about AWS services
* Gain more knowledge about AWS CloudFormation and CDK

### Tasks to be carried out this week:

| Day | Task                                                                                                                                                                                                                                                                                              | Start Date | Completion Date | Reference Materials                                                    |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ---------------------------------------------------------------------- |
| 2   | - Evaluate whether the model meets the requirements of the business problem. <br> - Re-train the model to improve accuracy and ensure other requirements are met.                                                                                                                                 | 20/10/2025 | 20/10/2025      |                                                                        |
| 3   | - Get familiar with Amazon Systems Manager and the centralized management mechanism for AWS resources. <br> - Understand the function of Session Manager for secure EC2 access without SSH. <br> - Practice creating VPC, subnet, EC2, IAM Role, and successfully connecting via Session Manager. | 21/10/2025 | 21/10/2025      | [https://000014.awsstudygroup.com/](https://000014.awsstudygroup.com/) |
| 4   | - Learn about AWS CloudFormation and the mechanism for deploying infrastructure as code. <br> - Understand the structure of CloudFormation Template and Intrinsic Functions. <br> - Practice creating a Stack, granting permissions to Cloud9 Role, and detecting Drift.                          | 22/10/2025 | 22/10/2025      | [https://000052.awsstudygroup.com/](https://000052.awsstudygroup.com/) |
| 5   | - Understand the concept of AWS CDK and its relationship with CloudFormation. <br> - Set up the CDK environment and initialize a project using Cloud9. <br> - Practice creating VPC, subnet, IAM Role, Security Group, and deploying EC2 using CDK.                                               | 23/10/2025 | 23/10/2025      | [https://000037.awsstudygroup.com/](https://000037.awsstudygroup.com/) |
| 6   | - Extend CDK infrastructure deployment with API Gateway, ECS, ELB, and Lambda. <br> - Practice creating ECS Cluster, deploying Nginx on Fargate with Load Balancer. <br> - Connect API Gateway and Lambda with S3 to return dynamic data.                                                         | 24/10/2025 | 24/10/2025      | [https://000076.awsstudygroup.com/](https://000076.awsstudygroup.com/) |


### Week 7 Achievements:

* A - Work with Amazon Systems Manager - Session Manager

  * Get familiar with and practice Amazon Systems Manager, understanding its mechanism for centralized AWS resource management.

  * Understand the function of Session Manager for secure EC2 Instance access and management without opening SSH port (22) or using a Bastion Host.

  * Practice creating and configuring a complete environment including:

    * VPC, Public Subnet, Private Subnet, Security Group
    * EC2 Instances (Linux & Windows)
    * IAM Role allowing EC2 to interact with Systems Manager

  * Successfully connect to the Public Instance via Session Manager, confirming that no SSH traffic occurs and only HTTPS is used, ensuring secure connection.

  * Configure VPC Interface Endpoints (ssm, ssmmessages, ec2messages) to connect to the Private Instance without the Internet, enhancing internal network security.

  * Deploy and test Session Logs:

    * Create an S3 Bucket to store session logs and command history.
    * Create an S3 Gateway Endpoint for internal data transfer.
    * Check and verify successful log storage.

  * Practice Port Forwarding via AWS CLI:

    * Configure RDP port forwarding from the local machine to the Windows Instance in the Private Subnet.
    * Successfully log in via Remote Desktop using internal port forwarding.


* B - AWS CloudFormation

  * Understand AWS CloudFormation – a service that enables describing and deploying AWS infrastructure as code (IaC), automating resource creation and management safely and repeatedly.

  * Learn to use CloudFormation Templates to model infrastructure through key components:

    * AWSTemplateFormatVersion
    * Description
    * Parameters
    * Resources
    * Outputs

  * Practice creating and editing CloudFormation Templates in AWS Cloud9, a web-based IDE supporting multiple programming languages (Python, JavaScript, PHP, etc.).

  * Install and configure required tools in Cloud9 Workspace, including:

    * jq, gettext, bash-completion, moreutils
    * cfn-lint (syntax checker for CloudFormation)
    * taskcat (automated template testing)

  * Understand and apply Intrinsic Functions in CloudFormation:

    * !Ref – reference parameter or resource values
    * !Sub – substitute variables in strings
    * !GetAtt – retrieve attributes from created resources

  * Successfully create basic resources using CloudFormation Template:

    * Security Group allowing port 80 (HTTP)
    * IAM Role & Instance Profile allowing EC2 to interact with SSM and CloudWatch
    * EC2 Instance automatically attached with IAM Role and Network Interface

  * Practice creating a CloudFormation Stack directly from Cloud9 via AWS CLI and grant Cloud9 Role the necessary permissions (AmazonEC2FullAccess, IAMFullAccess) to execute stack creation.

  * Understand the concept of Drift Detection – identifying discrepancies between actual infrastructure state and CloudFormation configuration.

  * Get familiar with advanced topics: Custom Resources, Mapping, StackSet, and Macro – for automating, extending, and managing complex infrastructure deployment.


* C - CDK Basic

  * Understand AWS CloudFormation and how to deploy infrastructure as code (IaC).

  * Learn the relationship between CloudFormation and AWS CDK, where CDK serves as an abstraction layer to define AWS infrastructure using popular programming languages such as Python, TypeScript, JavaScript, Java, and C#.

  * Install and initialize the AWS CDK working environment via Cloud9 IDE.

  * Practice initializing a CDK project.

  * Understand CDK workflow:

    * Write infrastructure code in Python
    * CDK synthesizes code into a CloudFormation Template (using cdk synth)
    * Deploy actual AWS resources via cdk deploy

  * Practice creating a VPC and public subnet using CDK.

  * Create and attach IAM Role for EC2 Instance, configure Security Group.

  * Deploy an EC2 Instance on the created VPC using AWS CDK.

  * Deploy infrastructure using cdk deploy and verify results in AWS Management Console.

  * Access the created EC2 Instance and check Apache Web Server operation via Public IP.

  * Understand the full CDK workflow: define – synthesize – validate – deploy – verify.


* D - CDK Basic - 2

  * Understand how to extend AWS infrastructure deployment with CDK by integrating multiple services such as API Gateway, ECS, Elastic Load Balancer, and Lambda.

  * Practice creating an ECS Cluster and deploying a sample Nginx application on Fargate with an Application Load Balancer.

  * Configure API Gateway to route requests to ECS services through the Load Balancer.

  * Create and configure a Lambda function to access an S3 Bucket, read and list objects within it.

  * Practice connecting Lambda with API Gateway and test dynamic data responses from S3.

  * Understand how to manage Python virtual environments and install dependencies when working with CDK.

  * Learn about Nested Stack and how to divide CDK architecture into sub-stacks for better scalability and maintainability.

  * Complete deployment and validation of the full advanced CDK architecture on AWS.
