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

### AWS WAF
AWS WAF (or AWS Web Application Firewall) provides a firewall that protects your web applications. WAF can stop common web attacks by reviewing the data being sent to your application and stopping well-known attacks.

- WAF is found under the Security, Identity, & Compliance section on the AWS Management Console.
- WAF can protect web sites not hosted in AWS through Cloud Front.
- You can configure CloudFront to present a custom error page when requests are blocked.
- AWS WAF is available under a composite dashboard, WAF & Shield, that combines the following three services:

AWS WAF: It allows you to protect your web applications from common web exploits by monitoring and controlling the web requests coming to an Amazon API Gateway API, an Amazon CloudFront distribution, or an Application Load Balancer.  
AWS Shield: It provides continuous DDoS attack detection and automatic mitigations. AWS Shield offers two tiers of protection - Standard and Advanced.  
AWS Firewall Manager: It allows you to configure and manage firewall rules across accounts and applications centrally.  

Within AWS WAF service, you can create Web access control lists (web ACLs) to monitor HTTP(S) requests for AWS resources. You can protect the following types of resources:

- CloudFront distributions
- Regional resources (Application Load Balancer, API Gateway, AWS AppSync)

While creating a web ACL, you add rules, such as conditions like originating IP addresses, that determines whether to allow/block each request.

### AWS Shield
AWS Shield is a managed DDoS (or Distributed Denial of Service) protection service that safeguards web applications running on AWS. AWS Shield offers two tiers of protection - Standard and Advanced.

- Standard tier: Standard AWS Shield is a service that you get "out of the box", it is always running (automatically) and is a part of the free standard tier.
- Advanced tier: If you want to use some of the more advanced features, you'll have to utilize the paid tier.

### IAM key terms

1. IAM User
   A user is a unique identifier generated by the IAM service and recognized by all AWS services to grant access to AWS resources. A user can be a person, system, or application that requires access to AWS services. You can generate login credentials and access keys for any user in your account. Roles and policies control the scope (permissions) of a user's access to AWS resources in your account.

2. IAM Group
   A group collects IAM users with the same level of permissions to access AWS resources. You can attach or detach permissions to a group using access control policies. A group makes it easier to manage IAM users with the same level of permissions.

3. IAM Role
   A role is simply a set of policies (permissions) to access AWS services. You can assign a role either to an IAM user or an AWS service such as EC2. Creating and storing roles helps to delegate access with defined permissions without sharing long-term access keys.

Difference between an IAM role and an IAM user
An IAM user has permanent credentials that can be used to interact with AWS services directly. In contrast, an IAM role does not have any credentials; hence it cannot make direct requests to AWS services. IAM roles are assumed by authorized entities, such as IAM users, applications, or other AWS services.

4. IAM Policy
   An access control policy is a JSON file that defines the resource to grant access, level of access, and allowed actions. You can attach a policy to multiple users, groups, or roles to assign permissions to AWS resources.

**2021-03-18**

### Route 53
Route 53 is a cloud domain name system (DNS) service that has servers distributed around the globe used to translates human-readable names like www.google.com into the numeric IP addresses like 74.125.21.147.

Features

- scales automatically to manage spikes in DNS queries
- allows you to register a domain name (or manage an existing)
- routes internet traffic to the resources for your domain
- checks the health of your resources
- Route 53 allows you to route users based on the user’s geographic location.

### EC2 Auto Scaling

EC2 Auto Scaling is a service that monitors your EC2 instances and automatically adjusts by adding or removing EC2 instances based on conditions you define in order to maintain application availability and provide peak performance to your users.

Features
- Automatically scale in and out based on needs.
- Included automatically with Amazon EC2.
- Automate how your Amazon EC2 instances are managed.
- EC2 Auto Scaling adds instances only when needed, optimizing cost savings.
- EC2 predictive scaling removes the need for manual adjustment of auto scaling parameters over time.

### Elastic Load Balancing

Elastic Load Balancing automatically distributes incoming application traffic across multiple servers.

Elastic Load Balancer is a service that:

- Balances load between two or more servers
- Stands in front of a web server
- Provides redundancy and performance
- Elastic Load Balancing works with EC2 Instances, containers, IP addresses, and Lambda functions.
- You can configure Amazon EC2 instances to only accept traffic from a load balancer.

