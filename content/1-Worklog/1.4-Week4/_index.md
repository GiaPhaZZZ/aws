---
title: "Week 4 Worklog"
date: 2025-10-05
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives:

* Master basic concepts of cloud computing
* Learn AWS CloudWatch, CloudFront, CLI, …

### Tasks to be carried out this week:

| Day | Task                                                                                                                                                    | Start Date | Completion Date   | Reference Materials                                                    |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | ---------- | ---------------------------------------------------------------------- |
| 2   | - Learn about AWS CloudWatch and related concepts                                                                                                       | 29/09/2025 | 29/09/2025 | [https://000008.awsstudygroup.com/](https://000008.awsstudygroup.com/) |
| 3   | - Get familiar with AWS Command Line Interface (CLI), test operations with services <br>  + S3 Bucket <br>  + SNS <br>  + IAM <br>  + VPC <br>  + …     | 30/09/2025 | 30/09/2025 | [https://000011.awsstudygroup.com/](https://000011.awsstudygroup.com/) |
| 4   | - Research information about CloudFront and how to use it                                                                                               | 1/10/2025  | 1/10/2025  | [https://000094.awsstudygroup.com/](https://000094.awsstudygroup.com/) |
| 5   | - Learn about Amazon DynamoDB and its features <br>  + Core components <br>  + Primary Keys <br>  + Secondary Index <br>  + Naming rules and query data | 2/10/2025  | 2/10/2025  | [https://000060.awsstudygroup.com/](https://000060.awsstudygroup.com/) |
| 6   | - Standardize and complete data for the project <br> - Study the Temporal Convolutional Network model to be used during training                        | 3/10/2025  | 3/10/2025  |                                                                        |

### Week 4 Achievements:

* A – AWS CloudWatch

  * Understand that AWS CloudWatch is a monitoring and management service that provides actionable insights for AWS resources.

  * Work with Metrics, view application Logs, and create Alarms from collected Metrics.

  * Prepare to work with CloudWatch:

    * Create a stack in CloudFormation
    * Configure basic stack settings
    * Complete stack creation and deployment

  * Work with CloudWatch metrics:

    * View EC2 metrics
    * Analyze CPU utilization
    * Customize chart visualization

  * Learn about search, math expressions, and dynamic labels and experiment with them

  * Examine CloudWatch Logs in detail:

    * View logs from EC2 instances
    * Practice creating a log
    * Create metric filters to collect and transform data into CloudWatch metrics

  * Explore CloudWatch Alarms and CloudWatch Dashboards features

* B – Getting familiar with AWS Command Line Interface (CLI)

  * Understand that AWS CLI is an open-source tool allowing users to interact with AWS services via command-line shell.

  * Download AWS CLI and perform setup to start using it

  * Work with Amazon S3 via AWS CLI:

    * Create S3 Buckets
    * List buckets and objects
    * Delete objects and buckets

  * Experiment with SNS and IAM via CLI:

    * Create SNS topic
    * Create IAM groups, users, etc.
    * Check group information, add/remove access keys

  * Use CLI to interact with VPC:

    * Create VPC and its components
    * Test creating an Internet Gateway

  * Review troubleshooting scenarios when working with AWS CLI

* C – CloudFront

  * Study CloudFront with S3 Bucket as Origin

  * Create an S3 Bucket to prepare for later steps

  * Upload index.html to the newly created S3 Bucket

  * Configure settings for Amazon CloudFront

  * Test removing CloudFront from S3 after usage

* D – Amazon DynamoDB

  * Understand that Amazon DynamoDB is a NoSQL database service supporting fast and predictable performance.

  * Learn key properties of DynamoDB:

    * Core components
    * Keys
    * Secondary Index
    * Naming rules and data types
    * Additional notes on consistency and read/write capacity modes

  * Perform preparation steps:

    * Create access key, table, read/write, and update data
    * Create a global secondary index and query it

  * Practice with AWS SDK:

    * Set up AWS CLI first
    * Create table, perform read-write-update-delete operations
    * Query and scan data, delete tables after use
