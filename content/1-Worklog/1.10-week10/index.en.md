+++
title = "Week 10 Worklog "
date = 2026-06-15
weight = 10
chapter = false
pre = " <b> 1.10. </b> "
+++

##  Basic Information
- **Full Name**: Truong Le Duy Tan
- **Student ID**: 2280602878
- **Class**: 22DTHH1
- **Major**: Information Technology
- **Internship Company**: AWS Cloud Training
- **Internship Position**: AWS Cloud Intern
- **Week Start Date**: June 15, 2026
- **Internship Week**: Week 10/12

##  Weekly Objectives
- Complete 100% of the remaining video lectures in the AWS training playlist series.
- Perform a comprehensive financial audit in the AWS Billing & Cost Management Dashboard for the Free Tier lifecycle.
- Conduct a complete resource clean-up across all active regions to terminate lab components and suppress trailing billing records.
- Synthesize all engineering blocks mastered over the 10-week Lab phase and transition documentation for the final graduation project building phase.

##  Tasks Performed

### 1. Finalizing Training Path and Researching AWS Well-Architected Framework
- **Description**: Watched the final videos in the training playlist, summarizing core knowledge blocks. Conducted theoretical study on the AWS Well-Architected Framework to evaluate how enterprise cloud infrastructures match industry standards.
- **Result**: Achieved 100% completion of the theoretical playlist track. Mastered the core pillars of the Well-Architected Framework: Security, Performance Efficiency, Reliability, Cost Optimization, and Operational Excellence.

### 2. Cloud Financial Governance and Billing Audits
- **Description**: Evaluated the AWS Billing & Cost Management Dashboard to check historical consumption patterns and metrics compiled across the lab term. Verified services approaching or surpassing Free Tier thresholds to implement remediation steps.
- **Result**: Gained command over cost control toolsets including AWS Cost Explorer and AWS Budgets. Configured an automated budget alarm routing alerting thresholds directly to personal email.

### 3. Global Infrastructure Clean-up (De-provisioning Resources)
- **Description**: Audited all geographic AWS Regions utilized throughout the internship to wipe away dangling assets and mitigate trailing bills. Executed the following teardown items:
  - Terminated all running and stopped EC2 compute instances.
  - Deleted standalone block-storage EBS Volumes and obsolete EBS Snapshots.
  - Removed Auto Scaling Groups, Launch Templates, and Application Load Balancers (ALBs).
  - Emptied all objects and deleted temporary Amazon S3 Buckets.
  - Deleted active NAT Gateways and released static Elastic IP addresses back into the AWS global public pool.
- **Result**: Cleaned up the AWS account safely, dropping the forecasted cost trajectory back down to $0.00 USD and eliminating any risk of surprise fees.

##  Knowledge Acquired

###  Technical Skills
- **AWS Services**: Advanced cloud financial governance tools (AWS Billing, Cost Explorer, AWS Budgets).
- **Resource Management**: Global resource lifecycle tracking, cross-regional auditing, and decommissioning complex interconnected infrastructures.

###  Concepts & Theory
- **New Concepts**: Deep comprehension of the AWS Well-Architected pillars to apply to high-scale cloud designs.
- **Best Practices**: Wipe away sandboxed lab resources immediately post-evaluation; use AWS Budgets as a hard firewall guarding personal and enterprise cloud spending.

##  Challenges & Solutions
- **Issue**: Certain Amazon S3 Buckets failed to drop despite the dashboard indicating zero visible contents, and specific Elastic IP addresses refused to release.
- **Root Cause**: The target S3 Buckets had Object Versioning active, keeping old hidden object versions and delete markers stored in background layers. For the Elastic IPs, they were still bound to a deleting NAT Gateway, causing the system to lock release permissions.
- **Solution**: Toggled the "Show versions" option inside the S3 browser bucket view, permanently wiped out historical versions, and proceeded to delete the bucket shell. Monitored the NAT Gateway until its status read completely `Deleted`, then released the mapped Elastic IPs successfully.

##  Reflection & Insights
- Concluding 10 weeks of continuous lecture tracks and practical labs has provided a solid foundation of real-world cloud engineering skills on the AWS platform. Getting my hands dirty with manual deployments and troubleshooting failures has significantly built my confidence for tackling advanced enterprise problems. This phase serves as an exceptional springboard for the upcoming project delivery.

##  Next Week's Plan
- Formally enter Phase 2 (Giai đoạn 2): Align with the internship cohort to pick a graduation topic, engineer the Project Proposal, and start active development on the real-world AWS solution.

##  Self Assessment
- Productivity: 9/10
- Learning: 9/10
- Collaboration: 7.5/10