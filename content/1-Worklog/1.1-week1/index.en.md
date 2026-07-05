+++
title = "Week 1 Worklog "
date = 2026-04-13
weight = 1
chapter = false
pre = " <b> 1.1. </b> "
+++

###  Basic Information
- **Full Name**: Truong Le Duy Tan
- **Student ID**: 2280602878
- **Class**: 22DTHH1
- **Major**: Information Technology
- **Internship Company**: AWS Cloud Training
- **Internship Position**: AWS Cloud Intern
- **Week Start Date**: April 13, 2026
- **Internship Week**: Week 1/12

###  Weekly Objectives
- Get familiar with the working environment, corporate culture, and reporting procedures at the internship unit.
- Receive training accounts, install necessary tools (AWS CLI, Git, VS Code), and activate account security.
- Begin the research path on foundational video lectures from the AWS training playlist recommended by the department (Focusing on Cloud Computing Overview and IAM service).

##  Tasks Performed

### 1. Internship Integration and Tool Setup
- **Description**: Attended the intern orientation session, clearly understanding the rules and the 10-week Lab roadmap. Initialized the personal working environment, successfully installed AWS CLI, Git for source code management, and VS Code for configuration editing.
- **Result**: Completed environment configuration and successfully verified the AWS CLI connection to the testing AWS Account using Access Keys.

### 2. Theoretical Research on Cloud Computing Overview and IAM
- **Description**: Watched the first video lectures in the training playlist. Learned about Cloud Computing concepts, service models (IaaS, PaaS, SaaS), and deployment models (Public, Private, Hybrid). Deeply researched the AWS Identity and Access Management (IAM) service.
- **Result**: Clearly understood the principles of authorization, the operating mechanism of the Root Account, and why the Root Account should not be used for daily configuration tasks.

### 3. Lab: Account Security Configuration and IAM Authorization
- **Description**: Accessed the AWS Console using the provided account. Configured and activated Multi-Factor Authentication (MFA) to enhance account security. Practiced creating IAM Users, assigning them to specialized IAM Groups (such as Administrator and Developer groups), and attaching corresponding IAM Managed Policies to comply with the "Principle of Least Privilege".
- **Result**: The account was secured via MFA, and IAM Users logged in and operated strictly within their granted permissions.
- **Tools/Tech**: AWS IAM, Authenticator App, AWS Console.

##  Knowledge Acquired

###  Technical Skills
- **AWS Services**: AWS IAM (Users, Groups, Policies, Roles), MFA Activation.
- **Tools**: Proficient use of the AWS Management Console and basic AWS CLI configuration.

###  Concepts & Theory
- **New Concepts**: Shared Responsibility Model between AWS and the customer. The core difference between Authentication (identity verification) and Authorization (permission granting) in cloud security.

##  Challenges & Solutions
- **Issue**: Encountered errors when executing resource check commands via AWS CLI after installation.
- **Root Cause**: Input the wrong default region format (Default Region Name) and mistyped characters in the Secret Access Key string during the `aws configure` setup.
- **Solution**: Actively looked up AWS documentation, re-ran the `aws configure` command to update the exact new security Key pair, and selected the correct Region (`ap-southeast-1`).

##  Reflection & Insights
- The first week completely changed my mindset about infrastructure. Securing the account from the very first steps on the Cloud environment is critical to protecting business resources against cyber threats.

##  Next Week's Plan
- Move to Week 2 to study and practice the core computing service: Amazon EC2 (Elastic Compute Cloud), covering launching virtual machines, configuring Security Groups, and managing Key Pairs.

##  Self Assessment
- Productivity: 8.5/10
- Learning: 8.5/10
- Collaboration: 7/10