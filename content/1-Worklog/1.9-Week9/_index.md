---
title: "Week 9 Worklog"
date: 2025-11-09
weight: 9
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives:

* Learn about modules related to Security
* Get familiar with AWS Single Sign-On and Security Hub

### Tasks to Implement This Week:

| Day | Task   | Start Date | Completion Date | Reference Material                                                     |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ---------------------------------------------------------------------- |
| 2   | - Research and prepare to integrate the trained model with AWS services      | 03/11/2025 | 03/11/2025      |                                                                        |
| 3   | - Learn about AWS IAM Identity Center (AWS SSO) <br>  + Concept, role, and benefits <br>  + Basic setup and configuration                                                   | 04/11/2025 | 04/11/2025      | [https://000121.awsstudygroup.com/](https://000121.awsstudygroup.com/) |
| 4   | - Practice IAM Identity Center <br>  + Create and assign Permission Sets <br>  + Configure multi-account access through the portal <br>  + Set up Time-based Access Control | 05/11/2025 | 05/11/2025      | [https://000122.awsstudygroup.com/](https://000122.awsstudygroup.com/) |
| 5   | - Learn about IAM Permission Boundaries <br>  + Mechanism and purpose <br>  + Comparison with Identity-based Policy                                                         | 06/11/2025 | 06/11/2025      | [https://000123.awsstudygroup.com/](https://000123.awsstudygroup.com/) |
| 6   | - Access Control with IAM Policies and Conditions <br> - Enable and configure AWS Security Hub            | 07/11/2025 | 15/11/2025      | [https://000124.awsstudygroup.com/](https://000124.awsstudygroup.com/) |

### Week 9 Achievements:

* A - Identity Federation with AWS Single Sign-On

    * Understood the concept and role of AWS IAM Identity Center (formerly AWS Single Sign-On) in centralized identity management and access control across multiple AWS accounts.
    * Learned how to set up IAM Identity Center to manage access based on the principle of least privilege, assigning permissions by user groups and project roles.
    * Successfully deployed AWS Organization and created Organizational Units (Security, Shared Services, Logging, Application) for efficient resource management and separation.
    * Practiced creating and assigning Permission Sets for users and configuring multi-account access through AWS IAM Identity Center.
    * Learned and applied Time-based Access Control to restrict permissions within specific time frames, suitable for audit or temporary project roles.
    * Created, assigned, and verified users and groups in IAM Identity Center, confirming access through the portal URL and designated roles.
    * Practiced accessing AWS CLI through IAM Identity Center using automatic authentication (OIDC), ensuring security and Zero Trust compliance.
    * Learned how to use Customer Managed Policies to reuse custom permission sets across multiple AWS accounts for flexible and consistent access management.
    * Deployed and tested Identity Store APIs (IdentityStore API) to automate user, group, and membership creation, updates, and verification.
    * Completed user and group auditing using CLI commands to ensure permissions were properly granted and time-bound, maintaining compliance and security.

* B - Permission Management with IAM Permission Boundaries

    * Understood the concept and purpose of IAM Permission Boundaries for defining the maximum allowed permissions for users or groups.
    * Learned the mechanism of Permission Boundaries — where effective permissions are the intersection between the user policy (Identity-based Policy) and the boundary policy.
    * Practiced creating a Restriction Policy that only allows operations on EC2 services within the ap-southeast-1 (Singapore) region.
    * Created an IAM user “ec2-admin” with AmazonEC2FullAccess and applied a Permission Boundary named “ec2-admin-restrict-region.”
    * Verified that the “ec2-admin” user could only create and manage EC2 instances in Singapore and was restricted from other regions such as Sydney.
    * Understood the benefits of Permission Boundaries in preventing privilege escalation and simplifying large-scale permission management.
    * Performed cleanup by deleting users and policies after testing to maintain a clean and secure environment.

* C - Access Control with IAM Policies and Conditions

    * Understood and applied the principle of least privilege when granting permissions to ensure users only access what is necessary.
    * Learned the concept and process of Assume Role and how IAM users obtain temporary credentials via AWS STS.
    * Practiced creating IAM Groups with administrative privileges for EC2 and RDS to manage users more securely and centrally.
    * Created IAM Users with different permission levels (EC2-admin-user, RDS-admin-user, Group-user, No-permission-user) to simulate real-world access scenarios.
    * Configured IAM Roles with Admin privileges and established Trust Relationships to allow IAM Users to perform Assume Role operations.
    * Applied Conditions in IAM Roles to restrict access by IP address or time, enhancing security and fine-grained access control.
    * Verified successful role-switching according to defined conditions and cleaned up resources after completion.

* D - AWS Security Hub

    * Understood the role of AWS Security Hub in aggregating, organizing, and prioritizing security alerts from multiple AWS services such as GuardDuty, Inspector, and Macie.
    * Learned the operating mechanism of Security Hub in visualizing risks through an intuitive dashboard to easily track security posture and compliance.
    * Learned how to activate Security Hub in the AWS Management Console and select compliance standards such as AWS Foundational Security Best Practices, CIS AWS Foundations Benchmark, and PCI DSS.
    * Monitored and evaluated the AWS account’s Security Score under each standard to identify and address potential risks and vulnerabilities.
    * Understood the relationship between Security Hub and AWS Config and learned how to enable AWS Config to record resources necessary for compliance assessments.
    * Practiced removing irrelevant findings and managing the activation or deactivation of security standards based on actual project needs.
    * Completed the process of monitoring, assessing, and optimizing AWS account security posture based on applicable compliance frameworks.

