---
title: "Blog 2"
date: 2025-09-19
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

# Implement network connectivity patterns for Oracle Database@AWS

by Sameer Malik, Anvesh Koganti, and Shubham Singh | 11 SEP 2025 | AWS Cloud WAN, AWS Transit Gateway, Expert (400), Networking & Content Delivery, Oracle Database@AWS, Technical How-to


Oracle Database@AWS (ODB@AWS) is an offering you can use to access Oracle Exadata infrastructure managed by Oracle Cloud Infrastructure (OCI) within Amazon Web Services (AWS) data centers. You can use ODB@AWS to migrate your Oracle Exadata workloads to AWS while maintaining the same performance and features as your on-premises Oracle Exadata deployments. You benefit from reduced application latency by establishing low-latency connectivity between Oracle Exadata and your applications running on AWS. Additionally, you can integrate Oracle Database@AWS with other AWS services to improve the availability and scalability of your Oracle database applications.

In this post, we show how to implement different IP routing-based network connectivity patterns for connectivity between your ODB network and other resources deployed in AWS and your on-premises network. The patterns work well when you have non-overlapping IP address spaces and need traditional Layer 3 connectivity.

Connectivity patterns covered in this post include:
  * One-to-one connectivity between the application virtual private cloud (VPC) and ODB network

  * Scalable single-Region connectivity between multi-VPC or on-premises infrastructure and ODB network using AWS Transit Gateway

  * Scalable global connectivity between multi-VPC or on-premises infrastructure and ODB network using AWS Cloud WAN

Before proceeding further, we recommend that you be familiar with AWS services such as Amazon Virtual Private Cloud (Amazon VPC), AWS Direct Connect, Amazon Route 53 Resolver endpoints, Transit Gateway, and AWS Cloud WAN.

## Understanding the basics

The following is a high-level overview of the core components in ODB@AWS essential for network connectivity. For more information, see the Oracle Database@AWS User Guide.

  **ODB network** – An ODB network is a private, isolated network that hosts Oracle infrastructure within an AWS Availability Zone. Unlike a standard VPC, ODB network lacks internet connectivity and supports only ODB@AWS resources.

  **ODB peering** – ODB peering establishes private network connectivity between your ODB network and an Amazon VPC, enabling applications to communicate with Oracle databases as if they were on the same network. ODB peering bridges AWS and Oracle environments and offers a support for routing capability that enables traffic using specific AWS networking services connected to your peered VPC to reach the ODB network. The following figure illustrates this peering relationship between a peered VPC and ODB network.

![](/images/3-TranslatedBlogs/blog2/fig1.jpeg)

  **Access control with peered CIDRs** – Peered CIDRs is a configuration that acts as a network-level access control list (ACL). You can specify and manage IP CIDR ranges that are allowed to reach the Oracle database resources in your ODB network. Setting up the peered CIDRs triggers automation on the Oracle OCI side to configure route rules and security rules linked to the Oracle Virtual Cloud Network (Amazon VPC equivalent) where the resources reside to allow traffic from/to specific CIDRs on specific protocols and ports. You can include specific subnet CIDRs instead of entire VPC ranges, providing granular security control. Refer to the considerations section later in this post for more details on peered CIDRs and OCI automation specifics.

  **Peered VPC usage patterns** – The peered VPC can serve multiple purposes. It can function as a direct application VPC, providing the simplest network path for dedicated Oracle workloads. Alternatively, it can act as a transit VPC that uses transitive routing to make the ODB network accessible from multiple VPCs and on-premises networks through Transit Gateway or AWS Cloud WAN based hub-and-spoke architectures. A peered VPC can also simultaneously fulfill both roles, serving as both an application VPC hosting workloads and a transit VPC connecting other networks to the ODB network.

## DNS configuration

