+++
title = "Week 2 Worklog "
date = 2026-04-20
weight = 2
chapter = false
pre = " <b> 1.2. </b> "
+++

##  Basic Information
- **Full Name**: Truong Le Duy Tan
- **Student ID**: 2280602878
- **Class**: 22DTHH1
- **Major**: Information Technology
- **Internship Company**: AWS Cloud Training
- **Internship Position**: AWS Cloud Intern
- **Week Start Date**: April 20, 2026
- **Internship Week**: Week 2/12

##  Weekly Objectives
- Study theory and watch video lectures 11 to 20 from the AWS training playlist.
- Explore the core computing service: Amazon EC2 (Elastic Compute Cloud).
- Practice launching virtual machines, configuring Security Group firewalls, and managing Key Pairs.

##  Tasks Performed

### 1. Researching Amazon EC2 Computing Service
- **Description**: Learned about the components that make up a cloud virtual machine: Instance Type families (t2.micro, t3.micro), Operating Systems (AMI), virtual storage volumes (EBS Volumes), and transmission security encryption mechanisms.

### 2. Practical Launching and Connecting to a Linux EC2 Server
- **Description**: 
  - Created a new Key Pair for secure authentication.
  - Launched an EC2 Instance running Ubuntu Server under the Free Tier tier.
  - Used Terminal (or Git Bash) on a local machine to execute SSH commands to remotely connect to the server via its Public IP using the Key Pair.
- **Result**: Connection successful; gained full permission to interact with and manage the server via the command-line interface.

### 3. Configuring Security Group Firewalls
- **Description**: Configured inbound and outbound traffic control rules (Inbound/Outbound Rules). Opened port 22 for SSH traffic and port 80 for HTTP traffic to prepare for running a web application.
- **Result**: Successfully secured the EC2 server, blocking unauthorized access to unassigned ports.
- **Tools/Tech**: Amazon EC2, Ubuntu, SSH, Security Group.

##  Knowledge Acquired

###  Technical Skills
- **AWS Services**: Amazon EC2, Key Pair, Security Group, AMI.
- **Linux Tools**: Basic Linux administration commands, utilizing `chmod 400` to restrict private key file access.

###  Concepts & Theory
- **New Concepts**: The nature of a Stateful Firewall in Security Groups (automatically allowing outbound response traffic if the inbound traffic is valid).

##  Challenges & Solutions
- **Issue**: Continuously received "Permission denied (publickey)" or "Bad permissions" errors when trying to SSH into the Ubuntu EC2 instance.
- **Root Cause**: The downloaded `.pem` private key file had overly broad file permissions on the local machine; Linux/macOS systems require private keys to be strictly isolated.
- **Solution**: Executed `chmod 400 <key_file_name>.pem` to restrict access strictly to the computer owner, which fixed the SSH connection.

##  Reflection & Insights
- Being able to spin up a high-performance server in less than 2 minutes instead of buying physical hardware components demonstrates the exceptional flexibility of cloud infrastructure.

##  Next Week's Plan
- Move to Week 3 to research the global object storage service: Amazon S3, practicing object lifecycle management and S3 Static Website Hosting.

##  Self Assessment
- Productivity: 9/10
- Learning: 8.5/10
- Collaboration: 7/10