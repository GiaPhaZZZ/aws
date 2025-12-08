---
title: "AWS Cloud Mastery Series #2"
date: 2025-11-17
weight: 5
chapter: false
pre: " <b> 4.5. </b> "
---
# Summary Report: “DevOps on AWS”

### Event Objectives

* Introduce DevOps principles and the cultural mindset behind modern software delivery
* Demonstrate how to build automated CI/CD pipelines on AWS
* Provide guidance on implementing Infrastructure as Code (IaC)
* Compare AWS container services for modern application deployment
* Present best practices for observability and monitoring

### Speakers

* **Bao Huynh** – AWS Community Builder
* **Thinh Nguyen** – AWS Community Builder
* **Vi Tran** – AWS Community Builder

### Key Highlights

#### Understanding the DevOps Mindset

* Collaboration between development and operations → Faster delivery
* Automation reduces manual work and increases consistency
* Continuous feedback loops → More stable, reliable systems

#### CI/CD Pipeline on AWS

A fully automated pipeline built across four stages:
* **Source Control**: CodeCommit for managing and versioning code
* **Build & Test**: CodeBuild to compile, test, and package applications
* **Deployment**: CodeDeploy implementing rolling, canary, and blue/green methods
* **Orchestration**: CodePipeline connecting all stages into a continuous workflow

Live demos showed how code commits automatically triggered builds, tests, deployments, and rollbacks.

#### Infrastructure as Code (IaC)

A shift from manual setups to automated, version-controlled environments.

* **AWS CloudFormation**

  * Declarative YAML/JSON templates
  * Resources, parameters, conditions, outputs
  * Drift detection to maintain state consistency

* **AWS CDK (Cloud Development Kit)**

  * Define infrastructure in TypeScript, Python, Java, etc.
  * L1/L2/L3 constructs for reusable patterns
  * CLI to synthesize, diff, and deploy stacks

Examples demonstrated identical architectures built using IaC instead of “ClickOps.”

#### Containers on AWS

Overview of Docker basics and AWS container compute choices:

* **Amazon ECR**: Secure container registry with vulnerability scanning
* **Amazon ECS**: AWS-native orchestration with EC2 or Fargate launch types
* **Amazon EKS**: Managed Kubernetes for standards-based workloads
* **AWS App Runner**: Simplified container deployment with minimal operations

Comparisons highlighted when to choose App Runner vs ECS vs EKS based on team experience and workload patterns.

#### Observability and Monitoring

Building visibility for modern systems:
* **Amazon CloudWatch**
  * Metrics, logs, alarms, dashboards
* **AWS X-Ray**
  * Distributed tracing to identify bottlenecks and slow microservices

Emphasis on actionable alerts, meaningful dashboards, and proactive monitoring practices.

### Key Takeaways

#### DevOps Practices

* Automation → speed + reliability
* Cultural alignment between dev and ops
* Use DORA metrics to guide improvement
* Integrate feedback at every development stage

#### Infrastructure as Code

* Minimize manual configuration in production
* CloudFormation for AWS-native declarative workflows
* CDK for flexible, programmatic infrastructure definitions
* Treat infrastructure like software: test, version, automate

#### Application Delivery

* CI/CD pipelines reduce human error
* Choose deployment strategies based on risk (rolling, canary, blue/green)
* Integrate automated testing in every step

#### Container Strategy

* Containers offer portability, consistency, modular architecture
* ECS → simple operational model
* EKS → Kubernetes flexibility
* App Runner → low-ops deployment
* ECR as the foundation for image management

#### Observability

* Combine metrics, logs, traces for a 360° view
* CloudWatch dashboards + X-Ray service maps for troubleshooting
* Build proactive alerts, not reactive firefighting

### Applying to Work

* **Automate CI/CD** using CodePipeline, CodeBuild, and CodeDeploy to streamline releases
* **Adopt IaC** with CloudFormation or CDK to replace manual setups and ensure consistency
* **Containerize services** and select ECS, EKS, or App Runner based on workload needs
* **Improve observability** using CloudWatch metrics, logs, alarms, and custom dashboards
* **Enable distributed tracing** with AWS X-Ray for microservice troubleshooting
* **Use DORA metrics** to measure delivery performance and guide DevOps improvements

### Event Experience

Attending the **“Cloud Mastery Series #2 – DevOps on AWS”** workshop provided both strategic direction and practical knowledge for implementing DevOps at scale.

#### Learning from highly skilled speakers

* The speakers offered clear explanations of CI/CD, containers, IaC, and monitoring
* Real-world case studies illustrated how DevOps practices work in production environments

#### Hands-on technical exposure

* Observed CI/CD pipelines running from commit → build → deployment
* Understood how CloudFormation and CDK help enforce repeatable infrastructure
* Clarified trade-offs between ECS, EKS, and App Runner for container orchestration

#### Leveraging modern tools

* IaC tools enforce consistency and reduce configuration drift
* CloudWatch and X-Ray provide the foundation for operational excellence

#### Networking and discussions

* Opportunities to connect with experts and peers
* Discussions reinforced the importance of culture, automation, and measurable improvement

#### Lessons learned

* Automation is key to scaling safely
* Observability is required for reliability
* Choosing the right compute/container service leads to reduced operational burden

#### Some event photos

<p align="center">
  <img src="/images/4-EventParticipated/event_5/photo1.jpg" alt="Picture 1" />
  <br/>
  <strong style="font-size: 18px;">Figure 1</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_5/photo2.jpg" alt="Picture 2" />
  <br/>
  <strong style="font-size: 18px;">Figure 2</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_5/photo3.jpg" alt="Picture 3" />
  <br/>
  <strong style="font-size: 18px;">Figure 3</strong>
</p>

> Overall, the workshop delivered a comprehensive and practical understanding of DevOps principles, CI/CD pipelines, IaC, container orchestration, and monitoring — all essential components of modern cloud-native development.

