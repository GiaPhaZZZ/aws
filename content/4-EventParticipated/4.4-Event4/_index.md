---
title: "AWS Cloud Mastery Series #1"
date: 2025-11-15
weight: 4
chapter: false
pre: " <b> 4.4. </b> "
---

# Summary Report: “AI/ML/GenAI on AWS Workshop”

### Event Objectives

* Provide an overview of AWS’s AI/ML ecosystem
* Introduce Generative AI with Amazon Bedrock
* Explore real-world applications of Prompt Engineering and RAG
* Demonstrate how AI services integrate into cloud-based products
* Present AgentCore for scalable, production-ready AI agents

### Speakers

* **Lam Tuan Kiet** – Senior DevOps Engineer, FPT Software
* **Dang Hoang Hieu Nghi** – AI Engineer, Reonova Cloud
* **Dinh Le Hoang Anh** – Cloud Engineer Trainee, FCJ

### Key Highlights

#### Transformation from Traditional ML to Foundation Models

* **Traditional ML models**

  * Task-specific
  * Require pre-labeled datasets
  * Limited generalization

* **Generative AI (Foundation Models)**

  * Trained on massive *unlabeled* datasets
  * Self-supervised learning
  * Capable of multiple tasks using **prompts**
  * Bedrock supports major FM providers: **OpenAI, DeepSeek, Anthropic Claude, Meta Llama, Amazon Titan**

#### Prompt Engineering Essentials

* **What is a prompt?**
  Instructions that guide a model’s behavior and output

* **Techniques**

  * **Zero-shot prompting**: Minimal instruction → concise but sometimes shallow output
  * **Few-shot prompting**: Provide examples to guide patterns
  * **Chain-of-Thought prompting**: Add reasoning guidance → higher-quality, step-by-step outputs

#### Retrieval-Augmented Generation (RAG)

* Enhances model outputs by adding **relevant, external knowledge**

* Process:

  1. User gives a prompt
  2. System retrieves related documents
  3. Combined context fed into the model
  4. Model generates an informed answer

* **Embeddings**

  * Convert text → vectors representing semantic meaning
  * Enable clustering of similar concepts
  * **Titan Text Embeddings** support **100+ languages**

* RAG improves accuracy, reduces hallucinations, and grounds responses in real data

#### AWS AI Services Overview

A suite of ready-to-use APIs:

* **Rekognition** – Image/video object detection
* **Translate** – Automatic translation & language detection
* **Textract** – Extract text and layout from documents
* **Transcribe** – Speech-to-text, voice identification
* **Polly** – Text-to-speech
* **Comprehend** – NLP insights, sentiment analysis
* **Kendra** – Intelligent enterprise search (e.g., auto-grading student submissions)
* **Lookout Family** – Anomaly detection for metrics, equipment, images
* **Personalize** – Recommendation systems
* **Pipecat** – AI agent pipeline framework

#### Amazon Bedrock AgentCore

A platform to streamline development and deployment of **AI agents**:

* Automates challenging aspects of GenAI production:

  * Scaling
  * Context memory
  * Identity & access control
  * Tool and API integration
  * Workflow orchestration
  * Observability and tracing

* **Key Components**

  * **Runtime** – Executes multi-step agent tasks
  * **Memory** – Stores past interactions
  * **Identity** – Defines access rules
  * **Gateway** – Unified access to tools & services
  * **Code Interpreter** – Safe code execution environment
  * **Browser tool** – Retrieve external web information
  * **Observability** – Logs, metrics, debugging

### Key Takeaways

#### AI & Cloud Development Mindset

* Companies are shifting from simple ML models to **AI-driven cloud-native products**
* Building real projects is crucial — not just assignments for grades
* Foundation models + cloud services = faster product delivery

#### Technical Knowledge

* Understanding how **prompt engineering** affects output quality
* RAG improves factual correctness and supports structured knowledge integration
* Embeddings enable powerful search and clustering capabilities
* AWS AI services cover end-to-end workflow: speech, text, vision, anomaly detection

#### Agent Development

* AgentCore simplifies workflows that used to require multiple services and heavy DevOps
* Essential for building:
  * Chatbots
  * Automation agents
  * Research assistants
  * Knowledge-based applications


### Applying to Work

* Develop **real product prototypes** and include them in the CV
* Use **RAG** to build domain-specific AI systems
* Integrate AWS AI APIs to accelerate feature development
* Leverage **Bedrock Agents** for multi-step workflows
* Explore embeddings for semantic search, recommendation, and classification
* Practice prompt engineering techniques to improve model performance


### Event Experience

Attending the **“AI/ML/GenAI on AWS”** workshop was highly insightful, providing a comprehensive look into modern AI development on the AWS cloud. Key experiences include:

#### Knowledge from Industry Practitioners

* Speakers from FPT, Reonova Cloud, and AWS shared practical insights on how companies build cost-efficient AI solutions on cloud platforms.
* Learned how modern businesses deploy AI across vision, text, speech, and automation workflows.

#### Hands-on Understanding of GenAI Concepts

* Deepened understanding of how **Foundation Models** differ from traditional ML.
* Gained clarity on **prompting styles**, why they matter, and how they change model behavior.
* Saw practical examples of **RAG pipelines** improving accuracy and reliability.

#### Exposure to AWS Tools

* Understood the roles of Rekognition, Textract, Transcribe, Translate, and Comprehend across real use cases.
* Explored how **Bedrock AgentCore** simplifies building scalable GenAI applications with memory, access control, and tool integration.

#### Networking & Practical Advice

* Discussed with engineers how to build **real, production-quality projects** instead of school-level assignments.
* Learned about product-focused mindsets and industry expectations for modern AI skillsets.

#### Lessons Learned

* Combining AI + cloud services accelerates real-world product development.
* Prompt engineering and RAG are essential for enterprise-grade GenAI.
* AgentCore represents the next step in scalable AI application design.

#### Some event photos

<p align="center">
  <img src="/images/4-EventParticipated/event_4/photo1.jpg" alt="Picture 1" />
  <br/>
  <strong style="font-size: 18px;">Figure 1</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_4/photo2.jpg" alt="Picture 2" />
  <br/>
  <strong style="font-size: 18px;">Figure 2</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_4/photo3.jpg" alt="Picture 3" />
  <br/>
  <strong style="font-size: 18px;">Figure 3</strong>
</p>

> Overall, the workshop provided both strategic understanding and hands-on technical knowledge, helping shape a stronger foundation for AI/ML development on AWS.
