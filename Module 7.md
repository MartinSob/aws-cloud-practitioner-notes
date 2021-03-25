# Module 7: Monitoring and Analytics
## Amazon CloudWatch
Amazon CloudWatch is a web service that enables you to monitor and manage various metrics (CPU, RAM) and configure alarm actions based on data from those metrics. CloudWatch uses metrics to represent the data points for your resources in graphs.

### CloudWatch alarms
With CloudWatch, you can create alarms that automatically perform actions if the value of your metric has gone above or below a predefined threshold.

### CloudWatch dashboard
The CloudWatch dashboard feature enables you to access all the metrics for your resources from a single location.

## AWS CloudTrail
Records API calls for your account (and from other accounts). The recorded information includes the identity of the API caller, the time of the API call, the source IP address of the API caller, and more. Events are typically updated in CloudTrail within 15 minutes after an API call.

**CloudTrail Insights:** This optional feature allows CloudTrail to automatically detect unusual API activities in your AWS account.

## AWS Trusted Advisor
A web service that inspects your AWS environment and provides real-time recommendations in accordance with AWS best practices. The inspection includes security checks, such as Amazon S3 buckets with open access permissions.

Trusted Advisor compares its findings to AWS best practices in five categories: **cost optimization, performance, security, fault tolerance, and service limits**. For the checks in each category, Trusted Advisor offers a list of recommended actions and additional resources to learn more about AWS best practices.

**AWS Trusted Advisor Notification** is an optional service that needs to be set up from the dashboard.

### AWS Trusted Advisor dashboard
Where you can review completed checks for cost optimization, performance, security, fault tolerance, and service limits. For each category:
- Green 🡪 no problems
- Orange 🡪 recommended investigations
- Red 🡪 recommended actions.

**Penetration testing** can be performed by customers, provided they work with the list of services mentioned by AWS.

## Other services
**Change Sets:** Preview changes to resources when a stack is executed.

**Compute optimizer:** ML based tool that analyses metrics of historic utilization and makes recommendations of compute services.

**Config:** is a service that enables you to assess, audit, and evaluate the configurations of your AWS resources.

**Detective:** makes it easy to analyze, investigate, and quickly identify the root cause of potential security issues or suspicious activities. Uses machine learning.

**Disaster recovery techniques:** From highest to lowest highest downtime: Backup & Restore, Pilot light, Warm standby, Multi site.

**OpsWorks:** is a configuration management service that provides managed instances of Chef and Puppet. Chef and Puppet are automation platforms that allow you to use code to automate the configurations of your servers. These platforms will allow for the use of code to automate the configurations of EC2 instances. Mainly used for Linux and public endpoints.

**Quick Sight:** Graphic reports. Scalable, serverless, embeddable, machine learning-powered business intelligence (BI) service that lets you create BI dashboards.

**Service health dashboard:** most up-to-the-minute information on AWS service availability here.

**Well-Architected tool:** Provides advice on architecting the workload in the cloud.