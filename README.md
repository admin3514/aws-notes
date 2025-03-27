# aws-notes

**What is Cloud Computing?** <br>
The Cloud (or Cloud Computing) refers to the delivery of computing services over the internet. Instead of owning and managing physical hardware, companies and individuals can access on-demand computing resources from cloud providers like AWS, Google Cloud, and Microsoft Azure.

**Types of Cloud Computing :** <br>
*1. Public Cloud* – Services provided over the internet (e.g., AWS, Azure, Google Cloud). <br>
*2. Private Cloud* – Dedicated cloud infrastructure for a single organization. <br>
*3. Hybrid Cloud* – A mix of public and private cloud services. <br>

**Cloud Computing Service Models :** <br>
*IaaS (Infrastructure as a Service)* - Provides virtual servers, storage, and networking <br>
                                       ex. AWS EC2, Google Compute Engine <br>
                                       
*PaaS (Platform as a Service)* -	Provides a managed environment for app development	<br>
                                  ex. AWS Elastic Beanstalk, Google App Engine  <br>

*SaaS (Software as a Service)* - Delivers software applications over the internet	<br>
                                ex. Gmail, Dropbox, Office 365 <br>

*Region:* In AWS (Amazon Web Services), a Region is a geographical area where AWS has multiple data centers (called Availability Zones) that host cloud resources and services. <br>
ex. ap-south-1, us-east-1, us-east-2 <br>

*Availability Zone (AZ):* An Availability Zone (AZ) is a physically separate data center within an AWS Region. Each region has at least two AZs, and they are designed to be isolated from failures in other AZs. <br>

<hr>

**AWS IAM (Identity and Access Management) :** <br>
AWS IAM (Identity and Access Management) is a service that helps you securely control access to AWS resources. It allows you to manage who can access AWS (authentication) and what actions they can perform (authorization). <br>

✅ IAM is a global service, meaning that it is not tied to a specific AWS region. <br>

**IAM Resources & Components :** <br>
*1. IAM Users* - Represents individual people or applications that need access to AWS. <br>
Each user has credentials (passwords, access keys). <br>

*2. IAM Groups* - A collection of IAM users that share the same permissions. <br>
Easier to manage multiple users at once.

*3. IAM Roles* - Temporary access credentials assigned to AWS services or users. <br>
Used by EC2 instances, Lambda functions, or cross-account access.

*4. IAM Policies* - JSON documents that define permissions. <br>
**Two types:** <br>
1. *AWS Managed Policies* – Predefined by AWS (e.g., AmazonS3FullAccess). <br>
    i. JSON policy <br>
    ii. Visual policy <br>
2. *Customer Managed Policies* – Custom policies created by users. <br>

<hr>

**Amazon S3 (Simple Storage Service) :** <br>
**What is Amazon S3?** <br>
Amazon S3 (Simple Storage Service) is an object storage service that allows you to store and retrieve any amount of data from anywhere on the internet. It is highly scalable, durable, and secure, making it ideal for backups, static website hosting, data lakes, and more. <br>

✅ Amazon S3 is a region specific service. <br>

*Key Features of S3* <br>
✅ Unlimited Storage – Store petabytes of data. <br>
✅ Durability & Availability – 99.999999999% (11 9’s) durability. <br>
✅ Security & Access Control – IAM, encryption, and access policies. <br>
✅ Lifecycle Management – Automate moving data to cheaper storage classes. <br>
✅ Versioning – Maintain multiple versions of an object. <br>
✅ Static Website Hosting – Serve web content without a web server. <br>

*S3 Resources & Components* <br>
*1. S3 Buckets* - A bucket is a container for storing objects (files). <br>
   Each bucket has a unique name across globally. <br>

*2. S3 Objects* - Objects are the actual data files stored inside a bucket. <br>
   Each object consists of: <br>
   Data (the actual file) <br>
   Metadata (key-value pairs) <br>
   Key (the unique name of the object in the bucket) <br>

*3. S3 Storage Classes* - AWS S3 provides different storage classes to optimize cost vs. access frequency. <br>
   i. S3 Standard -	Frequently accessed data <br>
   ii. S3 Intelligent-Tiering -	Automatically moves objects to cheaper storage tiers based on usage <br>
   iii. S3 Standard-IA (Infrequent Access) - Data that is accessed less often but needs fast retrieval <br>
   iv. S3 One Zone-IA	- Lower-cost infrequent access storage in a single AZ <br>
   v. S3 Glacier - Long-term cold storage (retrieval takes minutes to hours) <br>
   vi. S3 Glacier Deep Archive - Cheapest option for archival storage (retrieval takes hours) <br>

   <hr>

**Amazon EC2 (Elastic Compute Cloud) :** <br>
**What is Amazon EC2?** <br>
Amazon EC2 (Elastic Compute Cloud) is a service that provides scalable virtual servers  in the cloud we called it as Instances. It allows users to launch, manage, and scale computing capacity without the need for physical hardware. <br>