ODB@AWS automatically manages DNS within the ODB network, creating Fully Qualified Domain Names (FQDNs) for virtual machine (VM) clusters. By default, these use the *.oraclevcn.com domain pattern (where you can specify a prefix that gets appended to oraclevcn.com, such as myhost.oraclevcn.com). Alternatively, you can configure custom domain names using your own complete domain (for example, myhost.myodb.com). Regardless of the domain configuration chosen, DNS queries from your VPCs must be forwarded to the ODB network’s DNS infrastructure to resolve these domain names.

The DNS architecture consists of the following components:
  * **Route 53 Resolver outbound endpoint** – Forwards DNS queries from your VPC to the ODB network’s DNS infrastructure. After the ODB network is created, it provides a DNS listener IP address that the outbound endpoint must have network connectivity to.

  * **Forwarding rules** – Direct queries for Oracle domains (for example, client.xxxxx.oraclevcn.com) to the ODB network’s DNS listener IP using the outbound endpoint. The rule matches both the exact domain and its subdomains (for example, if the rule is for example.com, it matches both example.com and sub.example.com). You can share these rules across AWS accounts using AWS Resource Access Manager (AWS RAM) and associate them with VPCs that need to resolve Oracle domain names. For more details on domain matching, see How Resolver determines whether the domain name in a query matches any rules.

In the following figure, the outbound endpoint is deployed within the application VPC for simplified configuration and direct connectivity to the peered ODB network. Alternative deployment options and centralized DNS management strategies are discussed later in this post. For detailed DNS configuration steps, see Configuring DNS for Oracle Database@AWS.

![](/images/3-TranslatedBlogs/blog2/fig2.jpeg)

## Network connectivity patterns

In this section, we discuss three common network connectivity patterns for ODB@AWS, ranging from simple direct connectivity to scalable multi-Region architectures. Each pattern addresses different business needs and scaling requirements. For simplicity, the diagrams don’t show account-level resource placement. Account placement considerations for each pattern are detailed in the next section.

### Connectivity pattern 1: Direct peering between the application VPC and the ODB network

This pattern uses the peered VPC as an application VPC, hosting database applications directly within the VPC peered to the ODB network. This approach provides the simplest network path between applications and databases.

This pattern works well when Oracle databases primarily serve applications within a single VPC. As shown in the following figure, the ODB network is bound to a single Availability Zone (defined when the ODB network is created), whereas the application VPC and its resources can span multiple Availability Zones. For multi-VPC or hybrid architectures, consider the ODB transit VPC patterns in subsequent sections.

![](/images/3-TranslatedBlogs/blog2/fig3.jpeg)


The workflow consists of the following components:
  * A. Amazon EC2 instances in the application VPC resolve the database hostname and initiate database connections using the IP.
  * B. VPC route tables direct traffic toward the ODB network through the ODB peering connection.
  * C. Because the VPC CIDR is included in the peered CIDRs list, configurations on the Oracle OCI side allow this traffic.

### Connectivity pattern 2: Single-Region scalable connectivity using Transit Gateway

In this pattern, we explore network connectivity to the ODB network at scale in the single AWS Region. At the time of writing, ODB network supports direct peering with only one VPC; one-to-many peering connection between an ODB network and multiple VPCs is not supported. A transit gateway is a centralized networking component that serves as an interconnection point for multiple VPCs and on-premises networks. At the time of writing, a built-in transit gateway attachment for ODB network is not supported. However, you can peer your ODB network to a single transit VPC and then connect that transit VPC to the transit gateway, as shown in the following figure.

![](/images/3-TranslatedBlogs/blog2/fig4.jpeg)

In this pattern, the peered VPC is acting only as the ODB transit VPC (as described earlier in this post). However, as highlighted in the peered VPC usage pattern, the peered VPC can simultaneously host workloads if desired.

The transit gateway attachment to the transit VPC must be created in a single Availability Zone only, specifically the same Availability Zone where the ODB network is created. To highlight this, in the preceding figure, we have shown the workloads spanning across multiple Availability Zones in the application VPC, but the transit VPC only has a transit gateway attachment in Availability Zone 1. For detailed configuration steps, see Configuring Amazon VPC Transit Gateways for Oracle Database@AWS.

