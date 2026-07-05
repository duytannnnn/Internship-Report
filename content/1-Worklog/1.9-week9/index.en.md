+++
title = "Week 9 Worklog "
weight = 9
chapter = false
pre = " <b> 1.9. </b> "
+++

##  Basic Information
- **Full Name**: Truong Le Duy Tan
- **Student ID**: 2280602878
- **Class**: 22DTHH1
- **Major**: Information Technology
- **Internship Company**: AWS Cloud Training
- **Internship Position**: AWS Cloud Intern
- **Week Start Date**: June 08, 2026
- **Internship Week**: Week 9/12

##  Weekly Objectives
- Advance through the curriculum roadmap, completing up to video lecture 257 of the AWS playlist.
- Deep dive into advanced identity security services, access control governance, and serverless authentication layers.
- Attend the internal AWS technical trivia and architectural competition for trainees to reinforce system assessment capabilities.

##  Tasks Performed

### 1. Lab: Advanced Security Controls and Identity Governance
- **Description**: Explored advanced authorization mechanisms using IAM Policies, IAM Roles, and Trust Policies. Applied rigid evaluation conditions (Conditions) inside JSON policies, such as IP Address white-listing, Time-based Access windows, and enforced Multi-Factor Authentication (MFA) requirements.
- **Result**: Achieved proficiency in structuring IAM users, groups, and cross-account assumption parameters following the Principle of Least Privilege.

### 2. Deploying Serverless Authentication with Amazon Cognito
- **Description**: Researched and configured Amazon Cognito User Pools to manage and validate consumer identities. Set up Amazon API Gateway to create a Serverless REST API backed by AWS Lambda processing. Configured Amazon Cognito as an Authorizer layer directly guarding API Gateway entry paths.
- **Result**: Successfully protected the Serverless API network tier. The edge API gateway automatically drops and returns authorization errors if an incoming HTTP request lacks a verifiable cryptographic ID Token from Cognito.

### 3. Operational Auditing with AWS CloudTrail and CloudWatch
- **Description**: Activated AWS CloudTrail to log and capture all API invocations and resource mutations across the cloud tenancy. Configured Amazon CloudWatch metrics and streams to parse logs, watch indicators, and detect unauthorized API actions or authorization rejections.
- **Result**: Established holistic auditing capability, strengthening threat detection and access debugging skills.

### 4. Attending the Internal AWS Technical Competition
- **Description**: Participated as an evaluator and attendee in the internal AWS knowledge and architectural design tournament organized for trainees (comprising 08 teams battling across brackets). Analyzed situational problem statements covering IAM, EC2, S3, VPC, Lambda, API Gateway, CloudWatch, and CloudFormation.
- **Result**: Absorbed architectural trade-offs from judges, evaluated multi-service operational graphs, and noted knowledge gaps to fix before the end of the internship.
- **Tools/Tech**: Amazon Cognito, Amazon API Gateway, AWS Lambda, IAM (Policies, Roles, Trust Policies), AWS CloudTrail, Amazon CloudWatch.

##  Knowledge Acquired

###  Technical Skills
- **AWS Services**: Amazon Cognito, Amazon API Gateway, AWS Lambda, IAM (Policy, Role, Trust Policy), AWS CloudTrail, Amazon CloudWatch.
- **Security & Operations**: Analyzing security logs, structuring cross-service AssumeRole handshakes, setting up API Authorizers, and troubleshooting access denied faults.

###  Concepts & Theory
- **New Concepts**: Identity Federation models, secure cross-service role assumption mechanics, and managing stateless authentication barriers within Serverless computing context.
- **Best Practices**: Maintain global log aggregation via CloudTrail for administrative tasks; append granular Condition Policies to shrink attack vectors.

##  Challenges & Solutions
- **Issue**: Configuring the Trust Policy JSON block for an IAM Role threw persistent `Invalid Principal` system rejections; integrating Cognito identity layers into API Gateway encountered verification failures.
- **Root Cause**: Typed an incorrect string structure for the Amazon Resource Name (ARN) identifying the authorized entity permitted to assume the role. Missed mapping properties for the App Client or skipped internal authorization permissions between the API Gateway and Cognito.
- **Solution**: Evaluated details inside CloudWatch logs, parsed the official AWS documentation, rectified ARN strings, and verified App Client client secrets to finalize the deployment.

##  Reflection & Insights
- Governance and real-time monitoring are the compass of any cloud blueprint. Merging practical lab tasks with the technical competition highlighted that optimal architectures do not just compile logic features—they protect them across multiple perimeters from network subnets down to consumer identities.

##  Next Week's Plan
- Watch the remaining video lectures to finish the AWS training playlist.
- Audit the AWS Billing and Cost Management center and execute a full clean-up of temporary lab infrastructure to protect against surprise trailing costs.
- Synthesize Giai đoạn 1 (Phase 1) assets and prepare handover checklists to transition into the final graduation project building phase.

##  Self Assessment
- Productivity: 9/10
- Learning: 9.5/10
- Collaboration: 8/10