Application Load balancer

Choose an Application Load Balancer when you need a flexible feature set for your web applications with HTTP and HTTPS traffic. Operating at the request level, Application Load Balancers provide advanced routing and visibility features targeted at application architectures, including microservices and containers.

Network load balancer

Choose a Network Load Balancer when you need ultra-high performance, TLS offloading at scale, centralized certificate deployment, support for UDP, and static IP addresses for your application. Operating at the connection level, Network Load Balancers are capable of handling millions of requests per second securely while maintaining ultra-low latencies.

### Messaging in the Cloud

There are often times that users of your applications need to be notified when certain events happen. Notifications, such as text messages or emails can be sent through services in the cloud. The use of the cloud offers benefits like lowered costs, increased storage, and flexibility.

### Simple Notification Service
Amazon Simple Notification Service (or SNS) is a cloud service that allows you to send notifications to the users of your applications. SNS allows you to decouple the notification logic from being embedded in your applications and allows notifications to be published to a large number of subscribers.

- SNS uses a publish / subscribe model.
- SNS can publish messages to Amazon SQS queues, AWS Lambda functions, and HTTP/S webhooks.
- SNS Topic names are limited to 256 characters.
- A notification can contain only one message.

### Queues
A queue is a data structure that holds requests called messages. Messages in a queue are commonly processed in order, first in, first out (or FIFO).

Messaging queues improve:

- performance
- scalability
- user experience

### Simple Queue Service
Amazon Simple Queue Service (SQS) is a fully managed message queuing service that allows you to integrate queuing functionality in your application. SQS offers two types of message queues: standard and FIFO.

- send messages
- store messages
- receive messages
- FIFO queues support up to 300 messages per second.
- FIFO queues guarantee the ordering of messages.
- Standard queues offer best-effort ordering but no guarantees.
- Standard queues deliver a message at least once, but occasionally more than one copy of a message is delivered.

### Containers

OS level virtualization allows us to run multiple isolated processes in parallel. A container is an isolated process that consists of the following items, all bundled into one package:

- the application code,
- the required dependencies (e.g. libraries, utilities, configuration files), and
- the necessary runtime environment to run the application.

Each container is an independent component that can run on its own and be moved from environment to environment.

- Containers make it easier for developers to create, deploy, and run applications on different hardware and platforms, quickly and easily.
- Containers share a single kernel and share application libraries.
- Containers cause a lower system overhead as compared to Virtual Machines.

Docker

Docker is a (container runtime) tool that helps to build, test, and run containers. You can build containers locally using a command-line utility, Docker Desktop. If there are multiple containers running individual services of an application, you will need to use Docker Compose utility to specify dependent relationships between containers.

Docker Image

An image (or Docker image) is a portable auto-generated template that contains a set of instructions to create a container. An image can be instantiated multiple numbers of times to create multiple containers.

Dockerfile

A text file containing commands to create an image. In other words, Docker generates images by reading the commands from a Dockerfile.

### ECS (Elastic container service)

ECS is an orchestration service used for automating deployment, scaling, and managing of your containerized applications. ECS works well with Docker containers by:

- launching and stopping Docker containers
- scaling your applications
- querying the state of your applications
- You can schedule long-running applications, services, and batch processes using ECS.
- Docker is the only container-runtime platform supported by Amazon ECS. Other container-runtime tools available in the industry are Rocket, LXD, OpenVZ, any a few more.

### Cloud Trail
Cloud Trail allows you to audit (or review) everything that occurs in your AWS account. Cloud Trail does this by recording all the AWS API calls occurring in your account and delivering a log file to you.

CloudTrail provides event history of your AWS account activity, including:

- who has logged in
- services that were accessed
- actions performed
- parameters for the actions
- responses returned

This includes actions taken through the AWS Management Console, AWS SDKs, command line tools, and other AWS services.

- CloudTrail shows results for the last 90 days.
- You can create up to five trails in an AWS region.

### Cloud Watch

Cloud Watch is a service that monitors resources and applications that run on AWS by collecting data in the form of logs, metrics, and events.

