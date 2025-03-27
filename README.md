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

   iii. Memory Optimized - Memory optimized instances are designed to deliver fast performance for workloads that process large data sets in memory.	<br>
                           ex. r5.large, x1e.32xlarge <br>

   iv. Storage Optimized - Storage optimized instances are designed for workloads that require high, sequential read and write access to very large data sets on local storage <br>
                           ex. i3.large, d2.xlarge <br>

   v. Accelerated Computing - Accelerated computing instances use hardware accelerators, or co-processors, to perform functions, such as floating point number calculations, graphics processing, or data pattern 
      matching, more efficiently than is possible in software running on CPUs. <br>

   vi. HPC Optimized - High performance computing (HPC) instances are purpose built to offer the best price performance for running HPC workloads at scale on AWS. HPC instances are ideal for applications that 
       benefit from high-performance processors such as large, complex simulations and deep learning workloads. <br>

   

 








