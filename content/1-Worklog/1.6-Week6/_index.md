---
title: "Week 6 Worklog"
date: 2025-10-19
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives:

* Learn more about Grafana, Tags, and AWS Systems Manager management
* Practice with FJC labs

### Tasks to be carried out this week:

| Day | Task  | Start Date | Completion Date   | Reference Materials                                                    |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | ---------- | ---------------------------------------------------------------------- |
| 2   | - Train the model for the next coordinate prediction problem, evaluate and comment on new integrations into the model  | 13/10/2025 | 13/10/2025 |   |
| 3   | - Get familiar with Grafana and monitor AWS resources through a visual dashboard <br>   + Learn the concept, functions, and applications of Grafana in system monitoring <br>   + Install and configure Grafana on EC2 instance <br>   + Connect Grafana with CloudWatch and create a monitoring dashboard for EC2 resources                | 14/10/2025 | 14/10/2025 | [https://000029.awsstudygroup.com/](https://000029.awsstudygroup.com/) |
| 4   | - Learn about Tags and Resource Groups in AWS <br>   + Understand the key–value pair mechanism and the role of tagging in resource organization <br>   + Practice creating, deleting, and filtering resources by tag via AWS Console and CLI <br>   + Create a Tag-based Resource Group with the criteria Key=BusinessUnit, Value=Marketing | 15/10/2025 | 15/10/2025 | [https://000027.awsstudygroup.com/](https://000027.awsstudygroup.com/) |
| 5   | - Manage EC2 access through IAM and Resource Tags <br>   + Apply the Least Privilege principle and create IAM Policies with Region and Tag conditions <br>   + Create admin group (Admin Group), user (Admin User), and role ec2-admin-team-alpha                                                                                           | 16/10/2025 | 16/10/2025 | [https://000028.awsstudygroup.com/](https://000028.awsstudygroup.com/) |
| 6   | - Manage and automate multiple servers using AWS Systems Manager  | 17/10/2025 | 17/10/2025 | [https://000031.awsstudygroup.com/](https://000031.awsstudygroup.com/) |

### Week 6 Achievements:

* A - Get familiar with Grafana and monitor AWS resources through a visual dashboard

  * Learn about Grafana:

    * Understand the concept, functions, and applications of Grafana in data visualization and system monitoring.
    * Grasp key features such as visualization, dynamic dashboards, alerting, and integration with multiple data sources.

  * Prepare the AWS environment:

    * Create VPC, Subnet, Security Group, IAM User, and IAM Role for Grafana installation.
    * Launch an EC2 instance to install Grafana Server.

  * Practice installing Grafana on EC2:

    * Connect to the instance via PuTTY, update the system, and add the YUM repository.
    * Install Grafana using the command sudo yum install grafana and start the service with systemctl start grafana-server.
    * Check the service status and set it to start automatically with the system.

  * Log in and perform the initial Grafana configuration:

    * Access the interface via <PublicIPv4>:3000, log in using default credentials admin/admin.
    * Reset the password and verify the basic dashboard interface.

  * Connect Grafana with CloudWatch:

    * Configure CloudWatch as a data source using the Access Key and Secret Key of the IAM User.
    * Verify a successful connection and query data.

  * Create a resource monitoring dashboard:

    * Add a panel showing the CPUUtilization metric of the EC2 instance.
    * Save the dashboard as “Grafana-Monitoring” and share it via link.
    * Try the Explore feature to query and visualize data in real time.

* B - Learn about Tags and Resource Groups in AWS

  * Understand the key–value pair concept of tags and the role of tagging in resource management, cost allocation, access control, and automation.

  * Practice using Tags through the AWS Management Console:

    * Create an EC2 instance with tags during initialization.
    * Add, delete, and filter resources by tag.

  * Get familiar with using AWS CLI to manage tags:

    * Assign tags to existing EC2 resources using the create-tags command.
    * Create new EC2 instances and EBS volumes with tags using run-instances and create-volume.
    * Use describe-instances to view tagged resource information.

  * Create and manage Tag-based Resource Groups:

    * Build a *Tag-based* resource group with criteria Key=BusinessUnit, Value=Marketing.
    * Check the resource list in the newly created group via the Resource Groups Console.

  * Understand how to organize, group, and access AWS resources efficiently using tags and resource groups.

* C - Learn about EC2 resource access management through IAM and Resource Tags

  * Understand the Least Privilege principle in IAM and how to apply conditions in IAM Policies to restrict access by region and tag.

  * Practice creating an admin group (Admin Group) and admin user (Admin User) in IAM Console.

  * Create specialized IAM Policies for EC2 management, including:

    * ec2-list-read: allows read-only EC2 access in regions us-east-1 and us-west-1
    * ec2-create-tags: allows tagging when creating EC2 instances
    * ec2-create-tags-existing: allows tagging if the tag has Key=Team, Value=Alpha
    * ec2-run-instances: allows launching EC2 instances when region and tag conditions are met
    * ec2-manage-instances: allows starting, stopping, and terminating EC2 instances when tag and region conditions are satisfied

  * Create and attach IAM Role ec2-admin-team-alpha with the above policies, and configure the Trust relationship to allow Assume Role.

  * Practice the Switch Role mechanism and verify user permissions according to each configured IAM policy.

  * Understand how to combine IAM and Resource Tags to control access flexibly, securely, and scalably for distributed administration models.

* D - Learn and practice managing multiple servers simultaneously using AWS Systems Manager

  * Understand the function of Systems Manager in centralizing operational data, automating processes, and synchronizing resource management on AWS.

  * Practice deploying an environment with two Windows EC2 virtual machines:

    * Create VPC, subnet, and configure IAM Role to allow Systems Manager to access and manage instances.
    * Attach IAM Role to each instance to connect with Systems Manager.

  * Check Managed Nodes status in Fleet Manager, verify that two nodes (Windows-Lab-SSM-1 and Windows-Lab-SSM-2) are active and can successfully initiate terminal sessions.

  * Use Patch Manager to scan and install updates for two Windows EC2 instances:

    * Select “Scan and Install” mode to check and install patches.
    * Configure not to reboot instances after patching.
    * Monitor and verify successful updates.

  * Practice using Run Command on multiple servers simultaneously via AWS Systems Manager:

    * Execute “AWS-RunPowerShellScript” to run remote PowerShell commands.
    * Select both Windows EC2 instances as targets.
    * Enable the option to save output results to an S3 Bucket for log and error checking.

  * Complete the output verification process for each instance, confirm successful command execution, and validate correct system response.

  * Master centralized and automated multi-server management to optimize system maintenance, control access, and reduce manual operations in AWS environments.