Features
- There are several useful features:
- Collect and track metrics
- Collect and monitor log files
- Set alarms and create triggers to run your AWS resources
- React to changes in your AWS resources
- Metrics are provided automatically for a number of AWS products and services.

### Cloud Formation
AWS Cloud Formation allows you to model your entire infrastructure in a text file template allowing you to provision AWS resources based on the scripts you write.

- Cloud Formation templates are written using JSON or YAML.
- You can still individually manage AWS resources that are part of a CloudFormation stack.

### AWS Command Line Interface (CLI)
The AWS CLI (or Command Line Interface) allows you to access and control services running in your AWS account from the command line. To use the CLI, simply download, install, and configure it.

- The AWS CLI allows you to work with AWS services in a programmatic manner

In order to use the aws cli:
- Install AWS CLI
- Create an admin iam user (AdministratorAccess policy) with programmatic access
- Configure the profile (called default in that case) `aws configure --profile default`
- Export the variables `export AWS_CONFIG_FILE=~/.aws/config` and `export AWS_SHARED_CREDENTIALS_FILE=~/.aws/credentials`
- Check the configuration with `aws configure list`
- Test the credential by using a simple command like `aws iam list-users`
- Create a bucket with `aws s3api create-bucket --bucket my-bucket-name --acl public-read-write --region eu-west-3 --profile default --create-bucket-configuration LocationConstraint=eu-west-3`
- Upload a file `aws s3api put-object --bucket my-bucket-name --key name-in-bucket --body path/to/file --profile default`
- Delete a file `aws s3api delete-object --bucket my-bucket-name --key name-in-bucket`
- Delete the bucket `aws s3api delete-bucket --bucket my-bucket-name --profile default`

**2021-04-23**

### Tips for creating a RESTful API

API - Application program interface

- Use plural, consistent nouns and no verbs.
- Version the api `host/api/v1/books/`
- Paginate lists `host/api/v1/books/?offset=40&limit=100`
- Responses send status codes
- Responses send a data format
- Error payloads includes useful messages

### Consumable API

- Consumable APIs are accessible from outside the organisation
- No consumable APIs aren't accessible to those outside

### Persisting

Some terrible ideas or options:

- RAM (Random Access Memory): Data can be accessed quickly, but is erased once the server restarts. It may be okay to use RAM when prototyping, and later replace it with a database.
- Hard Drive Disk: Data remains after server restarts, but is specific to that server (not shared across servers).
- Race Condition: When an application’s behavior is dependent on other uncontrollable events. This is an issue with storing data on disks or RAM of multiple servers.
- Relational Database: can store at scale, improve search runtime, and maintain relationships between data fields. We recommend using a database for storing data.

Basic concepts about databases:

- B-Tree: a generalization of a binary search tree, which stores sorted data, but can have more than 2 child nodes.
- Bloom Filters: a data structure that is useful for determining if an item is probably in a data set, or definitely not in the data set. Bloom filters don’t actually store the data themselves.
- primary key and foreign key: The primary consists of one or more column in a table that are unique to each record (each row). A foreign key in a table contains the primary key of another table.

Files

- File stores allow for archiving data. In AWS, the file store is called S3, and the archive resource is called “glacier”.
- Content Delivery Network (CDN): are a network of proxy servers that are placed closer to end users to deliver data and compute. CDNs reduce latency for end users.
- SignedURLs allow clients to send and receive data by directly communicating with the file store. This saves the server from using its bandwidth to serve as the intermediary that transmits data to and from the client. This is faster for clients as well.
- Buckets: a simple directory-like system in which to store data.

**2021-04-26**

### Access buckets via console

```bash
aws s3 ls [s3://bucketname] [--profile profile-name]
```

We can create roles, groups and permissions.

We can attach groups to users and roles to services to give a specific set of permissions to some kind of users (like developers), to some kind of services (like a s3 bucket)

### Notes

