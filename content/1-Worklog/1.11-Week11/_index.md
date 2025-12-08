---
title: "Week 11 Worklog"
date: 2025-11-23
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives:


* Get familiar with AWS serverless services
* Hands-on experience with AWS SAM, Cognito, and related tools

### Tasks to carry out this week:

| Day | Task                                                                                                                                                                                     | Start Date | Completion Date | Reference                                                              |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ---------------------------------------------------------------------- |
| Mon | - Learn how to deploy the Java SpringBoot Monolith TravelBuddy application on AWS                                                                                                          | 17/11/2025 | 17/11/2025      | [https://000050.awsstudygroup.com/](https://000050.awsstudygroup.com/) |
| Tue | - Create CloudFormation stack, Key Pair, RDS MySQL <br> - Import TravelBuddy project into Eclipse and run locally                                                                            | 18/11/2025 | 18/11/2025      | [https://000052.awsstudygroup.com/](https://000052.awsstudygroup.com/) |
| Wed | - Learn Lambda and serverless microservices <br> - Create Java Lambda function, test locally, upload to AWS <br> - Connect Lambda with S3 trigger                                              | 19/11/2025 | 19/11/2025      | [https://000078.awsstudygroup.com/](https://000078.awsstudygroup.com/) |
| Thu | - Deploy Node.js Lambda function to process S3 and DynamoDB <br> Configure IAM role, memory, timeout, environment                                                                          | 20/11/2025 | 20/11/2025      | [https://000080.awsstudygroup.com/](https://000080.awsstudygroup.com/) |
| Fri | - Deploy SAM project, create API Gateway and Lambda functions <br> - Configure front-end with REST API on S3 <br> - Create Cognito User Pool, authentication flow, and test registration/login | 21/11/2025 | 21/11/2025      | [https://000081.awsstudygroup.com/](https://000081.awsstudygroup.com/) |


### Week 11 Achievements:

* A - Monolith to Microservices Migration

  * Learned how to deploy the Java SpringBoot TravelBuddy application on AWS
  * Used CloudFormation to provision and verify AWS resources
  * Utilized AWS Tools for Eclipse and Elastic Beanstalk CLI to deploy and update the application
  * Used AWS SDK to query and manipulate AWS resources programmatically

  * Prepared environment before deployment:

  * Created Key Pair to access instances
  * Created CloudFormation stack
  * Connected to Windows Instance
  * Set up MySQL database on RDS
  * Downloaded TravelBuddy project

  * Tested project on Eclipse IDE:

  * Imported Maven project into Eclipse
  * Configured environment variables for RDS connection (JDBC_CONNECTION_STRING, JDBC_UID, JDBC_PWD)
  * Created internal Tomcat server to run the application
  * Ran application and checked data from RDS

  * Deployed application on Elastic Beanstalk:

  * Exported WAR file from Eclipse
  * Created Elastic Beanstalk Application and Environment
  * Configured environment: High availability, VPC, Load Balancer, Subnet, Security Groups, Instance type, EC2 Key Pair
  * Set environment variables in Elastic Beanstalk matching RDS
  * Deployed WAR file and accessed application via Elastic Beanstalk URL

  * Application update (Update Application):

  * Edited index.jsp
  * Built new WAR file using Maven (mvn package)
  * Used Elastic Beanstalk CLI (eb init` + `eb deploy) to update application
  * Verified changes on the website

  * Query API and manipulate AWS through Eclipse IDE:

    * Imported EC2Report Maven project
    * Updated EC2Manager.java to query correct region
    * Ran JUnit Test to retrieve EC2 instance information
    * Practiced reading tags, instance info, and creating new instances via AWS SDK

  * Managed entire workflow from local development, build, deployment, to AWS resource management and queries

* B - Building Microservices

  * Learned to create and deploy serverless microservices on AWS using Lambda
  * Prepared environment and configured Eclipse IDE for Lambda function development

  * Created and tested Lambda microservices locally:

  * Created Java Lambda project in Eclipse
  * Updated pom.xml to use latest Mockito version
  * Ran JUnit Test with JSON payload simulating S3 events
  * Handled URL-encoded keys in LambdaFunctionHandler

  * Uploaded and tested Lambda on AWS:

  * Created new Lambda function named TestLambda
  * Uploaded code from Eclipse and selected IAM role LambdaRole
  * Connected Lambda to S3 bucket for automatic triggering

  * Extended serverless microservices:
    * Created Lambda ImageManager to generate thumbnails for JPG files and delete other files
    * Used AWS SAM and CloudFormation for automated deployment of Lambda, triggers, and S3 bucket
    * Updated Lambda permissions as needed

  * Configured orchestration with CodeStar:
    * Created new branch and managed CI/CD pipeline
    * Redeployed microservices upon code updates
    * Updated target region for API

  * Optional advanced exercises:

    * Created Lambda function to process various file types
    * Configured S3 trigger to invoke Lambda for uploaded images
    * Deployed and configured Lambda function automatically
    * Connected microservice to RDS within VPC
    * Deployed microservices using AWS Developer Tools and CI/CD automation

* C - Serverless Backend with Lambda, S3, and DynamoDB

  * Hands-on with serverless architecture and AWS Lambda
  * Created Lambda function to handle S3 events for resizing and managing images
  * Configured source and destination S3 buckets, set up event notifications
  * Set up IAM role and policy for Lambda with least privilege
  * Configured memory, timeout, and environment variables for Lambda function
  * Deployed Node.js Lambda, tested image processing pipeline, logging, and CloudWatch monitoring
  * Created DynamoDB table with appropriate write capacity
  * Created Python Lambda function to write data into DynamoDB (book_create)
  * Configured runtime, function name, and wrote code to handle event data and HTTP responses
  * Deployed and tested Lambda function with correct permissions
  * Applied serverless best practices: error handling, logging, least privilege, throughput management


* D - Deployment Automation with AWS SAM

  * Installed SAM CLI and configured AWS credentials for sam-admin
  * Created sample SAM project using sam init
  * Created front-end S3 bucket with static web hosting and public access policy via SAM template
  * Built, validated, and deployed SAM application using sam build, sam validate, sam deploy --guided
  * Created DynamoDB table for book data storage
  * Deployed Python Lambda functions for listing, writing, deleting data, and image resizing
  * Configured API Gateway with GET, POST, DELETE endpoints interacting with Lambda functions
  * Tested APIs using Postman: listing, creating, and deleting items
  * Connected front-end to REST API, updated configuration, uploaded to S3, and tested functionality


* E - User Authentication with Amazon Cognito

  * Studied documentation, installed SAM CLI and AWS CLI, configured AWS credentials

  * Built front-end from FCJ-Serverless-Workshop repository and uploaded to S3 bucket

  * Created Cognito User Pool:
    * Selected traditional web application with email authentication
    * Created App client cognito-fcj-book-shop, saved Client ID and Secret
    * Enabled ALLOW_USER_PASSWORD_AUTH authentication flow

  * Updated template.yaml with Cognito Client ID/Secret, deployed Lambda functions for registration/login

  * Created Registration function in SAM with registerPathPart

  * Deployed Lambda and API Gateway:

    * Built, validated, and deployed SAM project
    * Retrieved Invoke URL to connect front-end

  * Tested front-end:
    * Updated APP_API_URL in config.js
    * Built and uploaded front-end to S3
    * Registered user and confirmed email
    * Logged in and tested features: Create book, Management, Order access according to permissions

  * Completed authentication flow with Cognito, Lambda, and API Gateway, ensuring users can only access features after logging in
