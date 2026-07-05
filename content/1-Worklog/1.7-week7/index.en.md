+++
title = "Week 7 Worklog "
date = 2026-05-25
weight = 7
chapter = false
pre = " <b> 1.7. </b> "
+++

##  Basic Information
- **Full Name**: Truong Le Duy Tan
- **Student ID**: 2280602878
- **Class**: 22DTHH1
- **Major**: Information Technology
- **Internship Company**: AWS Cloud Training
- **Internship Position**: AWS Cloud Intern
- **Week Start Date**: May 25, 2026
- **Internship Week**: Week 7/12

##  Weekly Objectives
- Accelerate the learning path, completing up to video number 210 of the recommended AWS training playlist.
- Master High Availability (HA) and Fault Tolerance architectures with Application Load Balancers (ALB) and Auto Scaling Groups (ASG).
- Gain hands-on practice containerizing applications with Docker and explore container orchestration (ECS, Fargate).
- Research the principles of building automated CI/CD integration and deployment pipelines on AWS.

##  Tasks Performed

### 1. Deploying High Availability (HA) and Fault Tolerance Architectures
- **Description**: Explored advanced theories regarding high availability and fault tolerance on cloud platforms. Practiced configuring Application Load Balancers (ALB) and Network Load Balancers (NLB) to distribute incoming traffic into target server pools (Target Groups). Established an Auto Scaling Group (ASG) coupled with Launch Templates to automatically scale EC2 server fleets up or down based on actual real-time CPU load metrics.
- **Result**: Successfully built a web tier architecture capable of elastic horizontal scaling and self-healing when virtual machines encounter system anomalies.

### 2. Practical Container Technology (Docker) and AWS Container Services
- **Description**: Studied basic and advanced Docker concepts. Practiced writing Dockerfiles to package a web application into a Docker Image, managing and running Docker Containers in local testing environments. Explored AWS enterprise-scale container orchestration platforms including Amazon ECS (Elastic Container Service) and AWS Fargate (the serverless compute engine for containers).
- **Result**: Mastered application containerization life cycles, optimizing Docker image layers to build leaner operational payloads.

### 3. Researching Automated CI/CD Pipelines
- **Description**: Studied the principles of building pipelines to automate continuous software delivery. Explored specialized AWS developer toolsuites: AWS CodeCommit (source control management), AWS CodeBuild (automated app compilation and container packaging), AWS CodeDeploy (automated source deployment), and AWS CodePipeline (orchestrating the end-to-end automation stream).
- **Result**: Understood the CI/CD lifecycle from the moment a developer commits code up to the automated build and rollout onto container services without manual intervention.
- **Tools/Tech**: Application Load Balancer, Auto Scaling Group, Docker, Amazon ECS, AWS Fargate, AWS CodePipeline, AWS CodeBuild, Amazon CloudWatch.

##  Knowledge Acquired

###  Technical Skills
- **AWS Services**: ALB, NLB, Auto Scaling Group, Launch Template, Amazon ECS, AWS Fargate, AWS CI/CD Developer Tools.
- **DevOps**: Managing application lifecycles via Containers, writing optimized multi-stage Dockerfiles, structuring automated CI/CD pipelines, and centralizing tracking logs via CloudWatch.

###  Concepts & Theory
- **New Concepts**: Serverless compute models for containers (AWS Fargate) which eliminate OS patch management, and Self-healing Infrastructure architectures.
- **Best Practices**: Decouple infrastructure layers cleanly; position logic processing business applications behind Load Balancers within safe Private Subnets, and implement CI/CD to control system performance and minimize waste.

##  Challenges & Solutions
- **Issue**: Writing Dockerfiles initially resulted in oversized image footprints or missing runtime environment packages; the CI/CD pipeline failed during the deployment stage, preventing traffic routing to new containers.
- **Root Cause**: Poor early management of Docker Image build layers. Furthermore, routing dependencies between the Load Balancer, Target Group, and ASG are highly intricate; misconfiguring subnet mappings blocked traffic from reaching EC2/Containers inside the Private Subnet.
- **Solution**: Read official AWS Whitepapers, re-watched practical lab sections in the video playlist, and tracked centralized error logs using CloudWatch to add an Inbound rule allowing traffic from the ALB into the Containers, successfully resolving the labs.

##  Reflection & Insights
- Automation and Containerization remove an incredible amount of manual workload from infrastructure engineers. Integrating Docker and CI/CD smoothly increases software delivery speed drastically, eliminating human errors and assuring parity between development environments.

##  Next Week's Plan
- Effort to complete the final sections of the AWS training playlist.
- Explore cloud database solutions (Amazon RDS and Amazon DynamoDB).
- Study advanced Serverless engineering with AWS Lambda and Amazon API Gateway.
- Consolidate knowledge to draft an architectural layout for a 3-Tier Architecture Mini Project.

##  Self Assessment
- Productivity: 9/10
- Learning: 9/10
- Collaboration: 7/10