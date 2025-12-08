---
title: "Week 2 Worklog"
date: 2025-09-21
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives:

* Continue building knowledge for project model development.
* Gain solid understanding of EC2, Cloud9, S3, and related services.

### Tasks to be carried out this week:

| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                  |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------- |
| 2   | - Study algorithms needed for the project: <br>&emsp; + Spherical geometry <br>&emsp; + Linear algebra & probability/statistics <br>&emsp; + Machine learning algorithms <br>&emsp; + Predict new points from old points + direction + distance | 15/09/2025 | 15/09/2025      |                                     |
| 3   | - Learn about EC2: <br>&emsp; + Main functions of the service <br>&emsp; + Deployment practice <br>&emsp; + Cost of usage                                                                             | 16/09/2025 | 16/09/2025      | <https://000004.awsstudygroup.com/> |
| 4   | - Explore Cloud9 programming IDE: <br>&emsp; + Deploy and configure basic settings <br>&emsp; + Hands-on usage                                                                                        | 17/09/2025 | 17/09/2025      | <https://000049.awsstudygroup.com/> |
| 5   | - Study Amazon S3: <br>&emsp; + Create S3 bucket and upload data <br>&emsp; + Try out main features                                                                                                   | 18/09/2025 | 18/09/2025      | <https://000057.awsstudygroup.com/> |
| 6   | - Translate log "Implement network connectivity patterns for Oracle Database@AWS" from English to Vietnamese                                                                                                                                                        | 19/09/2025 | 19/09/2025      | <https://aws.amazon.com/blogs/database/implement-network-connectivity-patterns-for-oracle-databaseaws/>                                     |


### Week 2 Achievements:

* **A – EC2**
  * Learned the basics of Amazon Elastic Compute Cloud (EC2).
    * Provides compute power and ability to launch virtual servers without upfront hardware.
    * AMI (Amazon Machine Image) used as templates for EC2 instances (OS, app server, block device mapping).
    * Storage options: Amazon EBS volumes & Instance Store volumes.

  * Explored key EC2 features:
    * Elastic Infrastructure
    * Networking Capabilities
    * Availability Zone selection
    * Resource management
    * Performance monitoring & notifications
  
  * Deployment preparation:
    * Created VPC for Windows instance
    * Created Security Group for Windows instance
  
  * Successfully launched Microsoft Windows EC2 instance and connected from local computer.
  
  * Advanced EC2 practices:
    * Modified instance type
    * Created & managed EBS Snapshots
    * Created custom AMI
    * Deployed instances from custom AMI
    * Tested recovery access for Windows instances
    * Deployed Node.js application on EC2 Windows
  
  * Learned about EC2 cost management:
    * Restricting service usage
    * Limiting EC2 usage
    * Managing EBS storage types
    * Restricting resource deletion by IP and time window
  
  * Cleaned up resources:
    * Deleted EC2 instances, AMIs, Snapshots
    * Deleted security groups, key pairs, VPC, etc.


* **B – AWS Cloud9**
  * Learned the basics of AWS Cloud9:
    * Cloud9 is a browser-based IDE
    * Provides build, run, edit, and cloud deployment support
    * Customizable IDE (themes, keyboard shortcuts, etc.)
  
  * Created Cloud9 environment:
    * Named and configured settings
    * Completed setup and waited for environment readiness
  
  * Tested basic features:
    * Used Cloud9 terminal
    * Experimented with text files
    * Tried out other available functions


* **C – Amazon S3**
  * Learned the basics of Amazon Simple Storage Service (S3):
    * Provides secure, scalable storage
    * Designed to handle all data sizes & types
    * Use cases: data warehouses, websites, mobile apps, etc.
  
  * Created S3 bucket and uploaded data
  
  * Expanded S3 usage:
    * Enabled static website hosting
    * Configured public access & object permissions
    * Tested static website
    * Accelerated website using CloudFront
  
  * Tried additional features:
    * Bucket versioning
    * Object movement
    * Cross-region replication
  
  * Cleaned up resources after experiments
