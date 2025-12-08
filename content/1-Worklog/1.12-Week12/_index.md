---
title: "Week 12 Worklog"
date: 2025-11-30
weight: 12
chapter: false
pre: " <b> 1.12. </b> "
---

### Week 12 Objectives:

* Understand the concept of Data Lake and the core components on AWS (S3, Glue, Athena, QuickSight)
* Practice ingesting, processing, querying, and visualizing data on AWS
* Get familiar with serverless analytics and machine learning workflow using SageMaker

### Tasks to carry out this week:

| Day | Task                                                                                                                                                    | Start Date | Completion Date | Reference                                                              |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | ---------------------------------------------------------------------- |
| Mon | - Read about Data Lake introduction on AWS                                                                                                                | 24/11/2025 | 24/11/2025      | [https://000035.awsstudygroup.com/](https://000035.awsstudygroup.com/) |
| Tue | - Query data using Athena <br> - Practice statistics and data analysis                                                                                      | 25/11/2025 | 25/11/2025      | [https://000070.awsstudygroup.com/](https://000070.awsstudygroup.com/) |
| Wed | - Visualize data using QuickSight <br> - Create Dataset, Visual, Analysis, basic Dashboard <br> - Share Dashboard with other users                            | 26/11/2025 | 26/11/2025      | [https://000073.awsstudygroup.com/](https://000073.awsstudygroup.com/) |
| Thu | - Practice Athena Spark for ETL and data processing <br> - Create federated queries connecting multiple sources <br> Monitor session, DPU, notebook history | 27/11/2025 | 27/11/2025      | [https://000106.awsstudygroup.com/](https://000106.awsstudygroup.com/) |
| Fri | - Get familiar with SageMaker Studio and Feature Store <br> - Feature engineering using Data Wrangler                                                       | 28/11/2025 | 28/11/2025      | [https://000200.awsstudygroup.com/](https://000200.awsstudygroup.com/) |


### Week 12 Achievements:

* A - Data Lake Fundamentals on AWS

  * Understand Data Lake and the main components:

    * Amazon S3 for data storage
    * AWS Glue for data management and ETL
    * Amazon Athena for data querying
    * Amazon QuickSight for data visualization

  * Created IAM role for AWS Glue and attached necessary policies

  * Created S3 bucket for storing data and set up Delivery Stream for data collection

  * Generated sample data to test ingest and analysis workflows

  * Used AWS Glue Crawler to ingest data from S3 into Data Catalog:

    * Created Crawler summitcrawler
    * Created database summitdb
    * Ran Crawler and verified raw data tables

  * Used Amazon Athena to query data:

    * Executed SQL queries to inspect data
    * Performed statistical queries, e.g., counting by activity_type

  * Created and used SageMaker Notebook for data processing and transformation:

    * Initialized interactive session
    * Ran Python code to clean, transform, and analyze data

  * Used Amazon QuickSight to visualize data:

    * Created Data source and Dataset from S3/Athena
    * Built Visuals, Analysis, and Dashboard
    * Shared Dashboard with other users

  * Capable of implementing a full Data Lake workflow on AWS, from ingestion, processing, querying to visualization

* B - Building a Data Lake with Your Own Data

  * Explored serverless Data Lake construction on AWS with core components:

    * Amazon S3 for raw and processed data
    * AWS Glue DataBrew for data cleaning, normalization, and transformation
    * AWS Glue Crawler and Jobs to create Data Catalog and convert data to Parquet
    * Amazon Athena for SQL queries
    * Amazon QuickSight for visualization

  * Used Glue DataBrew to clean and transform data:

    * Data profiling, cleaning, transforming
    * Prepared next dataset
    * Uploaded processed data to another S3 bucket

  * Set up AWS Glue for data ingestion workflow:

    * Created IAM Role with necessary permissions
    * Created Data Catalog with Glue Crawler
    * Ran Glue Jobs to convert CSV to Parquet
    * Created new Data Catalog for Parquet data
    * Verified schema for Athena queries

  * Queried data with Amazon Athena:

    * Executed basic and advanced queries (join, partition, view)
    * Compared columnar vs row-based data

  * Visualized data with Amazon QuickSight:

    * Registered and configured access permissions
    * Connected dataset and modified data
    * Built Visuals, Analysis, and Dashboard

  * Performed cleanup after workshop:

    * Unregistered QuickSight and deleted IAM Roles
    * Deleted Workflows, Jobs, Crawlers, and Databases on AWS Glue
    * Emptied and deleted S3 buckets
    * Deleted Cloud9 instance

* C - Business Intelligence with Amazon QuickSight

  * Learned to build dashboards and visualize data in QuickSight:

    * Key concepts: Data source, Dataset, Analysis, Visual, Dashboard
    * Connected data from S3, Athena, or other sources
  * Prepared QuickSight environment:

    * Created QuickSight Enterprise account
    * Connected and registered sample dataset (sales.csv)
    * Set permissions and region (Singapore)
  * Built basic dashboard:

    * Updated Dataset
    * Created Line Chart, Pie Chart, Pivot Table, key statistics
    * Completed dashboard to summarize information
  * Enhanced dashboard:

    * Used Sheets to organize pages
    * Applied Themes to customize colors, fonts, and spacing
    * Configured field format and visual format for each chart
    * Added data details and secondary charts for better visualization
  * Created interactive dashboard:

    * Saved dashboard backup
    * Set up filter layers and navigation actions
    * Published dashboard and shared with other users

* D - Serverless Analytics with Amazon Athena

  * Learned about Amazon Athena and key features:
    * Serverless interactive analytics, supports SQL and Python queries directly on S3 or other sources
    * Supports multiple sources: S3, RDS, Redshift, on-premises, and other cloud services
    * Integrated with AWS Glue Data Catalog for metadata and schema management


  * Used Athena for Apache Spark:
    * Created Workgroup using Spark engine
    * Created Notebook, executed calculations, monitored/debugged via CloudWatch Logs
    * Interacted with data from Glue Data Catalog, S3, and other sources
    * Performed ETL, data normalization, and stored results in S3

  * Visualized data in Athena Spark:
    * Used Matplotlib and Seaborn for statistical plots, data analysis, and reports
    * Integrated additional Python libraries via pip and S3

  * Managed sessions and Workgroup:
    * Monitored session details, compute history, DPU usage, execution status, and notebook results
    * Used Workgroup to manage Notebooks, Sessions, and calculations

  * Athena Federation:
    * Ran federated queries across multiple sources using familiar SQL
    * Supported connectors for RDS, MySQL, PostgreSQL, Redshift
    * Combined data from multiple sources, saved results to S3 for further analysis
    * Created Lambda function and VPC endpoint for federated data connection

* E - Machine Learning with Amazon SageMaker

  * Learned Amazon SageMaker Immersion Day concepts:
    * Full ML workflow: feature engineering, training, tuning, deploying models
    * Transition ML workloads from traditional environment to SageMaker
    * Basics of Model Debugging, Model Monitoring, AutoML, AWS ML Well-Architected assessment

  * Prepared SageMaker environment:
    * Created SageMaker Studio in Singapore region
    * Created user sagemakeruser and default Execution role
    * Initialized first Python 3 Notebook and opened Studio
    * Cloned GitHub repo amazon-sagemaker-immersion-day into Studio

  * Feature Engineering with Data Wrangler:
    * Imported bank-additional-full.csv from S3
    * Explored data, identified types, created summary analysis
    * Analyzed correlation between features and target variable y

  * Used SageMaker Feature Store:
    * Stored standardized features for team use in training/inference
    * Tracked metadata and versioning
    * Exported features offline for training preparation

  * Exported data to S3:
    * Retrieved data from Feature Store into Pandas DataFrame
    * Split into train, test, validation sets
    * Converted data to CSV/libSVM for XGBoost
    * Uploaded data to S3 for training

  * Trained, tuned, and deployed XGBoost:
    * Used built-in SageMaker XGBoost algorithm
    * Performed training and automatic hyperparameter tuning
    * Deployed model to endpoint and evaluated performance
