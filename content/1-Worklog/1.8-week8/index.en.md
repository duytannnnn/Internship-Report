+++
title = "Week 8 Worklog "
date = 2026-06-01
weight = 8
chapter = false
pre = " <b> 1.8. </b> "
+++

##  Basic Information
- **Full Name**: Truong Le Duy Tan
- **Student ID**: 2280602878
- **Class**: 22DTHH1
- **Major**: Information Technology
- **Internship Company**: AWS Cloud Training
- **Internship Position**: AWS Cloud Intern
- **Week Start Date**: June 01, 2026
- **Internship Week**: Week 8/12

##  Weekly Objectives
- Research core database services on AWS, including Amazon RDS and Amazon DynamoDB.
- Explore advanced Serverless architecture patterns with AWS Lambda and Amazon API Gateway.
- Consolidate all accumulated knowledge to design the system architecture for a 3-Tier Architecture Mini Project.

##  Tasks Performed

### 1. Implementing Cloud Databases and Serverless Architectures
- **Description**: Studied relational database structures via Amazon RDS (MySQL) and NoSQL key-value document engines with Amazon DynamoDB. Provisioned a live production database instance on RDS isolated within a Private Subnet. Simultaneously explored AWS Lambda event-driven compute and methods to expose RESTful APIs out to the public Internet using Amazon API Gateway.
- **Result**: Mastered secure cloud database deployment methodologies, and learned to write Lambda functions to handle data layer logic without the overhead of operating system lifecycle tasks.

### 2. System Architecture Design for the 3-Tier Mini Project
- **Description**: Consolidated infrastructure components practiced since week 1 to draft a blueprint for the final Mini Project. The system aligns with enterprise standards: Presentation Tier (S3 Static Website Hosting paired with CloudFront CDN) -> Application Logic Tier (ECS Fargate or EC2 instances protected behind an Application Load Balancer) -> Data Tier (Amazon RDS MySQL).
- **Result**: Finalized a detailed system architecture drawing, itemizing CIDR subnet spaces and mapping security interdependencies using cross-referenced Security Groups in preparation for deployment.
- **Tools/Tech**: Amazon RDS, Amazon DynamoDB, AWS Lambda, Amazon API Gateway, Draw.io, AWS Architecture Icons.

##  Knowledge Acquired

###  Technical Skills
- **AWS Services**: Amazon RDS (MySQL), Amazon DynamoDB, AWS Lambda, Amazon API Gateway.
- **System Design**: Ability to design and deconstruct 3-tier software systems while maintaining security boundaries and infrastructure efficiency.

###  Concepts & Theory
- **New Concepts**: Serverless mindset - developers focus 100% on writing optimal logic code while the Cloud automatically dictates scaling capabilities and background operations.
- **Best Practices**: Always activate Multi-AZ deployments for Amazon RDS in Production environments to enable synchronous automated replication to an alternate Availability Zone, ensuring disaster recovery against data center outages.

##  Challenges & Solutions
- **Issue**: The AWS Lambda function failed to communicate with and query records from the newly deployed Amazon RDS instance.
- **Root Cause**: By default, AWS Lambda runs outside the VPC container network space, cutting off its direct route to the RDS Private Subnet, while the RDS Security Group rejected all traffic outside its immediate cluster.
- **Solution**: Configured the Lambda function to run inside the custom VPC, selected matching Private Subnets, and supplemented an Inbound firewall rule into the RDS Security Group allowing secure traffic coming from the Lambda function's Security Group ID.

##  Reflection & Insights
- Shifting architectural blueprints to Serverless models strips away immense deployment footprints and overhead costs because billing is metered down to the millisecond of active compute runtime instead of paying to keep idle servers running.

##  Next Week's Plan
- Participate in and follow the internal AWS cloud services knowledge competition designed for interns and trainees (Week 9).
- Conduct a deep dive into advanced cloud security components: Amazon Cognito, Trust Policies, and complex IAM Role configurations.

##  Self Assessment
- Productivity: 8.5/10
- Learning: 9/10
- Collaboration: 7/10