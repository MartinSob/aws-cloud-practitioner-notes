# Module 3: Global infrastructure and reliability
## Selecting a Region
- Compliance with data governance and legal requirements: Depending on your company and location, you might need to run your data out of specific areas.
- Proximity to your customers: Selecting a Region that is close to your customers will help you to get content to them faster.
- Available services within a Region: The closest Region might not have all the features that you want to offer to customers.
- Pricing: May change based on local taxes or other factors.

## Availability zone
Single data center or a **group** of data centers within a Region. Availability Zones are located tens of miles apart from each other. This is close enough to have low latency (the time between when content requested and received) between Availability Zones. Regions are completely isolated.

## Edge locations
Site that **Amazon CloudFront** (a global content delivery service, that cache dynamic content and cant use S3 buckets as their origin server) uses to store cached copies of your content closer to your customers for faster delivery.

## Ways to interact with AWS services
**AWS Outposts:** Extend AWS infrastructure and services to your on-premises data center. Service that provides hybrid experience by facilitating running AWS services and infrastructure on premises.

### AWS management console
Web-based interface for accessing and managing AWS services. The console includes wizards and automated workflows that can simplify the process of completing tasks. A web-based user interface that helps users to access and manage aspects of AWS services.

You can also use the AWS Console mobile application to perform tasks such as monitoring resources, viewing alarms, and accessing billing information. Multiple identities can stay logged into the AWS Console mobile app at the same time.

### AWS command line interface
Enables you to control multiple AWS services directly from the command line within one tool. AWS CLI is available for users on Windows, macOS, and Linux.

By using AWS CLI, you can automate the actions that your services and applications perform through scripts. Also, SSH allows users to interact with AWS services through AWS CLI.

### Software development kits
SDKs make it easier for you to use AWS services through an API designed for your programming language or platform. SDKs enable you to use AWS services with your existing applications or create entirely new applications that will run on AWS.

## AWS Elastic Beanstalk
You provide code and configuration settings, and Elastic Beanstalk deploys the resources necessary to perform the following tasks: Adjust capacity, Load balancing, Automatic scaling, Application health monitoring. A service for deploying and scaling web applications and services. For deploying and scaling webapps. 

### AWS CloudFormation
You can treat your infrastructure as code. This means that you can build an environment by writing lines of code. AWS CloudFormation provisions your resources in a safe, repeatable manner, enabling you to frequently build your infrastructure and applications without having to perform manual actions or write custom scripts.

## Other Services
**Global accelerator:** Improves performance and availability. It doesn’t include content caching capability and is for apps that are not HTTP.

**Resource access manager:** Allows to share resources between multiple AWS accounts.

**Service Catalog:** Ideal for organizing, distributing, and provisioning application stacks on AWS. Uses AWS IAM & AWS CloudFormation to create a portfolio of products.