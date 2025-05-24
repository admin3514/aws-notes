# aws-notes

**What is Cloud Computing?** <br>
The Cloud (or Cloud Computing) refers to the delivery of computing services over the internet. Instead of owning and managing physical hardware, companies and individuals can access on-demand computing resources from cloud providers like AWS, Google Cloud, and Microsoft Azure.  <br>

**Types of Cloud Computing :** <br>
*1. Public Cloud* – Services provided over the internet (e.g., AWS, Azure, Google Cloud). <br>
*2. Private Cloud* – Dedicated cloud infrastructure for a single organization. <br>
*3. Hybrid Cloud* – A mix of public and private cloud services. <br>

**Cloud Computing Service Models :** <br>
*IaaS (Infrastructure as a Service)* - IaaS is a cloud service that runs services on “pay-for-what-you-use” basis <br>
                                       ex. AWS EC2, Google Compute Engine <br>
                                       Users: IT Administrators  <br>
                                       
*PaaS (Platform as a Service)* -	PaaS runs cloud platforms and runtime environments to develop, test and manage software	<br>
                                  ex. AWS Elastic Beanstalk, Google App Engine  <br>
                                  Users: Software Developers  <br>

*SaaS (Software as a Service)* - :In SaaS, cloud workers host and manage the software application on a pay-as-you-go pricing model 	<br>
                                  ex. Gmail, Dropbox, Office 365 <br>
                                  Users: End Customers  <br>

**What is AWS?** <br>
Answer:AWS stands for Amazon Web Services. AWS is a platform that provides on-demand resources for hosting web services, storage, networking, databases and other resources over the internet with a pay-as-you-go pricing. 

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
Easier to manage multiple users at once.  <br>

*3. IAM Roles* - Roles are for AWS services, Where we can assign permission of some AWS service to other Service. <br>
Example – Giving S3 permission to EC2 to access S3 Bucket Contents.   <br>

*4. IAM Policies* - Policies are for users and groups, Where we can assign permission to user’s and groups.  <br>
Example – Giving permission to user to access the S3 Buckets.   <br>

**Two types:** <br>
1. *AWS Managed Policies* – Predefined by AWS (e.g., AmazonS3FullAccess). <br>
    i. JSON policy <br>
    ii. Visual policy <br>
2. *Customer Managed Policies* – Custom policies created by users. <br>

**Q. How many Policies can be attached to a role.** <br>
Answer: 10 (Soft limit), We can have till 20   <br>

<hr>

**Amazon S3 (Simple Storage Service) :** <br>

**What is Amazon S3?** <br>
Amazon S3 (Simple Storage Service) is an object storage service that allows you to store and retrieve any amount of data from anywhere on the internet. It is highly scalable, durable, and secure, making it ideal for backups, static website hosting, data lakes, and more. <br>

**Q. What is the minimum and maximum size of individual objects that you can store in S3**  <br>
Answer: minimum 0 bytes and the maximum is 5TB.  <br>

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
    1️⃣ S3 Standard -	Frequently accessed data <br>
    2️⃣ S3 Intelligent-Tiering -	Automatically moves objects to cheaper storage tiers based on usage <br>
    3️⃣ S3 Standard-IA (Infrequent Access) - Data that is accessed less often but needs fast retrieval <br>
    4️⃣ S3 One Zone-IA	- Lower-cost infrequent access storage in a single AZ <br>
    5️⃣ S3 Glacier - Long-term cold storage (retrieval takes minutes to hours) <br>
    6️⃣ S3 Glacier Deep Archive - Cheapest option for archival storage (retrieval takes hours) <br>

**Q. Explain Amazon s3 lifecycle rules?**
Answer: Amazon S3 lifecycle configuration rules, you can significantly reduce your storage costs by automatically transitioning data from one storage class to another or even automatically delete data after a period of time.  <br>
• Store backup data initially in Amazon S3 Standard  <br>
• After 30 days, transition to Amazon Standard IA  <br>
• After 90 days, transition to Amazon Glacier  <br>
• After 3 years, delete  <br>