- Create “dev” resources: Use the “dev” set of infrastructure (set of servers, filestores, databases) for development, and a separate set of infrastructure for production.
- AES 256: Advanced Encryption Standard with a 256-bit key. This is a popular encryption standard.
- CORS: Cross Origin Resource Sharing: defines how a client can interact with a resource, and what the client can and cannot do with that resource. Setting the CORS policy of our S3 bucket allows our client to communicate with the S3 bucket using the SignedURL pattern.
- Use environment variables to store your username and password, to avoid hard-coding username and password information in your code.
- Avoid committing your passwords to git. Use .gitignore to define files that you do not want to commit to git.
- IAM user role: an IAM role can give a user a set of permissions to access one or more services.
- IAM service role: an IAM role gives a service a set of permissions to access one or more services.

### Elastic Beanstalk

- Install the EB cli
- `eb init` creates a beanstalk config file
- We add a deployment artifact target within this file so that EB knows which code to be deployed
```yaml
deploy:
  artifact: ./www/Archive.zip
```
- `eb create` creates the environment in aws infrastructure and upload the application.
- `eb deploy application-name` will deploy your artifact.

**2021-04-28**

### Auth

- Password encryption in transit
- Password encryption in database
- Recommended way: Salted (extra random data), hashed (jumbled text) strings using bcrypt (at this time is a good one way encryption algorithm)

### JWT

- Once the user authenticated we send a json web token.
- The client will send the token along with each request.

**2021-05-04**

### Monolith vs Microservice

Monolith
- Utilize a powerful, more costly machine
- Codebase is centralized and easy manage
- Code is easily shared across the project
- Scoped for worst-case usage across all parts of the application

Microservice
- Utilize smaller, cost-effective machines for what we need
- Flexibility to implement logic in a way that makes sense for the team and business
- Lean to be targeting a specific business purpose
- Interfaces set up for building out other applications
- Try not to overcommit and pay for resources that aren't needed

### Some considerations of microservices

Business Requirements Drive Teams: Teams can be organized around business needs and have a clearer focus on customer requirements. There is clear ownership on who owns what.

Teams Can Work in Parallel: Since projects are deployed independently, teams can develop and deploy code without stepping on each others' toes.

Flexibility in Technology: We are not limited to a certain technology and can choose what may work best for the business need or team.

### Considerations for Not Using Microservices
System Complexity: Rather than deploying a single application, we would be deploying multiple modules separately. There is more overhead in setting up projects.

Network Latency: By introducing a network between modules, we have increased latency in application performance and will find it harder to debug our application.

Difficulty with Debugging: We can no longer rely on a stack trace or tools that can help us pinpoint where a bug is. We may end up relying on logging to find causes of issues.

### What is a microservice
Architectural style where our application is composed of several modules that can be developed and deployed independently.

- Different applications communicates through networks.
- Scale is more easy.
- Cost-effective.
- Parallel development.
- Flexibility.

### Properties of Microservices

Communication
- Services communicate through a network
- REST is currently the most-commonly used network interface

Independently Deployed
- Deployment to one service should not affect another

Fault tolerant
- Diligence in writing code that can anticipate when another microservice isn’t working

### How to make a decision

- Dependency graphs are one way to help us visualize and make an informed decision
- We often have to use additional context with regards to business functionality to weigh decisions
- Database complexity should also be considered for refactors. Services that seem simple may have complicated refactor strategies with their databases.

### Microservice Benefits
- Scale
- Development in Parallel
- Cost Effectiveness
- Flexibility

### Microservice Properties
- Communication
- Independently Deployed
- Fault tolerant

### Refactor Strategies
- Dependency Graph as a starting point to understand downstream effects of modules
- Strangler Pattern as an approach to how we gradually refactor our code in pieces

### Docker terms

Base Image  
A set of common dependencies built into a Docker image that acts as a starting point to build an application’s Docker images to reduce build times

Container  
Grouped software dependencies and packages that make it easier and more reliable to deploy software

Container Registry  
A centralized place to store container images

Docker-compose  
A tool used to run multiple Docker containers at once; often used to specify dependent relationships between containers

Dockerfile  
A file containing instructions on how to translate an application into an image that can be run in containers

Ephemeral  
Software property where an application is expected to be short-lived

Image  
A snapshot of dependencies and code used by Docker containers to run an application

### Docker container registry

As GitHub, DockerHub is a centralized place to store our images.

We can create a repository in DockerHub

We take our local image un put it into our docker hub.
```bash
docker tag local_image_name user_name/repository_name
# we should login to execute the next command
docker push user_name/repository_name
```
