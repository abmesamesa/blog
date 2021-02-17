# AWS learning path notes

I will take notes about the progress learning AWS.

**2021-01-24**

### List of the main compute services

**EC2** Elastic compute cloud: Allows deploying virtual servers.  
**ECS** Elastic container service: Allows running docker-enabled applications packaged as containers across a cluster of EC2 instances.  
**ECR** Elastic container registry: Provides a secure location to store and manage docker images.  
**EKS** Elastic container service for kubernetes: Allows running Kubernetes across the aws infrastructure without to take care of provisioning.  
**Beanstalk** Elastic beanstalk takes uploaded code and automatically provisions and deploys the required resources. Great of inexperience profiles.  
**Lambda** AWS Lambda is a serverless compute service that allows running apps without having to manage EC2 instances.  
**Batch-CF** AWS Batch allows running and managing batch computing workloads.  
**Lightsail** AWS Lightsail is a VPS (virtual private server) like an EC2 but without as many configuration steps. Better for lower cost, small scale, small business or individuals.

**2021-01-25**

### Lab. Creating an EC2 instance

- Configure and launch an instance in EC2
- Understand the Instance States and other critical instance information
- Generate and use a Secure Shell (SSH) public/private key pair
- Connect to a running Linux instance using an SSH client
- Extract metadata about your running instance
  - We can use this within the shell of the instance: `curl -w "\n" http://169.254.169.254/latest/meta-data/`  
- Terminate an instance

**2021-01-27**

### ELBs and EC2

- Understand what an elastic load balancer is and what is used for
- Be aware of the different load balancers available to you in AWS
- Understand how ELBs handle different types of requests, including those that are encrypted
- Be able to identify the different components of ELBs
- Know how to configure ELBs
- Know when and why you might need to configure an SSL/TLS certificate
- Understand what EC2 auto scaling is
- Be able to configure auto scaling launch configurations, launch templates and auto scaling groups
- Explain why you should use ELBs and auto scaling together

**2021-01-31**

### Aws global infrastructure

Understanding these components:

- Availability Zones (AZs)
- Regions
- Edge Locations
- Regional Edge Caches

**2021-02-02**

### Aws storage services

- An overview and introduction to the different AWS storage services, including EBS Storage
- An understanding of how to transfer data into and out of AWS
- The knowledge to confidently select the most appropriate storage service for your needs

#### S3 Amazon simple storage service

- Object based storage service
- Regional based
- Best durability and availability 99.99%
- Objects are stored in buckets (globally uniques)
- Several storage classes are proposed depending on the frequency of access
- Bucket policies set access controls to particular buckets
- ACLs (Access control lists) control access of user outside the aws account
- Data can be encrypted (Server side or Client side)
- SSL is supported
- Versioning is possible (adds a cost, cannot be disabled, only suspended)
- Lifecycle rules can be configured
- Great for data backup, static content and websites and large data sets
- Not great for data archiving, dynamic data, file system required, structured data that need to be queried

#### Amazon glacier

- Low cost, long term storage
- It does not provide instant access to data
- Organized in vaults (containers) and archives (any object as in S3)
- Managed via API
- Data is encrypted
- Vault data policies and vault lock policies can be configured

#### EC2 instance storage

- Local disk drives associated to an instance
- Ephemeral
- Instance stopped of terminated the data is lost
- Instance reboot keep the data
- Included in the price of an instance
- Very high I/O
- Ideal for cache, buffer

#### Elastic block store EBS

- Persistent and durable data storage
- Data stored in blocks instead of objects
- Low latency access  
- Can be attached to an EC2 instance, but they remain independent
- Backups can be made (Snapshots) stored in S3, incrementally
- A snapshot can be used to recreate an EBS volume
- EBS volumes are replicated by AZ
- General purpose SSD EBS volume can be used to store databases
- Offers encryption on selected volumes types
- Can be accessed by one instance at a time  
- Not recommended for temporary storage or multi-instance storage access

#### Elastic file system

- Low latency access
- Can be accessed by several instances at once
- Supports NFS 4.1/0

#### CloudFront

- Is a CDN (Content delivery network)
- Cached data in edge locations
- Origin data can come from S3

**2021-02-16**

### Aws VPC and networking components

Topics

- Virtual Private Clouds (VPCs)
- Subnets
- Route Tables
- Network Access Control Lists (NACLs)
- Security Groups
- NAT Gateways
- Bastion Hosts
- VPN and Direct connection
- VPC Peering
- AWS Transit Gateway

Objectives

- Confidently architect a VPC across multiple availability zones within a Region
- Explain different networking components commonly used within AWS VPCs
- Secure your VPCs, helping you to protect your resources within them
- Assess which method of connectivity to your VPCs would be best in different scenarios

#### VPC

- Your own isolated cloud inside the aws cloud.
- It allows to provision and deploy your application within the vpc.
- Up to 5 VPCs per region, per account. 
- When creating a Vpc you need to give it a name, and a CIDR block address.

#### Subnets

- Segment vpc infrastructure into many networks
- Any subnet create within the VPC need to reside inside the CIDR block address of the VPC.
- Can be public or private subnets. By default, they are private (can't access Internet).
- Public subnets are accessible from the outside (Internet) as web servers. Web servers would have 2 IP addresses (one internal in the range of the Subnet CIDR block and one public)
- Private subnets are inaccessible by default (Backend, databases)
- To make public a subnet we need to create an Internet Gateway attached to our VPC and create a route in the route table of the subnet mapping any route not known by the route table and the internet gateway.
- The first 4 addresses of the subnet CIDR block, and the last one are reserved and can not be used.

#### NACLs

- Network access control list: network level firewall
- By default, accept all the traffic
- The can control Inbound and Outbound traffic
- Stateless by design

#### Segurity groups

- Instance level firewall
- Stateful by design

#### NAT Gateway

- It allows traffic originated within you EC2 instance from the internet, so for instance you can keep your instances up to date while keeping them within a private subnet.

#### Bastion host

- Gain access to instance in a private subnet from the internet through a secured machine
- Best practice is to use ssh key forwarding to store the private keys of the keys in the machine of the engineer (and not in the bastion host)