**Q. What is the default storage class in S3?**  <br>
Answer: S3 Standard frequently accessed.  <br>

**Q. What is glacier?**  <br>
Answer: Glacier is the back up or archival tool that you use to back up your data in S3.  <br>

**Q. How can you secure the access to your S3 bucket?**  <br>
Answer: There are two ways that you can control the access to your S3 buckets,  <br>
 • ACL – Access Control List  <br>
 • Bucket polices   <br>

**Q. How can you encrypt data in S3?**  <br>
Answer: You can encrypt the data by using the below methods,  <br>
 • Server Side Encryption – S3 (AES 256 encryption)  <br>
 • Server Side Encryption – KMS (Key management Service)  <br>
 • Server Side Encryption – C (Client Side)  <br>

 **Q. what are the things we need to remember while creating s3 bucket?**  <br>
 Answer:  <br>
  • Amazon S3 and Bucket names are  <br>
  • This means bucket names must be unique across all AWS  <br>
  • Bucket names can contain upto 63 lowercase letters, numbers, hyphens and  <br>
  • You can create and use multiple buckets  <br>
  • You can have upto 100 per account by  <br>

**Q. What is the function of cross region replication in Amazon S3?**  <br>
Answer: Cross region replication is a feature allows you asynchronously replicate all new objects in the source bucket in one AWS region to a target bucket in another region. To enable cross-region replication, versioning must be turned on for both source and destination buckets. Cross region replication is commonly used to reduce the latency required to access objects in Amazon S3   <br>

**Q. Maximum number of bucket which can be crated in AWS S3.** <br>
Answer:100 buckets can be created by default in AWS account.To get more buckets additionally you have to request Amazon for that. 

 <hr>

**Amazon EC2 (Elastic Compute Cloud) :** <br>
**What is Amazon EC2?** <br>
Amazon EC2 (Elastic Compute Cloud) is a service that provides scalable virtual servers  in the cloud we called it as Instances. It allows users to launch, manage, and scale computing capacity without the need for physical hardware. <br>

✅ Amazon EC2 is Region-Specific Service<br>

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
   1️⃣ General Purpose - General purpose instances provide a balance of compute, memory and networking resources, and can be used for a variety of diverse workloads.	<br>
                         ex. t3.micro, m5.large <br>

   2️⃣ Compute Optimized - High performance processors. <br>
                           ex. (AI, gaming)	c5.2xlarge, c6g.large <br>

   3️⃣ Memory Optimized - Memory optimized instances are designed to deliver fast performance. <br>
                           ex. r5.large, x1e.32xlarge <br>

   4️⃣ Storage Optimized - Storage optimized instances are designed for workloads that require high, sequential read and write access to very large data sets on local storage <br>
                           ex. i3.large, d2.xlarge <br>

   5️⃣ Accelerated Computing - Accelerated computing instances use hardware accelerators, or co-processors, to perform functions.<br>

   6️⃣ HPC Optimized - High performance computing (HPC) instances are purpose built to offer the best price performance for running HPC workloads at scale on AWS. <br>



*3. Launch Templates :* <br>
   **What is a Launch Template?** <br>
    A Launch Template in AWS is a pre-configured blueprint for launching EC2 instances. It helps automate and standardize EC2 instance launches by defining key parameters like: <br>
    Used to launch EC2 instances with specific settings <br>
   ✅ AMI (Amazon Machine Image) <br>
   ✅ Instance type (e.g., t3.micro, m5.large) <br>
   ✅ Security groups & IAM roles <br>
   ✅ Storage (EBS volumes) <br>
   ✅ User data scripts (to run commands on startup) <br>
  Launch Templates simplify EC2 deployment, improve consistency, and support Auto Scaling & Spot Instances. <br>



