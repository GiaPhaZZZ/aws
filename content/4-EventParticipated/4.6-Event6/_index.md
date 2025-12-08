---
title: "AWS Edge Services Wokrshop"
date: 2025-11-19
weight: 6
chapter: false
pre: " <b> 4.6. </b> "
---

# Summary Report: “AWS Edge Services Workshop - Amazon CloudFront as Your Foundation”

### Event Objectives

* Understand how Amazon CloudFront enhances security, performance, and cost efficiency
* Learn best practices for edge caching, content delivery, and origin protection
* Explore CloudFront capabilities for static, dynamic, and large-scale content
* Gain practical insights into implementing edge logic and failover strategies

### Speakers

* **Hung Nguyen Gia** – Head of Solutions Architect, Edge Technical Field Community, Amazon Web Services Viet Nam

### Key Highlights

#### Customer Challenges and Financial Solutions

* **Unpredictable CDN Costs:** Usage-based billing can lead to high bills during traffic spikes or attacks
* **Solution:** AWS Fixed-Price CDN + Security plans, providing predictable monthly costs and reducing financial risk
  * Bundles: CloudFront, WAF, Shield AMR, Route 53, CloudWatch Logging, S3 storage credits
  * Fixed monthly pricing regardless of usage

#### CloudFront Capabilities

**Security and Protection**

* **HTTPS/TLS Support:**
  * Reduce key size for higher performance and lower latency
  * Use TLS library (s2n) to validate destinations
  * TLS 1.3, ECDSA certificates, and post-quantum-ready options

* **Mutual TLS (2-way):** Support for client certificate authentication, upcoming CloudFront setup

* **Origin Cloaking:**
  * VPC Origin: hides origin from internet, using private ALB
  * Origin Access Control (OAC): signed requests for S3, Lambda, MediaPackage, no API Gateway needed
  * Custom Origins: restrict CloudFront IPs, add custom headers with pre-defined secrets

* **Access Control:** Geographic restrictions, Signed URLs with time-frame, URL path, and client IP validation

**Cost Optimization**
* Automatic object compression (up to 10 GB, skip already compressed files)
* Free AWS data transfer from origins to CloudFront
* Offload origin workload: reduces CPU and load balancer costs

**Reliability and Resiliency**
* Caching with TTL and stale content delivery
* Built-in failover to healthy secondary origins
* Graceful failure: deliver cached content or custom error pages

**Performance Enhancements**
* Multi-layer caching: Regional Edge Caches + Origin Shield
* Request collapsing to reduce duplicate requests
* Persistent connections to origin to avoid extra TCP handshakes
* Edge logic execution with CloudFront Functions or Lambda@Edge

#### Use Cases and Best Practices

* **Use Cases:**
  * Static web resources
  * Whole website delivery (global performance, security, high availability)
  * API acceleration (connection reuse, reduced latency)
  * Media streaming and large file downloads (resumable, edge caching)
* **Best Practices:**

  1. End-to-end visibility: monitor user experience and request paths
  2. Maximum caching: normalize cache keys, select appropriate TTL, cache errors to prevent brute-force attacks
  3. Block unwanted requests: detect malicious patterns, implement rate limiting
  4. Offload business logic: move lightweight processing to edge, e.g., CloudFront Functions
  5. Automatic failover: configure Route 53 health checks or CloudFront origin groups

### Key Takeaways
* CloudFront is a **comprehensive foundation** for edge security, performance, and cost efficiency
* Edge caching and logic reduce origin load while improving response times
* Security features (TLS, mutual TLS, origin cloaking, signed URLs) protect content at the edge
* Following best practices ensures **high availability, optimized caching, and resilience**

### Applying to Work
* Enable compression and multi-layer caching for both static and dynamic content
* Implement Signed URLs and OAC for sensitive content
* Move lightweight business logic to CloudFront Functions for faster response
* Monitor edge metrics and logs to maintain visibility and detect unwanted traffic
* Configure failover to maintain high availability

### Event Experience

Attending the **AWS Edge Services Workshop** was highly valuable, offering a deep dive into **CloudFront’s security, performance, and operational capabilities**. Key experiences included:

#### Learning from an expert speaker
* Hung Nguyen Gia shared **practical insights and real-world examples** on edge optimization
* Gained an understanding of CloudFront’s **full spectrum of features** for global content delivery

#### Hands-on technical exposure
* Learned **origin cloaking** and **origin access control** configurations
* Explored compression, caching strategies, and persistent connections
* Understood how **edge logic** reduces latency and improves scalability

#### Leveraging best practices
* End-to-end visibility and error handling strategies
* Advanced caching configurations for maximum efficiency
* Techniques to block malicious requests and offload processing to the edge

#### Some event photos

<p align="center">
  <img src="/images/4-EventParticipated/event_6/photo1.jpg" alt="Picture 1" />
  <br/>
  <strong style="font-size: 18px;">Figure 1</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_6/photo2.jpg" alt="Picture 2" />
  <br/>
  <strong style="font-size: 18px;">Figure 2</strong>
</p>

<p align="center">
  <img src="/images/4-EventParticipated/event_6/photo3.jpg" alt="Picture 3" />
  <br/>
  <strong style="font-size: 18px;">Figure 3</strong>
</p>

> Overall, the workshop reinforced the importance of **security, performance, and reliability at the edge**, and provided actionable strategies for implementing CloudFront in enterprise environments.

