+++
title = "Week 4 Worklog "
date = 2026-05-04
weight = 4
chapter = false
pre = " <b> 1.4. </b> "
+++

##  Basic Information
- **Full Name**: Truong Le Duy Tan
- **Student ID**: 2280602878
- **Class**: 22DTHH1
- **Major**: Information Technology
- **Internship Company**: AWS Cloud Training
- **Internship Position**: AWS Cloud Intern
- **Week Start Date**: May 04, 2026
- **Internship Week**: Week 4/12

##  Weekly Objectives
- Complete up to video 65 of the AWS training playlist.
- Establish a basic Amazon VPC network infrastructure.
- Divide Public and Private Subnets and configure Internet routing.

##  Tasks Performed

### 1. Setting Up Amazon VPC and Subnet Infrastructure
- **Description**: Initialized a Custom VPC isolated virtual network with a CIDR block of `10.0.0.0/16`. Split the network into a Public Subnet (`10.0.1.0/24`) and a Private Subnet (`10.0.2.0/24`) to separate public-facing resources from internal secure workloads.
- **Result**: Successfully established the virtual subnet system on the Cloud infrastructure. Enabled auto-assign public IP settings for resources launched inside the Public Subnet.
- **Tools/Tech**: AWS VPC Console.

### 2. Configuring Internet Gateways and NAT Gateways
- **Description**: Created an Internet Gateway (IGW) and attached it to the VPC to provide an Internet path for the Public Subnet. Allocated an Elastic IP address, then set up a NAT Gateway service deployed within the Public Subnet. Modified the Private Subnet's Route Table to direct `0.0.0.0/0` traffic through the NAT Gateway.
- **Result**: EC2 virtual machines in the Private Subnet could securely connect out to the Internet to download package updates, while external entities could not initiate direct connections inward.
- **Tools/Tech**: Internet Gateway, NAT Gateway, Elastic IP, Route Table.

##  Knowledge Acquired

###  Technical Skills
- **AWS Services**: Amazon VPC, Route Table, Internet Gateway, NAT Gateway, Elastic IP.
- **Networking**: Subnetting skills and controlling network traffic routing.

###  Concepts & Theory
- **New Concepts**: The working principles and role of a two-tier network architecture (Public and Private) in building a secure cloud infrastructure.
- **Best Practices**: A NAT Gateway must always be placed in a Public Subnet to communicate outwards, and Elastic IPs must be released when a NAT Gateway is deleted to avoid costs outside the Free Tier.

##  Challenges & Solutions
- **Issue**: The EC2 instance placed in the Private Subnet completely lost outbound Internet connectivity and could not download package extensions.
- **Root Cause**: Accidentally mapped the NAT Gateway deployment inside the Private Subnet, which isolated the NAT Gateway itself.
- **Solution**: Deleted the misconfigured NAT Gateway, re-created it while specifying its placement inside the Public Subnet, and updated the Private Subnet's Route Table accordingly.

##  Reflection & Insights
- Networking knowledge serves as the absolute foundation. When working on the Cloud, a single wrong parameter in a Route Table can paralyze the whole system or compromise the security of the network.

##  Next Week's Plan
- Move to Week 5 to explore advanced storage solutions on AWS and Hybrid storage connectivity methods (AWS Storage Gateway).

##  Self Assessment
- Productivity: 9/10
- Learning: 9/10
- Collaboration: 6/10