*4. EC2 Purchasing Models :* <br>
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

  3️⃣ Savings Plans (Flexible Cost Savings) - 💰 Pricing: Similar to RIs but more flexible → Save up to 72% <br>
     📌 Best For: <br>
     ✅ Long-term workloads but with some flexibility <br>
     ✅ Workloads that might change over time <br>
     ✅ Works across all AWS regions <br>
     🔹 Example: If your app may change instance types, Savings Plans are better than RIs. <br>

  4️⃣ Spot Instances (Up to 90% Discount!) - 💰 Pricing: Lowest cost option, but instances can be interrupted. <br>
     📌 Best For: <br>
     ✅ Batch processing, machine learning, big data, CI/CD <br>
     ✅ Applications that can handle interruptions <br>
     ✅ Highly cost-sensitive workloads <br>
     🔹 Example: Running AI training models at a fraction of the cost. <br>

  5️⃣ Dedicated Hosts (Physical Server for You Only) - 💰 Pricing: Expensive but required for compliance & licensing. <br>
     📌 Best For: <br>
     ✅ Running legacy apps that require a physical server <br>
     ✅ BYOL (Bring Your Own License) for software like Windows Server <br>
     ✅ Meeting compliance needs (e.g., HIPAA, GDPR) <br>
     🔹 Example: A company running Windows Server with its own licenses. <br>

   6️⃣ Dedicated Instances (Private EC2 Instances) - 💰 Pricing: More costly than On-Demand, but cheaper than Dedicated Hosts. <br>
      📌 Best For: <br>
      ✅ Workloads that need single-tenant EC2 instances <br>
      ✅ Not as strict as Dedicated Hosts but still private <br>
      🔹 Example: A finance company requiring high security but not full physical control. <br>

   7️⃣ Capacity Reservations - 💰 Pricing: Pay On-Demand rates but guarantee EC2 capacity in a specific region. <br>
      📌 Best For: <br>
      ✅ Mission-critical applications that must always run <br>
      ✅ When you need guaranteed instances in a busy AWS region <br>
      🔹 Example: E-commerce sites preparing for Black Friday traffic. <br>


*5. Amazon Machine Images (AMIs) :* <br>
  *What is an AMI?* <br>
  An Amazon Machine Image (AMI) Used to create instances with pre-installed OS & apps <br>
  It contains: <br>
  ✅ Operating System (OS) – Linux, Windows, macOS <br>
  ✅ Software Packages – Web servers, databases, applications <br>
  ✅ Configurations – Security settings, environment variables <br>
  ✅ EBS Snapshots – Root volume and optional additional storage <br>
  💡 Think of an AMI as a "golden image" that defines how your EC2 instance will be set up! <br>
  

*6. Elastic Block Store :* <br>
**What is Amazon Elastic Block Store (EBS)?**
Amazon Elastic Block Store (EBS) is a high-performance block storage service for EC2 instances. It works like a virtual hard drive that provides persistent storage. Even if the EC2 instance stops or terminates, the data in an EBS volume remains intact. <br>
🔹 Think of EBS as an external SSD attached to your EC2 instance. <br>

Key Features of EBS <br>
✅ Persistent Storage – Data remains even after stopping an EC2 instance. <br>
✅ Scalability – Easily increase storage size without downtime. <br>
✅ High Performance – Optimized for low-latency access. <br>
✅ Multiple Volume Types – Different types for different workloads (SSD, HDD). <br>
✅ Encryption – Supports encryption for security. <br>
✅ Snapshots – Back up EBS volumes to Amazon S3. <br>

