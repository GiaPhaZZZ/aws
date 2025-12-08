---
title: "Week 5 Worklog"
date: 2025-10-12
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

* Learn about the topics in the "Migrate to AWS" module
* Understand cost optimization with AWS Lambda

### Tasks to be carried out this week:

| Day | Task                                                                                                                                          | Start Date | Completion Date   | Reference Materials                                                    |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | ---------- | ---------------------------------------------------------------------- |
| 2   | - Continue researching for the project, draw a preliminary architecture diagram                                                               | 6/10/2025  | 6/10/2025  |                                                                        |
| 3   | - Practice VM Import/Export <br>   + Try deploying an application server <br>   + Upload and import VM to AWS                                 | 7/10/2025  | 7/10/2025  | [https://000014.awsstudygroup.com/](https://000014.awsstudygroup.com/) |
| 4   | - Practice Database Schema Conversion & Migration <br>   + Configure DMS and SCT <br>   + Perform schema conversion and data migration        | 8/10/2025  | 8/10/2025  | [https://000015.awsstudygroup.com/](https://000015.awsstudygroup.com/) |
| 5   | - Practice AWS Elastic Disaster Recovery Workshop <br>   + Configure DRS <br>   + Install agent and test failover process                     | 9/10/2025  | 9/10/2025  | [https://000016.awsstudygroup.com/](https://000016.awsstudygroup.com/) |
| 6   | - Practice Optimizing EC2 Costs with Lambda <br>   + Create Lambda functions to start/stop instances <br>   + Connect Slack for notifications | 10/10/2025 | 10/10/2025 | [https://000017.awsstudygroup.com/](https://000017.awsstudygroup.com/) |

### Week 5 Achievements:

* A – Learn about VM Import/Export

  * Understand the VM Import/Export process on AWS, including two-way migration between on-premises environments and AWS Cloud.

  * Successfully deploy an Ubuntu virtual machine in a VMWare Workstation environment:

    * Create a new VM and install Ubuntu OS.
    * Configure users, disk capacity, and OpenSSH Server for remote access.

  * Export the VM from on-premises:

    * Use the *Export to OVF* feature to generate .vmdk files for AWS import.

  * Create and configure an S3 bucket to store VM files:

    * Choose a unique bucket name and select an appropriate region.
    * Enable public access and upload the .vmdk file to S3.

  * Create an IAM Role “vmimport” and attach required policies so the VM Import/Export service can:

    * Access the S3 bucket containing the VM files.
    * Run import-image on AWS CLI to convert the VM into an AMI.

  * Deploy an EC2 Instance from the AMI:

    * Access EC2 Console and select the imported AMI.
    * Create a key pair, launch the instance, and test SSH connectivity.

  * Practice the export process from AWS:

    * Create a new S3 bucket and configure ACL to allow read/write access.
    * Use AWS CLI to export the Instance or AMI into "vhd / .vmdk" format.
    * Store the files in S3 and redeploy the VM on the on-premises system.

  * Master the two-way workflow:

    * Import: On-premises → S3 → AMI → EC2
    * Export: EC2 / AMI → S3 → On-premises

  * Complete all steps for CLI connection, AMI verification, import/export progress checking, and AWS resource management.

* B – Overview of Database Schema Conversion & Migration

  * Understand how to prepare AWS environment for database migration, including creating key pairs, configuring EC2 instances, and setting up connectivity.

  * Learn how to select and configure different database sources such as Oracle and SQL Server for AWS DMS.

  * Practice schema conversion using AWS Schema Conversion Tool (SCT) and learn how to modify procedural code when necessary.

  * Learn to set up database migration using AWS Database Migration Service (DMS), including creating replication instances, endpoints, and migration tasks.

  * Monitor migration activities via CloudWatch metrics, task logs, and event notifications.

  * Understand how DMS Serverless works and how it automatically scales under load.

  * Practice troubleshooting common migration issues such as memory errors or table errors in DMS tasks.

  * Complete environment cleanup after migration, including deleting migration tasks, replication instances, and IAM roles.

* C – AWS Elastic Disaster Recovery Workshop

  * Understand the overview of AWS Elastic Disaster Recovery (AWS DRS), including its purpose, operation, and benefits in reducing downtime and data loss.

  * Learn how to prepare infrastructure for a simulated on-premises environment for DRS practice, including subnet, DNS, and Bastion host setup.

  * Practice connecting to Bastion Host via RDP or SSH using the provided credentials.

  * Configure default DRS settings in AWS Management Console, including subnet selection, instance type, and security group.

  * Create and configure an IAM User for the DRS Agent with access rights and save the Access Key for installation.

  * Practice installing the DRS Agent on source servers (web and database) via Bastion Host, configuring AWS region, Access Key, Secret Key, and selecting disks to replicate.

  * Monitor the initial data sync and verify that DRS source servers are “Ready for recovery” and “Healthy.”

  * Perform the Failover process, including starting recovery jobs, selecting the latest data, and checking recovery progress in both DRS console and EC2.

  * Learn to check logs, monitor job history, and confirm that instances are successfully launched in AWS environment.

  * Complete familiarization with disaster recovery workflow to ensure system availability.

* D – Optimizing EC2 Costs with Lambda

  * Understand the objectives and principles of EC2 cost optimization using AWS Lambda, including automatically starting/stopping instances and using Savings Plans for continuous operation scenarios.

  * Practice creating the initial infrastructure, including VPC, Security Group, and EC2 instances for the lab.

  * Configure Slack Incoming Webhooks to receive instance status notifications directly on a Slack channel.

  * Tag the EC2 instance in the console (key: environment_auto, value: true) so Lambda can identify and manage it.

  * Create IAM Role for Lambda Function with AmazonEC2FullAccess and CloudWatchFullAccess permissions to allow EC2 management and logging.

  * Practice creating two Lambda functions:

    * stop instance – automatically stop EC2 when not needed.
    * start instance – automatically start EC2 when required.

  * Test the functions in AWS Management Console:

    * Running the start instance function launches the EC2 instance and Slack shows “Starting instance.”
    * Running the stop instance function stops the EC2 instance and Slack shows “Stopping instance.”

  * Complete the full test workflow and verify Lambda functions operate correctly, optimizing EC2 operational costs.

  * Perform resource cleanup after testing.

