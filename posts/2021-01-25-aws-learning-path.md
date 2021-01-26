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