Types of EBS Volumes <br>
i. gp3 (General Purpose SSD) --> Next-gen SSD, lower cost, high performance --> Most workloads (web servers, databases) <br>
ii. gp2 (General Purpose SSD) --> Legacy SSD, burstable performance --> Default for general workloads <br>
iii. io2/io1 (Provisioned IOPS SSD) --> High-performance, low-latency --> Databases, transactional apps <br>
iv. st1 (Throughput Optimized HDD) --> Optimized for sequential workloads --> Big data, log processing <br>
v. sc1 (Cold HDD) --> Lowest cost, infrequent access --> Archival storage <br>
🔹 SSD-based EBS (gp3, io2) is best for high-speed access. <br>
🔹 HDD-based EBS (st1, sc1) is best for large, sequential reads/writes. <br>

**Snapshots** <br>
In AWS EC2, a snapshot is a point-in-time backup of an EBS (Elastic Block Store) volume. Snapshots capture the current state of the EBS volume, including all its data, and store it in Amazon S3 (managed internally by AWS). <br>

**Lifecycle Manager** <br>
Amazon Data Lifecycle Manager (DLM) is a service that automates the creation, retention, and deletion of EBS snapshots and AMI (Amazon Machine Images) based on defined policies. It helps you manage the lifecycle of your EBS volumes and AMIs, ensuring that backups are created and removed automatically to reduce costs and improve data protection. <br>

**Network & Security** <br>
In Amazon EC2 (Elastic Compute Cloud), networking and security are critical components that ensure instances can communicate securely and efficiently within AWS and with external systems. AWS provides a range of networking features and security tools to manage traffic flow, protect data, and control access. <br>

**Security Group** <br>
A Security Group in Amazon EC2 (Elastic Compute Cloud) acts as a virtual firewall that controls inbound and outbound traffic for one or more EC2 instances. Security Groups enable you to define rules that allow or deny specific types of network traffic <br>
based on: <br>
Protocol (e.g., TCP, UDP, ICMP) <br>
Port range (e.g., 22 for SSH, 80 for HTTP) <br> 
Source/Destination (e.g., IP addresses, CIDR blocks, or other security groups) <br>

**What is an Elastic IP in EC2?** <br>
An Elastic IP (EIP) in Amazon EC2 (Elastic Compute Cloud) is a static, public IPv4 address that you can allocate to your AWS account and associate with an EC2 instance, network interface, or NAT gateway. <br>
Elastic IPs allow you to maintain a consistent public IP address even if you stop and restart an instance or encounter a failure — which makes them useful for services requiring high availability and consistent network endpoints.  <br>

🔑 **What is a Key Pair in EC2?** <br>
A Key Pair in Amazon EC2 (Elastic Compute Cloud) is a set of two cryptographic keys used for secure login to EC2 instances: <br>
 1. Public Key → Stored on the EC2 instance (AWS-managed). <br>
 2. Private Key → Stored on your local machine (user-managed). <br>

The public key is embedded into the instance when you launch it. You use the private key to authenticate and securely connect to the instance using SSH (Secure Shell) or RDP (Remote Desktop Protocol) for Windows instances. <br>

**Network Interfaces** <br>
An Elastic Network Interface (ENI) in Amazon EC2 is a virtual network interface that attaches to an EC2 instance to enable communication within a Virtual Private Cloud (VPC) and to the internet. <br>
A network interface essentially acts as a virtual network card that allows an EC2 instance to: <br>
 - Communicate with other instances.  <br>
 - Connect to the internet or private networks. <br>
 - Receive or send data using private and public IP addresses. <br>

🏆 *Why Use Network Interfaces?* <br>
✅ Provides network-level flexibility for EC2 instances. <br>
✅ Enables assigning multiple IP addresses to a single instance. <br>
✅ Supports network-level failover by moving the ENI between instances. <br>
✅ Allows instances to communicate privately within a VPC. <br>
✅ Can create and configure ENIs independently from instances. <br>

**What is Load Balancing in AWS?** <br>
Load Balancing is the process of distributing incoming network traffic across multiple servers (or EC2 instances) to: <br>
✅ Improve performance and availability. <br>
✅ Ensure high availability by routing traffic to healthy instances. <br>
✅ Scale infrastructure automatically during peak loads. <br>
✅ Prevent server overload and improve response times. <br>
 
