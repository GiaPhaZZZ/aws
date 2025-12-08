---
title: "Week 3 Worklog"
date: 2025-09-28
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

* Learn key concepts about Amazon Lightsail.  
* Understand the scaling process for EC2 instances.  

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ----- | ----------- | ---------------- | ------------------ |
| 2 | - Study the origin and characteristics of time-series data prepared for model training. <br> - Propose algorithms to diversify data and enrich patterns during model training. | 22/09/2025 | 22/09/2025 | |
| 3 | - Learn about Amazon Lightsail Workshop and related information. <br> - Practice using service features. | 23/09/2025 | 23/09/2025 | <https://000045.awsstudygroup.com/> |
| 4 | - Explore the functionalities of Amazon Lightsail Containers. <br> - Create and test container instances. | 24/09/2025 | 24/09/2025 | <https://000046.awsstudygroup.com/> |
| 5 | - Study EC2 Auto Scaling concepts: <br>&emsp; + Manual Scaling <br>&emsp; + Dynamic Scaling <br>&emsp; + Scheduled Scaling <br>&emsp; + Predictive Scaling | 25/09/2025 | 25/09/2025 | <https://000006.awsstudygroup.com/> |
| 6 | - Translate the technical blog titled "Introducing Universal Installers for AWS CLI v2 on macOS" | 26/09/2025 | 26/09/2025 | <https://aws.amazon.com/blogs/devops/introducing-universal-installers-for-aws-cli-v2-on-macos/> |


### Week 3 Achievements:

* A – Amazon Lightsail Workshop

  * Explored 3 applications available on Lightsail:
    * WordPress  
    * PrestaShop  
    * Akaunting  

  * Deployed a database on Lightsail:
    * Created specific login credentials  
    * Selected the standard $15 database plan  
    * Set up a name, added key–value tags, and completed database creation  

  * Tested WordPress instance creation:
    * Chose and deployed a WordPress server  
    * Configured Ubuntu and networking settings  
    * Followed setup instructions to configure and finalize WordPress installation  

  * Created a PrestaShop E-Commerce instance:
    * Learned that PrestaShop allows users to create an online store and integrate desired payment gateways  
    * Deployed a $5 PrestaShop instance following provided guidelines  
    * Configured network connections and achieved successful deployment  

  * Experimented with an Akaunting instance:
    * Understood that Akaunting is designed for financial management and can integrate with WordPress and PrestaShop  
    * Created a $5 instance from the available plan  
    * Configured connections and completed deployment  

  * Security setup:
    Configured security for all three instances, reviewed larger plan options, and added alarms.  

* B – Amazon Lightsail Container

  * Understood the basic concepts of Lightsail Containers used to run applications.  
  * Completed necessary preparation steps.  
  * Successfully created a container service.  
  * Deployed a container from a Public Image.  

  * Tested deployment from a local system:
    * Created a Lightsail instance and configured AWS CLI as instructed  
    * Installed Docker on Ubuntu and built a container image  
    * Pushed the created image and deployed it successfully  
    * Cleaned up resources after practice  


* C – EC2 Auto Scaling

  * Studied EC2 Auto Scaling and its different strategies:
    * Manual Scaling  
    * Dynamic Scaling  
    * Scheduled Scaling  
    * Predictive Scaling  

  * Preparation steps:
    * Created VPC environment, EC2 instance, and RDS database instance
    * Set up data for the database and deployed a web server  
    * Prepared data for predictive scaling, uploaded to CloudWatch, and validated  

  * Learned about AMI and Launch Templates:
    * Created an Amazon Machine Image (AMI) from an EC2 instance  
    * Built a Launch Template
    * Performed all required configurations  

  * Load Balancer setup:
    * Studied Elastic Load Balancing (ELB)
    * Created an Application Load Balancer Target Group
    * Configured and launched the load balancer from EC2  

  * Auto Scaling Group:
    * Successfully tested and created an Auto Scaling Group to manage EC2 instances  

  * Scaling solution testing:
    * Tested manual, scheduled, and dynamic scaling  
    * Interpreted results from predictive scaling solutions  