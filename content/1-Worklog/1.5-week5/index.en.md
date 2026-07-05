+++
title = "Week 5 Worklog "
date = 2026-05-11
weight = 5
chapter = false
pre = " <b> 1.5. </b> "
+++

##  Basic Information
- **Full Name**: Truong Le Duy Tan
- **Student ID**: 2280602878
- **Class**: 22DTHH1
- **Major**: Information Technology
- **Internship Company**: AWS Cloud Training
- **Internship Position**: AWS Cloud Intern
- **Week Start Date**: May 11, 2026
- **Internship Week**: Week 5/12

##  Weekly Objectives
- Complete up to video 107 of the AWS training playlist.
- Research hybrid storage solutions using AWS Storage Gateway, linking File Gateway with Amazon S3.
- Configure and successfully mount an SMB File Share on a Windows Server environment.
- Attend the AWS Vietnam Community Day technology event to consolidate real-world insights into GenAIOps, Agentic AI, and Multi-Agent architecture for enterprise operations.

##  Tasks Performed

### 1. Theoretical Research on Advanced Storage and AWS Storage Gateway
- **Description**: Consolidated core knowledge regarding EC2, VPC, and S3. Watched video lectures on Hybrid Cloud Storage and studied the mechanics of File Storage in the Cloud. Investigated how AWS Storage Gateway connects traditional On-Premises infrastructure with AWS cloud storage services, focusing on the File Gateway model combined with Amazon S3.
- **Result**: Understood the principles of data storage, caching, cloud synchronization, and local network file-sharing protocols (SMB and NFS).

### 2. Deploying an SMB File Share and Mounting on Windows Server
- **Description**: Practiced on the AWS Console to initialize a File Gateway and link it to an Amazon S3 bucket. Configured an SMB (Server Message Block) file share and set up Guest Access permissions. Launched a Windows Server instance on EC2 to simulate a local environment. Configured Security Groups for the Storage Gateway and mapped the network drive (Mounted SMB File Share) using the Storage Gateway's network address inside Windows.
- **Result**: Successfully mapped the network drive. Creating, modifying, or deleting data in this Windows folder automatically synchronized in real-time to the Amazon S3 Bucket securely.
- **Tools/Tech**: AWS Storage Gateway, Amazon S3, Windows Server (EC2), SMB Protocol, Guest Access, Security Group, AWS CloudWatch.

### 3. Attending AWS Vietnam Community Day and Extracting Insights
- **Description**: 
  - **GenAIOps Session**: Listened to architectural approaches for building a "Second AI Brain" (Store → Retrieve → Respond → Learn) using AWS infrastructure (S3, Vector DB, Bedrock). Analyzed common mistakes like stuffing unrelated documents that dilute the Large Language Model's (LLM) context.
  - **AI Assistants and Multi-Agent Architecture Session**: Explored the Amazon Quick Suite integrated with Agentic AI to automate repetitive corporate tasks. Studied the design of Multi-Agent architectures mimicking specialized business departments collaborating and cross-critiquing in complex scenarios (e.g., banking credit scoring).
- **Result**: Enhanced context management engineering skills, studied defensive technical layers (strict JSON formatting, majority voting mechanisms), and grasped FinOps strategies to control cloud costs before an infrastructure virally scales.
- **Tools/Tech**: Amazon Bedrock, Vector Databases, Amazon Quick Suite, Multi-Agent Architecture, Cost Optimization Strategies.

##  Knowledge Acquired

###  Technical Skills
- **AWS Services**: AWS Storage Gateway (File Gateway), Amazon S3, Amazon EBS Volume, EBS Snapshot, Amazon Bedrock, Amazon CloudWatch.
- **System Administration & AI**: Windows Server management skills, command-line network drive mounting, SMB protocol troubleshooting, and port configuration (opening port 445 for SMB). Mastered intelligent storage retrieval via Vector DBs on cloud structures.

###  Concepts & Theory
- **New Concepts**: Hybrid cloud storage models allowing infinite local scaling onto the Cloud without disrupting legacy apps; Enterprise AI brains and Multi-Agent Architectures.
- **Best Practices**: Strictly monitor Gateway boot times and implement minimalist Security Group configurations. Focus on minor modifications that yield high practical value (saving tokens) instead of prematurely disrupting the whole system design.

##  Challenges & Solutions
- **Vấn đề**: Encountered an "Access Denied" authentication error when attempting to mount the SMB share on Windows Server; additionally, advanced concepts on AI, LLM, and Vector DBs at the event were outside the basic curriculum scope.
- **Root Cause**: Confused the Storage Gateway's Public IP with its Private IP while the Security Group had not opened port 445 for traffic from the Windows EC2. The Storage Gateway service takes a significant amount of time to boot up, which can initially be mistaken for a deployment failure.
- **Solution**: Reviewed the guide, updated the Storage Gateway's Inbound Security Group rules to open port 445 from the Windows Server's CIDR block, and configured Guest Access properly. For the tech event, actively noted core keywords, took slides photos, and engaged directly with speakers during the Q&A sessions.

##  Reflection & Insights
- Integrating legacy infrastructure into the Cloud requires a profound understanding of both environments. Furthermore, technology evolves rapidly; an internship is not just about executing predefined labs but continuously updating yourself with market trends. Under extreme enterprise timeline pressures, technology gaps can be patched quickly with AI, but team chemistry remains the true key to success.

##  Next Week's Plan
- Return to the main training track, focusing on advanced infrastructure tracks: Study Docker, containers, understand basic AWS CI/CD pipelines, and configure Auto Scaling Groups with Elastic Load Balancers (Week 7).

##  Self Assessment
- Productivity: 9/10
- Learning: 9.5/10
- Collaboration: 8/10