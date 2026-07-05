+++
title = "Week 11 Worklog "
date = 2026-06-22
weight = 11
chapter = false
pre = " <b> 1.11. </b> "
+++

##  Basic Information
- **Full Name**: Truong Le Duy Tan
- **Student ID**: 2280602878
- **Class**: 22DTHH1
- **Major**: Information Technology
- **Internship Company**: AWS Cloud Training
- **Internship Position**: AWS Cloud Intern
- **Week Start Date**: June 22, 2026
- **Internship Week**: Week 11/12

##  Weekly Objectives
- Transition formally from the sandbox laboratory phase to the final graduation project building phase.
- Gather business and functional requirements to draft a comprehensive Project Proposal.
- Architect a multi-tier, secure, and highly available cloud solution blueprint on AWS.
- Present and successfully defend the technical proposal before the corporate review panel.

##  Tasks Performed

### 1. Requirements Engineering and Technology Selection
- **Description**: Analyzed the problem statement for the graduation project. Evaluated workload patterns, user traffic expectations, and regulatory security requirements to select the optimal AWS technology stack.
- **Result**: Defined an advanced tech stack separating workloads into a presentation layer (S3 + CloudFront CDN), a robust application layer (Amazon ECS Fargate), and a secure storage tier (Amazon RDS).

### 2. System Architecture Design and Blueprinting
- **Description**: Designed a high-availability infrastructure layout across multiple Availability Zones (Multi-AZ). Mapped network topology including custom VPC boundaries, public/private subnets, application load balancers, auto-scaling configurations, and strict security group interdependencies.
- **Result**: Completed a comprehensive 3-Tier System Architecture Diagram using enterprise-ready AWS notation tools, detailing all data flow pipelines and communication protocols.

### 3. Compiling and Defending the Official Project Proposal
- **Description**: Documented the engineering approach, budget estimates using the AWS Pricing Calculator, deployment roadmap, and risk mitigation strategies into a formal Project Proposal. Presented the architectural slides before the technical mentors and the corporate review board.
- **Result**: Successfully defended the Capstone Project Proposal, receiving valuable architectural feedback and authorization to proceed with full implementation.
- **Tools/Tech**: AWS Architecture Icons, AWS Pricing Calculator, Draw.io, Presentation Software.

##  Knowledge Acquired

###  Technical Skills
- **Cloud Architecture**: Multi-AZ infrastructure blueprinting, infrastructure cost forecasting, and requirements parsing for scalable systems.
- **Governance**: Mapping technical capabilities directly to compliance, business SLAs, and high-availability operational metrics.

###  Concepts & Theory
- **New Concepts**: Advanced structural patterns of enterprise architectures, standard software development lifecycle (SDLC) transitions inside cloud operations, and pitching cloud architectures to stakeholders.

##  Challenges & Solutions
- **Issue**: Initial infrastructure cost projections exceeded the simulated enterprise budget constraints allocated for the capstone phase.
- **Root Cause**: Over-provisioned resources by choosing high-tier production databases (Amazon RDS multi-AZ write clusters) and oversized container specifications unnecessarily for early-stage deployment.
- **Solution**: Refined the infrastructure blueprint by implementing strict cost-saving patterns, replacing bloated idle resources with dynamic AWS Fargate task boundaries, and utilizing Amazon RDS Single-AZ with automated snapshot strategies for development tiers.

##  Reflection & Insights
- Moving from isolated weekly labs to scoping a unified corporate project requires a broader perspective. An architecture cannot just be functional—it must balance security compliance, performance efficiency, and financial prudence.

##  Next Week's Plan
- Participate in advanced interactive technology workshops and seminars.
- Finalize the internship report, synthesize end-term documentation, and complete the final audit.

##  Self Assessment
- Productivity: 9.5/10
- Learning: 9/10
- Collaboration: 8.5/10