Workflow components:
  * A. EC2 instances in the application VPC resolve the database hostname to obtain the IP address and then initiate database connections using this IP. VPC subnet route table lookup happens, and the packet is forwarded to the transit gateway using the transit gateway attachment.

  * B. The associated Transit Gateway route table has a static route for ODB network CIDR with the destination as the transit VPC attachment.
  Traffic from the transit VPC uses the ODB peering route in the VPC subnet route table and traffic is forwarded to the ODB network.

  * C. Because the VPC CIDR is included in the peered CIDRs list, configurations on the Oracle OCI side are present to allow this traffic. Response traffic follows the reverse path back to the originating EC2 instances.

### Connectivity pattern 3: Multi-Region scalable connectivity using AWS Cloud WAN

In this pattern, we explore network connectivity to ODB from multiple Regions and on-premises networks. AWS Cloud WAN simplifies multi-Region connectivity through dynamic route propagation. You can use this to connect your data centers, branch offices, and VPCs across multiple Regions into one unified network, all controlled through a single global network policy. AWS Cloud WAN supports built-in segmentation, which means you can easily manage network isolation across your Regions and on-premises locations. Using network segments, you can divide your global network into separate isolated networks. For more information, see the AWS Cloud WAN User Guide.

At the time of writing, a built-in attachment for ODB network is not supported with AWS Cloud WAN. By peering your ODB network to a transit VPC and then attaching that transit VPC to the AWS Cloud WAN core network, you can use AWS Cloud WAN to route network traffic between your ODB network and multiple other VPCs across Regions and on-premises locations. In this pattern, the peered VPC acts as the transit VPC based on the peered VPC usage pattern. You need to make sure the transit VPC attachment to the AWS Cloud WAN core network is created in one Availability Zone only—the same one as the ODB network.

For simplicity, we have shown all application VPCs that need access to the ODB network to be associated with the ODB application VPC segment while the Direct Connect gateway is associated with a hybrid segment and segment sharing is enabled between both segments, as shown in the following figure. For detailed configuration steps, see Configuring AWS Cloud WAN for Oracle Database@AWS.

![](/images/3-TranslatedBlogs/blog2/fig5.jpeg)

Workflow components:
  * A. EC2 instances in the application VPC resolve the database hostname to obtain the IP address and then initiate database connections using this IP. VPC subnet route table lookup happens, and the packet is forwarded to the AWS Cloud WAN core network using the AWS Cloud WAN VPC attachment.

  * B. Application VPC 1 is associated with the ODB application VPC segment, which has the associated attachment CIDRs dynamically propagated. Because built-in attachment to ODB network is currently not supported on AWS Cloud WAN, we create a static route pointing to the transit VPC attachment.

  * C. Traffic from the transit VPC uses the ODB peering route in the subnet route table and traffic is forwarded to the ODB network.

  * D. As highlighted in the preceding section, necessary CIDRs for application VPCs and the on-premises network are added in the peered CIDR list on the ODB network. Response traffic follows the reverse path back to originating EC2 instances.

## Considerations

When implementing ODB@AWS network connectivity, keep in mind these considerations:

* When creating an ODB network, consider IP address space requirements, including non-overlapping CIDRs with connected networks and reserved IP ranges that can’t be used. These CIDR ranges can’t be modified after ODB network creation.

* Setting up ODB peering doesn’t automatically add routes for ODB network CIDRs (client CIDR or backup CIDR) to the peered VPC route tables. You must manually run the aws ec2 create-route command to add these routes to the VPC route tables as needed. See configuring VPC route tables for ODB peering for specific AWS Command Line Interface (AWS CLI) commands.

* When you set up ODB peering with a VPC, the primary VPC CIDR gets automatically added to the peered CIDR list. Secondary CIDRs of the peered VPC must be added manually. At the time of writing, you can’t edit the automatically added primary CIDR to limit it to specific subnet CIDRs of this VPC. Include all required source CIDR ranges that need to communicate with the databases in the peered CIDR list, which serves as an ACL.

