---
title: "Reinventing DevSecOps with AWS Generative AI"
date: 2025-10-16
weight: 3
chapter: false
pre: " <b> 4.3. </b> "
---

# Summary Report: “Reinventing DevSecOps with AWS Generative AI”

### Event Objectives

* To share how DevSecOps has evolved with the automation of system operations through AI.
* To provide detailed knowledge about the DevSecOps process.
* To answer how DevSecOps engineers are applying AI to reshape workflows and drive transformation.

### Speakers

* **Lê Thanh Đức** – Cloud Delivery Manager, CMC Global
* **Dư Quốc Thành** – Technical Leader, CMC Global
* **Văn Hoàng Kha** – Cloud Engineer, AWS Community Builder

### Key Highlights

#### Overview of DevSecOps

* The DevSecOps framework is more than a traditional DevOps cycle.
* It integrates security into multiple parts and throughout the entire lifecycle.

#### DevSecOps Lifecycle

* The DevSecOps lifecycle includes seven main components, starting from planning to operations. The detailed steps are outlined below:

Below are all stages in the **DEVSECOPS LIFECYCLE**, formatted as requested:

* **1. PLAN:**

  * Identify security requirements and risks from the start.
  * Align goals between Dev, Sec, and Ops teams.
  * Create a security roadmap linked to project objectives.

* **2. CODE:**

  * Apply secure coding standards and conduct code reviews.
  * Use SAST tools to detect early vulnerabilities.
  * Build a “security-first” mindset among developers.

* **3. BUILD:**

  * Automate security checks within CI/CD pipelines.
  * Perform dependency and binary scans.
  * Ensure consistent and secure builds.

* **4. TEST:**

  * Conduct vulnerability scans, DAST, and penetration tests.
  * Validate that applications meet security requirements.
  * Update tests to address newly discovered vulnerabilities.

* **5. DEPLOY:**

  * Verify configurations and IaC before deployment.
  * Automate runtime configuration monitoring.
  * Minimize manual errors and ensure secure deployment.

* **6. OPERATE:**

  * Automate patching and continuous security updates.
  * Implement incident response and performance monitoring.
  * Maintain stability and safety after release.

* **7. MONITOR:**

  * Continuously monitor activities and potential threats.
  * Use real-time analytics and alerting tools.
  * Detect risks early and respond quickly.

#### DevSecOps Toolchain Overview

* **Pre-commit & Code Quality:**

  * SonarQube, Codacy, Semgrep (SAST), Gitleaks – detect code issues and secrets before commit.

* **Dependency & SBOM Scanning:**

  * Syft, Grype, Dependency-Track – manage packages and detect library vulnerabilities.

* **IaC & Policy-as-Code:**

  * Checkov, TFsec – scan Terraform/Kubernetes configurations.
  * OPA Gatekeeper, Kyverno – automatically enforce policies and compliance.

* **SAST / DAST & Security Tests:**

  * Trivy, Checkmarx, Semgrep, Codacy – identify code and runtime vulnerabilities.

* **CI/CD Integration:**

  * Jenkins, GitHub Actions, GitLab CI, ArgoCD – automate build, test, and secure deployment.

* **Monitoring & Logging:**

  * Prometheus, Grafana, Loki, Promtail – real-time monitoring and observability.

* **Alerting & Governance:**

  * Slack webhooks, Email alerts, AI anomaly detection – provide alerts and quick responses.
  * Centralized risk reports – aggregate and analyze security risks.

#### Benefits of GenAI in DevSecOps

* **1. Automation & Acceleration of DevSecOps Processes**

  * Automated code review and security scanning.
  * Pipeline generation.
  * IaC generation.

* **2. Enhanced Proactive Security**

  * Natural language-based threat modeling.
  * Policy-as-code generation.
  * Dynamic scanning augmentation.

* **3. Optimized Observability & Incident Response**

  * Incident summaries and root cause analysis.
  * ChatOps integration.
  * Anomaly detection.

### Key Takeaways

#### Strategy for Integrating AI into Workflow

* AI improves incident detection and vulnerability analysis.
* It accelerates response and remediation, saving time and effort.
* Helps reduce manual workload while maintaining high-quality outcomes.
* Enables continuous learning and improvement within the DevSecOps cycle.

#### Applying Amazon Q in Coding

* Use **Amazon Q** to assist in secure coding.
* Evaluate carefully whether to approve AI-suggested actions.
* Utilize it for documentation search and recommendation across multiple sources.

### Event Experience

Attending the **“Reinventing DevSecOps with AWS Generative AI”** workshop provided me with practical insights into how AI is reshaping the entire DevSecOps workflow — from planning, coding, and testing to operations and monitoring. Below are the key experiences:

#### Hands-on Technical Experience

* Gained in-depth understanding of the **DevSecOps Lifecycle**, from **Plan – Code – Build – Test – Deploy – Operate – Monitor**, and how to integrate security across all stages of software development.
* Observed real-world examples of **CI/CD pipelines with integrated automated security checks**, emphasizing the importance of early vulnerability detection.

#### Modern Tool Application

* Learned how to use **Amazon Q** in the DevSecOps workflow — from secure code generation to IaC creation and automated issue fixing.
* Explored **DevSecOps toolchain components** such as SonarQube, Checkov, Trivy, Prometheus, and Grafana, understanding how they work together for end-to-end security.
* Recognized the critical role of **AI in safe code creation, testing, and deployment**, especially through **policy-as-code** and **natural language-based threat modeling**.

#### Networking and Discussion

* Had opportunities to **discuss directly with DevSecOps experts from AWS and CMC Global**, gaining valuable insights from real-world implementation.
* Engaged with the developer community to explore how **AI can be integrated into DevSecOps pipelines**, inspiring new ideas for my own projects.

#### Lessons Learned

* DevSecOps is not just about CI/CD automation but about **embedding security as a fundamental part** of the entire software lifecycle.
* Implementing **AI and Generative AI** enhances vulnerability detection, test automation, and incident response efficiency.
* **Amazon Q** is a promising tool that helps developers and security engineers **optimize their workflow**, minimize manual effort, and boost productivity.
* Effective DevSecOps requires **tight collaboration between people, processes, and technology**, with AI serving as an **intelligent assistant** for better decision-making and faster actions.

#### Some event photos

<p align="center">
  <img src="/images/4-EventParticipated/event_3/photo1.png" alt="Picture 1" />
  <br/>
  <strong style="font-size: 18px;">Figure 1</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_3/photo2.png" alt="Picture 2" />
  <br/>
  <strong style="font-size: 18px;">Figure 2</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_3/photo3.png" alt="Picture 3" />
  <br/>
  <strong style="font-size: 18px;">Figure 3</strong>
</p>

> Overall, the event not only deepened my understanding of DevSecOps but also reshaped my perspective on how AI can enhance security integration, streamline development workflows, and strengthen collaboration across engineering teams.
