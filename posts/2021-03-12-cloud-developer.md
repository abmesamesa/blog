# Cloud developer

I will take fast notes highlighting my learning path.

**2021-03-12**

### What is cloud computing

Cloud Computing is the delivery of IT resources over the Internet. The cloud is like a virtual data center accessible via the Internet that allows you to manage:
- Storage services likes databases
- Servers, compute power, networking
- Analytics, artificial intelligence, augmented reality
- Security services for data and applications

Characteristics of Cloud Computing
- Pay as you go - You pay only for what you use and only when your code runs.
- Autoscaling - The number of active servers can grow or shrink based on demand.
- Serverless - Allows you to write and deploy code without having to worry about the underlying infrastructure.

### Types of Cloud Computing

Infrastructure-as-a-Service (IaaS)
- The provider supplies virtual server instances, storage, and mechanisms for you to manage servers.

Platform-as-a-Service (PaaS)
- A platform of development tools hosted on a provider's infrastructure.

Software-as-a-Service (SaaS)
- A software application that runs over the Internet and is managed by the service provider.

### Cloud Deployment Models

Public Cloud
- A public cloud makes resources available over the Internet to the general public.

Private Cloud
- A private cloud is a proprietary network that supplies services to a limited number of people.

Hybrid Cloud
- A hybrid model contains a combination of both a public and a private cloud.

### Benefits

There are several benefits to the cloud.

- Stop guessing about capacity.
- Avoid huge capital investments up front.
- Pay for only what you use.
- Scale globally in minutes.
- Deliver faster.

### Global Infrastructure

Region
- A region is considered a geographic location or an area on a map.

Availability Zone
- An availability zone is an isolated location within a geographic region and is a physical data center within a specific region.

Edge Location
- An edge location is as a mini-data center used solely to cache large data files closer to a user's location.

Additional Information
- There are more Availability Zones (AZs) than there are Regions.
- There should be at least two AZs per Region.
- Each region is located in a separate geographic area.
- AZs are distinct locations that are engineered to be isolated from failures.

### Shared Responsibility Model

AWS is responsible for security OF the cloud, we are responsible for security IN the cloud.

Some examples

AWS is responsible for:
- Securing edge locations
- Monitoring physical device security
- Providing physical access control to hardware/software
- Database patching
- Discarding physical storage devices

You are responsible for:
- Managing AWS Identity and Access Management (IAM)
- Encrypting data
- Preventing or detecting when an AWS account has been compromised
- Restricting access to AWS services to only those users who need it

### Servers In The Cloud
Servers in the cloud have revolutionized the IT industry.

- Scale capacity up and down based on demands.
- Storage, more memory, and computing power can be added as needed.
- Obtain servers in minutes.
- No need for onsite hardware or capital expenses.

### Elastic Cloud Compute

Elastic Cloud Compute or EC2 is a foundational piece of AWS' cloud computing platform and is a service that provides servers for rent in the cloud.

Pricing Options

There are several pricing options for EC2.
- On Demand - Pay as you go, no contract.
- Dedicated Hosts - You have your own dedicated hardware and don't share it with others.
- Spot - You place a bid on an instance price. If there is extra capacity that falls below your bid, an EC2 instance is provisioned. If the price goes above your bid while the instance is running, the instance is terminated.
- Reserved Instances - You earn huge discounts if you pay up front and sign a 1-year or 3-year contract.

Tips
- EC2 is found under the Compute section of the AWS Management Console.
- Spot instances can save you up to 90% off the on-demand pricing.
- There are several instance types that provide varying combinations of CPU, memory, storage, and networking capacity.

### Elastic Block Store

Elastic Block Store (EBS) is a storage solution for EC2 instances and is a physical hard drive that is attached to the EC2 instance to increase storage.

- EBS is found on the EC2 Dashboard.
- There are several EBS volume types that fall under the categories of Solid State Drives (SSD) and Hard Disk Drives (HDD).
- Persist data after the instance is terminated
- Automatically replicated within its availability zone

### Virtual Private Cloud (VPC)

Virtual Private Cloud or VPC allows you to create your own private network in the cloud. You can launch services, like EC2, inside of that private network. A VPC spans all the Availability Zones in the region.

VPC allows you to control your virtual networking environment, which includes:

- IP address ranges
- subnets
- route tables
- network gateways

Tips
- VPC is found under Networking & Content Delivery section of the AWS Management Console.
- The default limit is 5 VPCs per Region. You can request an increase for these limits.
- Your AWS resources are automatically provisioned in a default VPC.
- There are no additional charges for creating and using the VPC. 
- You can store data in Amazon S3 and restrict access so that it’s only accessible from instances in your VPC.

### VPC ACL

- A network access control list (ACL) defines the set of firewall rules for controlling traffic coming in and out of subnets in your VPC.
- The default network ACL allows all inbound and outbound IPv4 traffic.
- Inbound/Outbound rules are numbered and ordered. The lowest numbered rule is evaluated first.
- Network ACLs are stateless.