* When an entry is added to the peered CIDR list, OCI side automation takes place to facilitate connectivity. A new static route is added in the route rules (VPC route table equivalent) associated to the Virtual Cloud Network (Amazon VPC equivalent) to facilitate traffic to the CIDR range added as an entry. Additionally, entries are added in the security rules (AWS security groups and network ACL equivalent) associated to the Virtual Cloud Network to allow ICMP traffic (for MTU path discovery and ping), TCP traffic on port 22 (for SSH), and other TCP ports needed for database traffic.

* Route 53 Resolver outbound endpoints can be deployed either in the peered VPC or in a separate VPC your networking team manages. If you already have outbound endpoints set up to facilitate hybrid DNS resolution, you can use them as well. In either case, make sure the VPC CIDR containing the endpoint is added to ODB’s peered CIDRs list and network connectivity exists between the endpoint VPC and the peered VPC (through Transit Gateway or AWS Cloud WAN).

* Route 53 profiles can be used to share resolver rules across AWS accounts instead of directly sharing individual rules using AWS RAM.
As of this writing, the Transit Gateway attachment and AWS Cloud WAN attachment for transit VPC need to be created in one Availability Zone only—the same one as the ODB network for connectivity.

* Multi-Region connectivity can also be achieved using Transit Gateway inter-Region peering instead of Cloud WAN. This approach requires static routing configuration between peered transit gateways.
A transit VPC can’t be simultaneously attached to both Transit Gateway and AWS Cloud WAN, or even multiple transit gateways or Cloud WAN core networks. You must choose a single transit service for connectivity.

* For a pattern 1 account placement, the ODB network is provisioned in the buyer account and can be shared using AWS RAM with multiple accounts. However, as of this writing, only one peering connection can be established to the ODB network. This means you can share the ODB network using AWS RAM to another account and create the ODB peering connection with the application VPC in that shared account, providing flexibility for cross-account application deployments. See Resource sharing in Oracle Database@AWS for more details.

* For patterns 2 and 3 account placements, when implementing Transit Gateway and AWS Cloud WAN connectivity, both the transit VPC and the ODB network must reside in the same AWS account—specifically the buyer account where the ODB network is provisioned. However, Transit Gateway and AWS Cloud WAN can reside in a different account (such as a central networking account) and be shared with the buyer account using AWS RAM to establish the necessary connectivity.

## Conclusion

In this post, we demonstrated the network integration capabilities of Oracle Database@AWS, which offers a robust and versatile solution for enterprises to seamlessly extend the power of Oracle Exadata databases in the AWS Cloud.

Oracle Database@AWS provides organizations with flexible options to integrate their Oracle database deployments with their broader AWS infrastructure and hybrid environments. By having the choice to peer an ODB network directly with a single VPC, use Transit Gateway to connect multiple VPCs, or use the centralized connectivity of AWS Cloud WAN, you can choose the network configuration that best suits your specific requirements.

For organizations needing IP-agnostic connectivity, overlapping IP address space support, or specialized integrations like zero-ETL and Amazon Simple Storage Service (Amazon S3) access, refer to Oracle Database@AWS network connectivity Using Amazon VPC Lattice.

### About the authors

**Sameer Malik**

Sameer has been working on relational Databases for over 23 years now and is currently working as a Principal Database Solution Architect at AWS focused on RDS and Aurora. He has helped several customers with the migration and modernization of their Database workloads to AWS.

**Anvesh Koganti**

Anvesh is a Solutions Architect at AWS specializing in Networking. He focuses on helping customers build networking architectures for highly scalable and resilient AWS environments. Outside of work, Anvesh is passionate about consumer technology and enjoys listening to podcasts on tech and business. When disconnecting from the digital world, Anvesh spends time outdoors hiking and biking.

**Shubham Singh**

Shubham is a Senior Network Specialist Solutions Architect at AWS. He helps customers design innovative, resilient, and cost-effective solutions using AWS services. He is passionate about technology and enjoys building solutions in the Networking and Security. He holds a MS in Telecommunication Systems Management from Northeastern University, specializing in Computer Networking.