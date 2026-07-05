+++
title = "Week 3 Worklog "
date = 2026-04-27
weight = 3
chapter = false
pre = " <b> 1.3. </b> "
+++

##  Basic Information
- **Full Name**: Truong Le Duy Tan
- **Student ID**: 2280602878
- **Class**: 22DTHH1
- **Major**: Information Technology
- **Internship Company**: AWS Cloud Training
- **Internship Position**: AWS Cloud Intern
- **Week Start Date**: April 27, 2026
- **Internship Week**: Week 3/12

##  Weekly Objectives
- Watch videos 21 to 30 of the training playlist regarding Amazon S3.
- Practice creating S3 Buckets, uploading/downloading, and managing object lifecycles.
- Configure S3 Static Website Hosting.

##  Tasks Performed

### 1. Theoretical Research on Amazon S3 (Simple Storage Service)
- **Description**: Studied the Object Storage model, the global unique constraint of Bucket Names, and storage classes (S3 Standard, Intelligent-Tiering, Standard-IA, Glacier) to optimize costs based on data access frequency.

### 2. Lab: S3 Configuration and Object Authorization
- **Description**: 
  - Created an S3 bucket with a globally unique name: `tan-fcj-internship-bucket`.
  - Practiced uploading document files and images to the bucket via the AWS Console.
  - Enabled Bucket Versioning to manage different versions of the same file when overwritten or accidentally deleted.
  - Configured Lifecycle Policies: Automatically transition files untouched after 30 days from Standard to S3 Standard-IA to save costs.
- **Result**: The bucket worked correctly, and the Versioning feature successfully preserved the complete file change history.

### 3. Practical Deployment of a Static Website on S3
- **Description**: Wrote simple `index.html` and `error.html` files. Uploaded them to the S3 bucket, disabled the "Block all public access" feature, and added a Bucket Policy allowing the public Internet `s3:GetObject` permissions. Enabled Static Website Hosting.
- **Result**: Successfully accessed the static webpage via the Endpoint URL provided by Amazon.
- **Tools/Tech**: Amazon S3, HTML, AWS Bucket Policy.

##  Knowledge Acquired

###  Technical Skills
- **AWS Services**: Amazon S3, S3 Object Versioning, S3 Lifecycle Rules.
- **Security**: Managing S3 access via Bucket Policies and Block Public Access controls.

###  Concepts & Theory
- **New Concepts**: The structural difference between Block Storage (EBS tied to EC2) and Object Storage (S3 independent, accessed via API/HTTP). How to design cost-optimized unstructured storage systems.

##  Challenges & Solutions
- **Issue**: After enabling Static Website Hosting and clicking the Endpoint link, the browser returned a "403 Forbidden" error.
- **Root Cause**: Although "Block all public access" was turned off globally, a JSON Bucket Policy had not yet been added to grant public read permission to the internal files.
- **Solution**: Went to Permissions -> Bucket Policy -> Added a JSON statement containing the `s3:GetObject` Action with the Principal set to `*`. Saved and reloaded the page, eliminating the 403 error and rendering the web interface successfully.

##  Reflection & Insights
- S3's speed and extreme durability (up to 99.999999999% durability) are highly impressive. Turning a storage bucket into a static website hosting environment in just a few clicks highlights the brilliant flexibility of cloud infrastructure.

##  Next Week's Plan
- Move to Week 4 to set up a basic Amazon VPC network infrastructure, separating Public and Private Subnets and configuring Internet routing.

##  Self Assessment
- Productivity: 9/10
- Learning: 8.5/10
- Collaboration: 7/10