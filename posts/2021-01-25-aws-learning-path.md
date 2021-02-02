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