*Key Features of EC2 :* <br>
✅ Elasticity – Scale instances up or down as needed. <br>
✅ Variety of Instance Types – Choose instances optimized for compute, memory, or storage. <br>
✅ Pay-as-You-Go Pricing – Only pay for what you use. <br>
✅ Security & Control – Secure instances using IAM roles, security groups, and VPCs. <br>
✅ Multiple OS Choices – Run Linux, Windows, or custom AMIs. <br>

*EC2 Resources & Components* <br>
*1. EC2 Instances (Virtual Servers)* - An EC2 instance is a virtual machine (VM) running on AWS. <br>
    Instances have CPU, RAM, storage, and networking. <br>
    We can choose an AMI (Amazon Machine Image) to preinstall software. <br>

*2. Instance Types* : <br>
    i. General Purpose - General purpose instances provide a balance of compute, memory and networking resources, and can be used for a variety of diverse workloads.	<br>
                         ex. t3.micro, m5.large <br>

   ii. Compute Optimized - High performance processors. <br>
                           ex. (AI, gaming)	c5.2xlarge, c6g.large <br>

   iii. Memory Optimized - Memory optimized instances are designed to deliver fast performance. <br>
                           ex. r5.large, x1e.32xlarge <br>

   iv. Storage Optimized - Storage optimized instances are designed for workloads that require high, sequential read and write access to very large data sets on local storage <br>
                           ex. i3.large, d2.xlarge <br>

   v. Accelerated Computing - Accelerated computing instances use hardware accelerators, or co-processors, to perform functions.<br>

   vi. HPC Optimized - High performance computing (HPC) instances are purpose built to offer the best price performance for running HPC workloads at scale on AWS. <br>


   **Launch Templates :** <br>
   **What is a Launch Template?** <br>
   A Launch Template in AWS is a pre-configured blueprint for launching EC2 instances. It helps automate and standardize EC2 instance launches by defining key parameters like: <br>
   ✅ AMI (Amazon Machine Image) <br>
   ✅ Instance type (e.g., t3.micro, m5.large) <br>
   ✅ Security groups & IAM roles <br>
   ✅ Storage (EBS volumes) <br>
   ✅ User data scripts (to run commands on startup) <br>
  Launch Templates simplify EC2 deployment, improve consistency, and support Auto Scaling & Spot Instances. <br>


  **EC2 Purchasing Models :** <br>
  1️⃣ On-Demand Instances (Pay-as-You-Go) - 💰 Pricing: Charged per second/minute with no long-term commitment. <br>
      📌 Best For: <br>
      ✅ Short-term, unpredictable workloads <br>
      ✅ Applications that require high flexibility <br>
      ✅ Development and testing environments <br>
     🔹 Example: Running a web app for a few hours without long-term commitment. <br>

  2️⃣ Reserved Instances (RIs) – Up to 75% Discount - 💰 Pricing: Prepaid commitment for 1 or 3 years → Huge savings! <br>
      📌 Best For: <br>
      ✅ Long-running, predictable workloads <br>
      ✅ Applications requiring steady usage <br>
      ✅ Big cost savings over time <br>
     🔹 Example: Running a database server 24/7 for a year → Reserved Instances save money! <br>

  3️⃣ Savings Plans (Flexible Cost Savings) - 💰 Pricing: Similar to RIs but more flexible → Save up to 72%
     📌 Best For: <br>
     ✅ Long-term workloads but with some flexibility <br>
     ✅ Workloads that might change over time <br>
     ✅ Works across all AWS regions <br>
     🔹 Example: If your app may change instance types, Savings Plans are better than RIs. <br>

  4️⃣ Spot Instances (Up to 90% Discount!) - 💰 Pricing: Lowest cost option, but instances can be interrupted.
     📌 Best For: <br>
     ✅ Batch processing, machine learning, big data, CI/CD <br>
     ✅ Applications that can handle interruptions <br>
     ✅ Highly cost-sensitive workloads <br>
     🔹 Example: Running AI training models at a fraction of the cost. <br>

  5️⃣ Dedicated Hosts (Physical Server for You Only) - 💰 Pricing: Expensive but required for compliance & licensing.
     📌 Best For: <br>
     ✅ Running legacy apps that require a physical server <br>
     ✅ BYOL (Bring Your Own License) for software like Windows Server <br>
     ✅ Meeting compliance needs (e.g., HIPAA, GDPR) <br>
     🔹 Example: A company running Windows Server with its own licenses. <br>

   6️⃣ Dedicated Instances (Private EC2 Instances) - 💰 Pricing: More costly than On-Demand, but cheaper than Dedicated Hosts.
      📌 Best For: <br>
      ✅ Workloads that need single-tenant EC2 instances <br>
      ✅ Not as strict as Dedicated Hosts but still private <br>
      🔹 Example: A finance company requiring high security but not full physical control. <br>


  