### Compute Power In The Cloud
Compute power in the cloud is a faster way to build applications, providing:

- no servers to manage (i.e. serverless)
- ability to continuously scale
- ability to run code on demand in response to events
- pay only when your code runs

### Lambda

AWS Lambda provides you with computing power in the cloud by allowing you to execute code without standing up or managing servers.

- Lambdas have a time limit of 15 minutes.
- The code you run on AWS Lambda is called a “Lambda function.”
- Lambda code can be triggered by other AWS services.
- AWS Lambda supports Java, Go, PowerShell, Node.js, C#/.NET, Python, and Ruby. There is a Runtime API that allows you to use other programming languages to author your functions.
- Lambda code can be authored via the console.

### Elastic Beanstalk

It is an orchestration service that allows you to deploy a web application at the touch of a button by spinning up (or provisioning) all of the services that you need to run your application.

- Elastic Beanstalk is found under the Compute section of the AWS Management Console.
- Elastic Beanstalk can be used to deployed web applications developed with Java, .NET, PHP, Node.js, Python, Ruby, Go, and Docker.
- You can run your applications in a VPC.

**2021-03-15**

### Storage in the Cloud

Storage and database services in the cloud provide a place for companies to collect, store, and analyze the data they've collected over the years at a massive scale.

Storage & Database Services
- Amazon Simple Storage Service (Amazon S3)
- Amazon Simple Storage Service (Amazon S3) Glacier
- DynamoDB
- Relational Database Service (RDS)
- Redshift
- ElastiCache
- Neptune
- Amazon DocumentDB

A compromise between durability, scalability and availability.

### S3 & Glacier

Amazon Simple Storage Service (or S3) is an object storage system in the cloud.

S3 use cases

- Static website
- CDN
- Backup and recovery
- Archiving big data
- Application data
- Hybrid cloud storage

Storage Classes: S3 offers several storage classes, which are different data access levels for your data at certain price points.

- S3 Standard
- S3 Glacier
- S3 Glacier Deep Archive
- S3 Intelligent-Tiering
- S3 Standard Infrequent Access
- S3 One Zone-Infrequent Access

A single object can be up to 5 terabytes in size.
You can enable Multi-Factor Authentication (MFA) Delete on an S3 bucket to prevent accidental deletions.
S3 Acceleration can be used to enable fast, easy, and secure transfers of files over long distances between your data source, and your S3 bucket.

### DynamoDB

DynamoDB is a NoSQL document database service that is fully managed. Unlike traditional databases, NoSQL databases, are schema-less. Schema-less simply means that the database doesn't contain a fixed (or rigid) data structure.

- DynamoDB is found under the Database section on the AWS Management Console.
- DynamoDB can handle more than 10 trillion requests per day.
- DynamoDB is serverless as there are no servers to provision, patch, or manage.
- DynamoDB supports key-value and document data models.
- DynamoDB synchronously replicates data across three AZs in an AWS Region.
- DynamoDB supports GET/PUT operations using a primary key.

### Relational Database Service (RDS)

RDS (or Relational Database Service) is a service that aids in the administration and management of databases. RDS assists with database administrative tasks that include upgrades, patching, installs, backups, monitoring, performance checks, security, etc.

Database Engine Support
- Oracle
- PostgreSQL
- MySQL
- MariaDB
- SQL Server

Features
- failover
- backups
- restore
- encryption
- security
- monitoring
- data replication
- scalability

### Redshift
Redshift is a cloud data warehousing service to help companies manage big data. Redshift allows you to run fast queries against your data using SQL, ETL, and BI tools. Redshift stores data in a column format to aid in fast querying.

- Redshift delivers great performance by using machine learning.
- Redshift Spectrum is a feature that enables you to run queries against data in Amazon S3.
- Redshift encrypts and keeps your data secure in transit and at rest.
- Redshift clusters can be isolated using Amazon Virtual Private Cloud (VPC).

### Content Delivery In The Cloud

A Content Delivery Network (or CDN) speeds up delivery of your static and dynamic web content by caching content in an Edge Location close to your user base.

Benefits
- The benefits of a CDN includes:
- low latency
- decreased server load
- better user experience

### Cloud Front
CloudFront is used as a global content delivery network (CDN). Cloud Front speeds up the delivery of your content through Amazon's worldwide network of mini-data centers called Edge Locations.

CloudFront works with other AWS services, as shown below, as an origin source for your application:

- Amazon S3
- Elastic Load Balancing
- Amazon EC2
- Lambda@Edge
- AWS Shield

Comments

- Amazon continuously adds new Edge Locations.
- CloudFront ensures that end-user requests are served from the closest edge location.
- CloudFront works with non-AWS origin sources.
- You can use GeoIP blocking to serve content (or not serve content) to specific countries.
- Cache control headers determine how frequently CloudFront needs to check the origin for an updated version your file.
- The maximum size of a single file that can be delivered through Amazon CloudFront is 20 GB.
