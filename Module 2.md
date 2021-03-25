# Module 2: Compute in the cloud

**Multitenancy:** Sharing underlying hardware between virtual machines.
**Vertical scaling:** Give an instance more memory or more CPU depending on needs.

## Amazon Elastic Compute Cloud (Amazon EC2)
Amazon Elastic Compute Cloud (Amazon EC2) provides secure, resizable compute capacity in the cloud as Amazon EC2 instances. EC2s can be copied to other regions. Characteristics:
- Allows the customer to retain full administrative privileges of the underlying virtual infrastructure
- You pay only for the compute time you use when an instance is running, not when it is stopped or terminated.

### How Amazon EC2 works
1. Launch: You launch an instance by selecting a template with basic configurations. These configurations include:
   - Operating system
   - Application server or applications
   - Instance type, which is the specific hardware configuration of your instance. 
   - Security settings to control the network traffic that can flow into and out of your instance.
1. Connect: Your programs and applications have multiple different methods to connect directly to the instance and exchange data.
1. Use

### Instance types
- **General purpose:** Provides a balance of compute, memory, and networking resources.
- **Compute optimized:** Ideal for compute-bound applications that benefit from high-performance processors.
- **Memory optimized:** Designed to deliver fast performance for workloads that process large datasets in memory.
- **Accelerated computing:** Uses hardware accelerators, or coprocessors, to perform some functions more efficiently than is possible in software running on CPUs. Ideal for workloads such as graphics applications, game streaming, and application streaming.
- **Storage optimized:** Designed for workloads that require high, sequential read and write access to large datasets on local storage. Ideal for data warehousing applications.

The term input/output operations per second (IOPS) is a metric that measures the performance of a storage device.

### Pricing
- **On-Demand:** Ideal for short-term, irregular workloads that cannot be interrupted. No upfront costs or minimum contracts apply. The instances run continuously until you stop them, and you pay for only the compute time you use. Instance type, AMI type and Region determine cost.
- **Amazon EC2 Savings Plans:** Reduce your compute costs by committing to a consistent amount of compute usage for a 1-year or 3-year term.
- **Reserved Instances:** Billing discount applied to the use of On-Demand Instances in your account. Extend boundaries across different Availability Zones.
- **Spot Instances:** Ideal for workloads with flexible start and end times, or that can withstand interruptions. Spot Instances use unused Amazon EC2 computing capacity. Useful for dev/test environments. If the instance is stopped by Amazon in the first hour, this first hour is not billed.
- **Dedicated Hosts:** Physical servers with Amazon EC2 instance capacity that is fully dedicated to your use.

### Scalability
Scalability involves beginning with only the resources you need and designing your architecture to automatically respond to changing demand by scaling out or in. 

### EC2 Auto Scaling
Enables you to automatically add or remove Amazon EC2 instances in response to your applications demand. By automatically scaling your instances in and out as needed, you are able to maintain a greater sense of application availability.

Within Amazon EC2 Auto Scaling, you can use two approaches: 
1. Dynamic scaling responds to changing demand. 
1. Predictive scaling automatically schedules the right number of EC2 instances based on predicted demand.

When you create an Auto Scaling group, you can set the minimum number of Amazon EC2 instances which is the number of instances that launch immediately after you have created the Auto Scaling group. Next, you can set the desired capacity, and then the **maximum** capacity.

### Elastic Load Balancing
Elastic Load Balancing is the AWS service that automatically distributes incoming application traffic across multiple resources. 

A load balancer acts as a single point of contact for all incoming web traffic to your Auto Scaling group. This means that as you add or remove EC2 instances in response to the amount of incoming traffic, these requests route to the load balancer first. Load Balancers now support invoking Lambda functions to serve HTTP(S) requests.

**Application Load Balancer:** Apt for http and https traffic load balancing.

## Monolithic applications and microservices
**Monolithic application:** Application with tightly coupled components. In this approach to application architecture, if a single component fails, other components fail, and possibly the entire application fails.
**Microservices approach:** Application components are loosely coupled. If a single component fails, the other components continue to work because they are communicating with each other.

### Amazon Simple Notification Service (Amazon SNS)
Is a publish/subscribe service. Using Amazon SNS topics, a publisher publishes messages to subscribers. SNS messages can be sent to registered addresses through email and lambdas.

### Amazon Simple Queue Service (Amazon SQS)
Is a message queuing service. Using Amazon SQS, you can send, store, and receive messages between software components, without losing messages or requiring other services to be available. In Amazon SQS, an application sends messages into a queue. A user or service retrieves a message from the queue, processes it, and then deletes it from the queue. Implements messaging that is a typical integration pattern to **decouple application components**.

## Serverless computing
Your code runs on servers, but you do not need to provision, manage or manage these servers. Another benefit is the flexibility to scale serverless applications automatically. Serverless computing can adjust the applications' capacity by modifying the units of consumptions, such as throughput and memory.

### AWS Lambda
Service that lets you run code without needing to provision or manage servers. While using AWS Lambda, you pay only for the compute time that you consume. 

**AWS Lambda@Edge** is a serverless service that makes it possible to run event-triggered functions on Edge Locations within the AWS Content Delivery Network. Using AWS CloudFront, an administrator can introduce decision-making and compute processing closer to the viewer’s location. 

## Containers
Standard way to package an application's code and dependencies into a single object. You can also use containers for processes in which there are essential requirements for security, reliability, and scalability. Container orchestration services help you to deploy, manage, and scale your containerized applications.

### Amazon Elastic Container Service (Amazon ECS)
Highly scalable, high-performance container management system that enables you to run and scale containerized applications on AWS. 
Amazon ECS supports Docker containers. Docker is a software platform that enables you to build, test, and deploy applications quickly. With Amazon ECS, you can use API calls to launch and stop Docker-enabled applications.

### Amazon Elastic Kubernetes Service (Amazon EKS)
Fully managed service that you can use to run Kubernetes on AWS. 
Kubernetes is open-source software that enables you to deploy and manage containerized applications at scale. 

### AWS Fargate
Serverless compute engine for containers. It works with both Amazon ECS and Amazon EKS. Manages your server infrastructure for you. You pay only for the resources that are required to run your containers.

## Other services
**Code Commit:** Helps in hosting git-based repositories securely.

**Code Deploy:** is a deployment service that allows developers to automate the installation of applications. AWS CodeDeploy can enable the update of those applications. 

**Code Guru:** Development tool powered by ML, that provides code quality improvement recommendations.

**Code Pipeline:** Management tool that facilitates automation of various phases of the release process. Does not provide infrastructure.

**Code Star:** Unified user interface. Helps in swift and quick development, build and deployment of applications in AWS.

**Kinesis:** Makes it easy to collect, process, and analyze real-time, streaming data so you can get timely insights and react quickly to new information.

**Kinesis Data Analytics:** A fully managed solution and you want to use SQL to process the data from your data stream. 

**Lightsail:** is an easy-to-use cloud platform that offers you everything needed to build an application or website, plus a cost-effective, monthly plan. “Upgrade to EC2” is the feature that allows customers to “create copy in EC2”.

**ParallelCluster:** is an open-source cluster management tool supported by AWS that helps customers deploy and manage HPC clusters in AWS.

**Quick Starts:** Helps in automating deployments aligned with the best practices. CloudFormation templates are included.

**Transfer Family:** SFTP, FTPS, FTP.

**X-Ray:** Helps developers analyze and debug production, distributed applications, such as those built using a microservices architecture. Can be used to detect performance issues for AWS Lambda applications.