In AWS, Elastic Load Balancer (ELB) is the managed service used for load balancing across EC2 instances, containers, and IP addresses within a VPC (Virtual Private Cloud). <br>

*Types of AWS Load Balancers*                         best for <br>
 1. Classic Load Balancer (CLB) (Legacy) ----> Simple HTTP, HTTPS, TCP traffic  <br>
 2. Application Load Balancer (ALB) ----> HTTP/HTTPS traffic  <br>
 3. Network Load Balancer (NLB) ----> High-performance TCP/UDP traffic  <br>
 4. Gateway Load Balancer (GWLB) ----> Security and network appliances  <br>

**What are Target Groups in EC2?** <br>
A Target Group is a logical grouping of EC2 instances, IP addresses, or AWS Lambda functions that an Elastic Load Balancer (ELB) routes traffic to. <br>

When you create a Load Balancer (ALB, NLB, or GLB), you need to specify one or more Target Groups that the Load Balancer will use to forward traffic. The Load Balancer will distribute incoming traffic to the registered targets in the target group based on the configured routing rules. <br>

**What is Auto Scaling in AWS?** <br>
AWS Auto Scaling is a service that automatically adjusts the number of EC2 instances based on traffic demand. It helps maintain application availability, performance, and cost efficiency by adding or removing instances as needed.  <br>

🔹 Think of Auto Scaling as a system that ensures you always have just the right number of instances running – not too many (to save cost) and not too few (to maintain performance).  <br>

*Key Benefits of Auto Scaling* <br>
✅ High Availability – Keeps applications running smoothly by replacing failed instances.  <br>
✅ Scalability – Automatically increases/decreases instances based on load.  <br>
✅ Cost Optimization – Reduces unused resources, saving money.  <br>
✅ Fault Tolerance – Replaces unhealthy instances with new ones. <br>
✅ Elasticity – Handles traffic spikes without manual intervention. <br>


1️⃣ Vertical Scaling (Scaling Up/Down) <br>
🚀 Increasing or decreasing the power of a single instance. <br>
 - Upgrading an EC2 instance to a more powerful type (e.g., t3.micro → m5.large). <br>
 - Adding more CPU, RAM, or disk space to a single machine. <br>
 - No change in the number of instances, only instance size. <br>

🔹 Best for: <br>
 ✅ Applications that cannot be distributed (e.g., databases like RDS, single-instance apps). <br>
 ✅ Quick performance boost without adding more instances. <br>
 
📌 Example: <br>
 - Upgrading an RDS database from db.t3.medium → db.r5.large to handle more queries. <br>
 - Increasing an EC2 instance’s RAM from 8GB to 16GB for better processing. <br>

⚠️ Limitations: <br>
 - There is a hardware limit (you can’t scale infinitely). <br>
 - Scaling requires a temporary downtime when upgrading. <br>


2️⃣ Horizontal Scaling (Scaling Out/In) <br>
🚀 Adding or removing multiple instances to handle traffic changes. <br>
 - Instead of upgrading a single server, add more servers (instances). <br>
 - Works well with Auto Scaling Groups (ASG) & Load Balancers. <br>
 - No downtime since traffic is distributed among instances. <br>

🔹 Best for: <br>
 ✅ Web apps, APIs, containerized applications (ECS, Kubernetes). <br>
 ✅ Handling high traffic loads dynamically. <br>

📌 Example: <br>
 - A website running on 3 EC2 instances scales up to 10 instances when traffic increases. <br>
 - A load balancer distributes incoming requests across multiple servers. <br>

⚠️ Limitations: <br>
 - Requires applications to be stateless or distributed (e.g., microservices). <br>
 - Managing multiple instances can be more complex. <br>


