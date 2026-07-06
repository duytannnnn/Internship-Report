+++
title = "Event : AWS Vietnam Community Day"
date = 2026-05-23
weight = 1
chapter = false
pre = " <b> 4.1. </b> "
+++



### Overview
* **Event Name:** AWS Vietnam Community Day (Technology Proceedings & Enterprise Operations)
* **Participation Date:** May 23, 2026
* **Technical Focus:** GenAIOps, Enterprise AI, Cloud Infrastructure, CloudFront Optimization

---

### I. Summary of Presentation Sessions

#### 1. GenAIOps: Building a Second AI Brain from a DevOps Perspective
* **Speaker:** Mr. Tinh (Platform Engineer at GoTymeX)
* **Problem:** Low-quality AI is often caused by a lack of target system context and long-term memory, coupled with mistakes like dynamic dynamic dynamic generic prompting or feeding irrelevant documentation.
* **Solution:** Building a "Second AI Brain" system model using the *Store → Retrieve → Respond → Learn* lifecycle backed by AWS infrastructure (S3, Vector DB, Bedrock). Context Engineering will become a core capability.

#### 2. User-Friendly AI Assistants with Amazon Quick Suite
* **Speaker:** Hai Anh (G-AsiaPacific Vietnam, AWS Community Builder)
* **Solution:** Leveraging Amazon Quick Suite integrated with Agentic AI to bridge enterprise internal data stores with global knowledge, supporting over 40 data connectors to fully automate workflows.
* **Application:** A PM Assistant that automates Minutes of Meeting (MoM) generation, triggers emails, and schedules meetings.

#### 3. From Edge to Origin: Amazon CloudFront as an Application Foundation
* **Speaker:** Nguyen Tuan Thinh (DevOps Engineer at First Cloud AI Journey)
* **Pricing Model:** Flat-rate pricing removes bandwidth billing spike risks when applications go viral or experience heavy DDoS threats.
* **Optimization & Security:** A massive network footprint of over 700 PoPs achieves an 82% payload compression rate; fully supports mTLS validation and backend shielding (Origin cloaking via VPC Origin/OAC).

#### 4. 36 Hours at LotusHacks – Project UTMorpho
* **Representative:** Team VIB
* **Product:** UTMorpho overcomes traditional AI-driven UI layout regeneration faults via a Smart Diffing engine paired with Amazon Bedrock, allowing real-time WYSIWYG Canvas edits without destroying existing UI integrity or wasting expensive tokens.

#### 5. Non-Determinism in Fixed LLM Configurations
* **Speaker:** Dao Duc (Solution Architect - Cloud Kinetics)
* **Reality:** Setting `Temperature = 0` can still lead to a structural drift of up to 15% in output schemas due to parallel non-associative floating-point operations on GPUs and inference batching mechanics.
* **Solution:** Fix `Temperature = 0.1`, increment the repeat penalty, enforce Majority Voting patterns, and restrict structures utilizing JSON Mode or Regex grammars.

#### 6. Multi-Agent Startup Credit Scoring Architecture
* **Speaker:** Vy Lâm (Senior Business Systems Analyst at VPBank)
* **Solution:** Orchestrating a "Virtual Credit Committee" composed of specialized operational agents (Financial, Market, Risk, Compliance) engaging in peer review under a Manager Agent workflow coordinator.
* **Impact:** Reduced processing turnarounds from 2-3 weeks to 2-4 hours (a 95% acceleration), cut decision computing costs by 95%, and maintained enterprise security via Bedrock AgentCore inside isolated VPC domains.

---

### II. Personal Experiences and Lessons Learned

* **Trend Shift:** The AI landscape has shifted aggressively from "curiosity testing" to automated runtime operations (GenAIOps) and enterprise-grade readiness, focusing deeply on token optimization patterns and PII token filtering.
* **Infrastructure Intersection:** High-performance AI frameworks must rely on structurally optimized cloud designs (such as CloudFront Flat-rate billing or Bedrock AgentCore boundaries).
* **Human Element:** Under extreme sandbox constraints (like a 36-hour Hackathon), team chemistry, shared trust, and baseline coordination prove far more critical than individual technical skills alone.


### Illustrative image


![Policy](/images/8/23-05-2026.jpg)