---
title: "AWS Cloud Mastery Series #3"
date: 2025-11-29
weight: 7
chapter: false
pre: " <b> 4.7. </b> "
---

# Summary Report: “Security - AWS Well-Architected Security Pillar”

### Event Objectives

* Introduce the core principles of the **AWS Well-Architected Security Pillar**
* Strengthen foundational knowledge in identity, detection, and incident response
* Guide students to build secure architectures using AWS best practices
* Promote community growth through learning, collaboration, and content creation
* Build a pathway for students to earn **AWS badges** and grow their cloud careers

### Speakers / Core Team

* Le Vu Xuan An - FCJ Memeber
* Tran Duc Anh - FCJ Memeber
* Tran Doan Cong Ly - FCJ Memeber
* Danh Hoang Hieu Nghi - FCJ Memeber


### Key Highlights

#### Overview of AWS Cloud Club — Security Track

* A community to **grow cloud and security skills**, develop leadership, and collaborate with peers
* A structured **badging journey** recognizes progress and contributions
* The **core team** forms the foundation of the club, supporting new members and leading initiatives
* Participants earn badges by attending workshops and can redeem them for rewards
* Club members contribute by creating **technical content** and social media posts
* A major highlight of the year is the **Student Community Day** event
* Benefits to members include:
  * Build Skills
  * Build Community
  * Build Opportunities

#### IAM (Identity & Access Management)

* Identity controls form the foundation of every AWS security strategy
* Assign permissions based on **least privilege**, granting only what each user/service truly needs
* Remove long-term access keys; prefer **IAM roles** instead
* Enable **MFA** for all users to strengthen authentication
* Use **AWS Single Sign-On (IAM Identity Center)** for consistent access management
* Avoid relying on free credits for experimentation; use AWS Organizations to manage accounts properly
* **Service Control Policies (SCPs)** enforce guardrails across multiple accounts (enterprise-level feature)
* Use **Permission Boundaries** to prevent privilege escalation
* Avoid creating IAM users with long-term credentials
* Support strong authentication methods: **TOTP** and **FIDO2** hardware keys
* **IAM Access Analyzer** helps identify unintended public or cross-account access


#### Detection & Continuous Monitoring

* Implement **multi-layer visibility** to understand what is happening across the environment
* Use **Amazon EventBridge** to automate alerts when unusual activity occurs
* Adopt **Detection-as-Code**: manage detection rules and automation through code for consistency
* Ensure that logs from AWS CloudTrail, CloudWatch, and VPC Flow Logs are centralized for analysis


#### Amazon GuardDuty

* Addresses key business concerns:
  * Not knowing whether the system is under attack
  * Slow response time
  * Compliance risks
  * Unexpected cost spikes due to malicious usage

* GuardDuty uses **machine learning** and threat intelligence to identify suspicious behavior
* Fully integrates with **EventBridge** to enable automated workflows
* Advanced features include **S3 Protection**, **RDS Protection**, and attack sequence mapping
* Provides **real-time findings**, automated recommendations, and multi-account event routing

#### AWS Security Hub

* Managing multiple AWS services makes security findings difficult to track
* **Security Hub** aggregates alerts across services into a single, consistent format
* Helps maintain compliance and implement best practices using AWS and CIS standards
* Provides **step-by-step remediation guidance** for findings
* Supports governance across **multiple accounts** and **multiple regions**


#### Network Layer Security

* A defense-in-depth approach starts with secure VPC design
* Use **Security Groups** and **Network ACLs** to restrict network traffic
* Monitor network behavior using **VPC Flow Logs**
* Design isolated, least-privileged networks and avoid unnecessary public exposure
* Integrate AWS Network Firewall or PrivateLink where necessary



#### Incident Response

* Prepare clear **incident response playbooks** for containment, investigation, remediation, and recovery
* Automate critical IR steps using EventBridge, Lambda, and Security Hub actions
* Practice tabletop exercises to validate readiness
* Document escalation paths, communications, and post-incident reviews


### Key Takeaways

#### Security Mindset

* **Security is continuous** — identity, detection, and incident response must evolve as systems grow
* Least privilege and strong authentication form the core of AWS identity security
* Multi-account and multi-region governance ensures consistent protection

#### Technical Practices

* Use GuardDuty and Security Hub together for end-to-end detection and visibility
* Automate alerts and workflows with EventBridge
* Implement Detection-as-Code for version-controlled and repeatable monitoring
* Apply layered network protection and limit unnecessary access

#### Growth & Community

* Members develop both technical and leadership skills
* The club encourages collaboration, teaching, and content creation
* Badging supports motivation and helps showcase cloud expertise

### Event Experience

Attending the **Master 3 — Security** workshop provided a comprehensive introduction to modern AWS security practices. Key experiences included:

#### Learning from Practitioners

* The core team offered hands-on insights into identity management, detection tools, and cloud governance
* Real-world examples helped solidify best practices in IAM and organizational security

#### Hands-on Understanding

* Discussions about permission boundaries, SCPs, and IAM roles clarified common student difficulties
* Demonstrations of GuardDuty and Security Hub helped visualize how AWS detects and responds to threats

#### Automation and Visibility

* EventBridge examples showed how alerts and workflows can be automated
* Seeing detection and remediation in action highlighted the importance of visibility in security architecture

#### Community Building

* Sharing knowledge and participating in discussions strengthened connections among members
* The workshop reinforced the mission of the Cloud Club: **learn, grow, and build opportunities together**

#### Lessons Learned

* Identity is the first line of defense
* Continuous monitoring is essential
* Automation reduces risk and response time
* Governance across accounts and regions is critical for real-world environments

#### Some event photos

<p align="center">
  <img src="/images/4-EventParticipated/event_7/photo1.jpg" alt="Picture 1" />
  <br/>
  <strong style="font-size: 18px;">Figure 1</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_7/photo2.jpg" alt="Picture 2" />
  <br/>
  <strong style="font-size: 18px;">Figure 2</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_7/photo3.jpg" alt="Picture 3" />
  <br/>
  <strong style="font-size: 18px;">Figure 3</strong>
</p>


> Overall, the event strengthened my understanding of cloud security and deepened my appreciation for AWS best practices. It also highlighted the value of community-driven learning and collaboration.
