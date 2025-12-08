---
title: "Week 8 Worklog"
date: 2025-11-02
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives:

* Explore knowledge about IoC, VPC Flow Logs, and billing.
* Complete the hands-on labs provided in the course.

### Tasks to Implement This Week:

| Day | Task                                                                                                                                                                                                                                                                                          | Start Date | Completion Date | Reference Material                                                     |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ---------------------------------------------------------------------- |
| 2   | - Run a comparison between the proposed STFA method and other augmentation techniques. <br> - Evaluate performance using multiple error metrics, including custom error measures.                                                                                                                      | 27/10/2025 | 27/10/2025      |                                                                        |
| 3   | - Learn the concept and benefits of Infrastructure as Code (IaC) for automated infrastructure management. <br> - Differentiate CloudFormation, CDK, Terraform, and Pulumi. <br> - Practice setting up Cloud9, creating an IAM Role, and deploying a Lambda Function using CloudFormation. | 28/10/2025 | 28/10/2025      | [https://000111.awsstudygroup.com/](https://000111.awsstudygroup.com/) |
| 4   | - Configure and monitor EC2 resources with Amazon CloudWatch. <br> - Install the CloudWatch Agent to collect CPU, memory, network, and disk metrics. <br> - Apply AWS EC2 Resource Optimization and Compute Optimizer to generate cost optimization recommendations.              | 29/10/2025 | 29/10/2025      | [https://000014.awsstudygroup.com/](https://000014.awsstudygroup.com/) |
| 5   | - Learn about VPC Flow Logs and how to monitor IP traffic within a VPC. <br> - Deploy network monitoring infrastructure using CloudFormation. <br> - Analyze logs using CloudWatch Log Insights to identify issues and optimize network performance.                                  | 30/10/2025 | 30/10/2025      | [https://000105.awsstudygroup.com/](https://000105.awsstudygroup.com/) |
| 6   | - Practice delegating Billing Console access to IAM Users. <br> - Create a custom IAM Policy (BillingViewAccess) and attach it to users or groups. <br> - Verify Billing Console access and clean up resources after practice.                                                            | 31/10/2025 | 31/10/2025      | [https://000106.awsstudygroup.com/](https://000106.awsstudygroup.com/) |

### Week 8 Achievements:

* A - Infrastructure as Code

    * Understood the concept and benefits of Infrastructure as Code (IaC) in automating infrastructure management through source code.

    * Distinguished among common IaC frameworks such as CloudFormation, CDK, Terraform, and understood their deployment differences.

    * Learned the role of IaC in DevOps and CI/CD for improving productivity and maintaining consistency in infrastructure deployment.

    * Practiced setting up a Cloud9 environment, creating an IAM Role with AdministratorAccess, and attaching it to an EC2 Instance.

    * Deployed a Lambda Function using a CloudFormation Template and successfully validated the created resources.

    * Implemented a sample VPC and EC2 deployment using CloudFormation and understood template structures including Parameters, Mappings, Resources, and Outputs.

    * Connected to the EC2 Instance via SSM, verified the connection, and confirmed a secure connection without opening SSH ports.

    * Explored the three-tier architecture deployment model (Bastion Host, Web Tier, App Tier, Database Tier) on AWS CloudFormation.

    * Practiced creating stacks, testing cross-tier connectivity, and cleaning up resources after deployment.

* B - Right-sizing with EC2 Resource Optimization

    * Mastered the setup, configuration, and monitoring of EC2 resources using Amazon CloudWatch to track real-time instance performance.

    * Successfully created and attached an IAM Role to EC2 for enabling the CloudWatch Agent to collect CPU, memory, network, and disk metrics.

    * Installed and configured CloudWatch Agent to include custom metrics for more accurate analysis.

    * Applied AWS EC2 Resource Optimization to identify underutilized instances and recommend cost reduction strategies.

    * Understood and applied EC2 right-sizing principles in combination with Saving Plans for cost efficiency.

    * Used AWS Compute Optimizer to analyze and receive optimization recommendations for EC2, Auto Scaling Groups, EBS, Lambda, and Fargate based on real performance data.

    * Understood the conditions and limitations of Compute Optimizer across different resource types.

* C - Network Monitoring with VPC Flow Logs

    * Gained a clear understanding of how VPC Flow Logs work and how to collect IP traffic data between network interfaces within a VPC.

    * Deployed automated network monitoring infrastructure using CloudFormation, including VPC, subnets, IAM Roles, and CloudWatch Log Groups.

    * Enabled VPC Flow Logs and configured them to send data to Amazon CloudWatch Logs for real-time network traffic monitoring.

    * Practiced log analysis using CloudWatch Log Insights to detect security, configuration, and performance issues.

    * Completed the full network monitoring workflow and understood its application in optimizing, controlling, and troubleshooting AWS environments.

* D - Billing Console Delegation

    * Learned the process of delegating Billing Console access in AWS to ensure secure financial management and proper role separation.

    * Enabled Billing access for IAM Users via “IAM User and Role Access to Billing Information” in the root account.

    * Created a custom IAM Policy (BillingViewAccess) to restrict permissions to billing and cost management only.

    * Attached the policy to IAM groups or users, ensuring precise and controlled access.

    * Successfully verified Billing Console access using the authorized IAM account.

    * Cleaned up all user groups and policies after the exercise to maintain a clean environment.
