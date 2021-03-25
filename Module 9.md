# Module 9: Migration and innovation
## Six core perspectives of the Cloud Adoption Framework
Organizes guidance into six areas of focus, called Perspectives. Each Perspective addresses distinct responsibilities.
1. **Business:** Ensures that IT aligns with business needs.
1. **People:** Evaluate organizational structures and roles and process requirements. This helps prioritize training and staffing.
1. **Governance:** To understand how to update the staff skills and processes to ensure business governance in the cloud.
1. **Platform:** Includes principles and patterns for implementing new solutions on the cloud and migrating on-premises workloads to the cloud.
1. **Security:** Ensures that the organization meets security objectives for visibility, auditability, control, and agility.
1. **Operations:** Align with and support the operations of the business.

## Six strategies for migration
1. **Rehosting:** Involves moving applications without changes to another host.
1. **Replatforming:** involves making a few cloud optimizations to realize a tangible benefit.
1. **Refactoring:** involves reimagining how an application is architected and developed by using cloud-native features.
1. **Repurchasing:** involves moving from a traditional license to a software-as-a-service model.
1. **Retaining:** consists of keeping applications that are critical for the business in the source environment.
1. **Retiring:** process of removing applications that are no longer needed.

## AWS Snow Family members
It is a collection of physical devices that help to physically transport data into and out of AWS.
- **AWS Snowcone** is a small, rugged, and secure edge computing and data transfer device. 
    - It features 2 CPUs, 4 GB of memory, and 8 TB of usable storage.
- **AWS Snowball**
    - **Snowball Edge Storage Optimized** devices are well suited for large-scale data migrations. 
        - Storage: 80 TB - 1 TB 
        - Compute: 40 vCPUs, and 80 GiB of memory.
    - **Snowball Edge Compute Optimized** provides powerful computing resources. 
        - Storage: 42-TB - 7.68 TB 
        - Compute: 52 vCPUs, 208 GiB of memory, and an optional NVIDIA Tesla V100 GPU.
- **AWS Snowmobile** is a data transfer service used to move large amounts of data to AWS. Up to 100 petabytes.

## Innovation
**Serverless applications:** Refers to applications that don’t require you to provision, maintain, or administer servers. You don’t need to worry about fault tolerance or availability.

**Artificial intelligence:**
 - *Amazon Transcribe:* Convert speech to text
 - *Amazon Comprehend:* Discover patterns in text
 - *Amazon Fraud Detector:* Identify potentially fraudulent online activities
 - *Amazon Lex:* Build voice and text chatbots
 - *Amazon Augmented AI:* provides built-in human review workflows for common machine learning use cases.

**Machine learning:** AWS offers **Amazon SageMaker** to remove the difficult work from the process and empower you to build, train, and deploy ML models quickly.

**Macie:** Fully managed service that provides data security and privacy using machine learning algorithms. For S3. Can be used to detect users' personal credit card numbers from data stored in Amazon S3. Discover, Classify, Protect.

**Amazon Textract:** A fully managed machine learning service that automatically extracts printed text, handwriting, and other data from scanned documents

## Other services
**DataSync:** To move huge amounts of data (hundreds of terabytes) between on-prem storage to S3, EFS, FSx. Can work over AWS Direct Connect or not. It is not an agentless data transfer service. 