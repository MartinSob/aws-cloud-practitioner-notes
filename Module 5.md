# Module 5: Storage & Database
## Instance stores
Block-level storage volumes behave like physical hard drives. An instance store provides temporary block-level storage for an Amazon EC2 instance. An instance store is disk storage that is physically attached to the host computer for an EC2 instance, and therefore has the same lifespan as the instance. When the instance is terminated, you lose any data in the instance store.

**Amazon Elastic Block Store (Amazon EBS)** is a service that provides block-level storage volumes. If you stop or terminate an Amazon EC2 instance, all the data on the attached EBS volume remains available.

To create an EBS volume, you define the configuration (such as volume size and type) and provision it. After you create an EBS volume. Because EBS volumes are for data that needs to persist, it’s important to back up the data. You can take incremental backups of EBS volumes by creating Amazon EBS snapshots. It is replicated in the same Availability Zone.

### Amazon EBS snapshots
An EBS snapshot is an incremental backup. This means that the first backup taken of a volume copies all the data. For subsequent backups, only the blocks of data that have changed since the most recent snapshot are saved. In full backups, all the data in a storage volume copies each time a backup occurs. Store snapshots on S3 can help reduce costs. Responsibility of the customer.

Data is not saved in backups outside a region unless you configure it that way. EBS snapshots are customer’s responsibility.

## Object storage
In object storage, each object consists of data, metadata, and a key.
- The data might be an image, video, text document, or any other type of file. 
- Metadata contains information about what the data is, how it is used, the object size, and so on. Instance metadata is the defined parameters and attributes specified in instance configuration. User data is information that is passed to the instance’s operating system to automatically execute during boot time.
- An object’s key is its unique identifier.

## Amazon Simple Storage Service (Amazon S3)
A service that provides object-level storage. Amazon S3 stores data as objects in buckets. Amazon S3 offers unlimited storage space. The maximum file size for an object in Amazon S3 is 5 TB (*Virtually unlimited storage*).

When you upload a file to Amazon S3, you can set permissions to control visibility and access to it. You can also use the Amazon S3 versioning feature to track changes to your objects over time. Lifecycle transition requests (GET/PUT) are paid, but the number of buckets do not add cost.

By default, a user can only access resources they created. S3 supports both server-side and client-side encryptions.

### Amazon S3 storage classes
With Amazon S3, you pay only for what you use. You can choose from a range of storage classes to select a fit for your business and cost needs. When selecting an Amazon S3 storage class, consider these two factors: How often you plan to retrieve your data & How available you need your data to be.
- **S3 Standard:** Provides high availability for objects. Has a higher cost than other storage classes intended for infrequently accessed data and archival storage. Stores data in a minimum of three Availability Zones. Object versioning and lifecycle policies (obj transition to other storage class after time).
- **S3 Standard-Infrequent Access (S3 Standard-IA):** Ideal for infrequently accessed data. Similar to S3 Standard but has a lower storage price and higher retrieval price. Stores data in a minimum of three Availability Zones.
- **S3 One Zone-Infrequent Access (S3 One Zone-IA):** Stores data in a single Availability Zone
- **S3 Intelligent-Tiering:** Ideal for data with unknown or changing access patterns. Requires a small monthly monitoring and automation fee per object. If you haven’t accessed an object for 30 consecutive days, Amazon S3 automatically moves it to the infrequent access tier, S3 Standard-IA. If you access an object in the infrequent access tier, Amazon S3 automatically moves it to the frequent access tier, S3 Standard.
- **S3 Glacier:** Low-cost storage designed for data archiving. Able to retrieve objects within a few minutes to hours
- **S3 Glacier Deep Archive:** Lowest-cost object storage class ideal for archiving. Able to retrieve within 12 hours

## Athena
Is a serverless query service used to analyze BigData stored in S3. It queries data directly from Amazon S3 and there are no additional data storage commitments beyond the object storage. It is compatible with data formats such as CSV, JSON, ORC, AVRO and Parquet.

## File storage
In file storage, multiple clients can access data that is stored in shared file folders. In this approach, a storage server uses block storage with a local file system to organize files. Clients access data through file paths.

Compared to block storage and object storage, file storage is ideal for use cases in which a large number of services and resources need to access the same data at the same time.

**Amazon Elastic File System (Amazon EFS)** is a serverless scalable file system used with AWS Cloud services and on-premises resources. As you add and remove files, Amazon EFS grows and shrinks automatically. It can scale on demand without disrupting applications. Stores data *across multiple Availability Zone*. Up to petabytes. You can also share files between thousands of Amazon EC2 instances and on-premises servers via AWS Direct Connect or AWS VPN. *Regional offering*.

## Relational databases
In a relational database, data is stored in a way that relates it to other pieces of data. Relational databases use structured query language (SQL) to store and query data. This approach allows data to be stored in an easily understandable, consistent, and scalable way.

### Amazon Relational Database Service
A service that enables you to run relational databases in the AWS Cloud. Amazon RDS is a managed service that automates tasks such as hardware provisioning, database setup, patching, and backups. Many Amazon RDS database engines offer encryption at rest (protecting data while it is stored) and encryption in transit (protecting data while it is being sent and received). User can restrict access with security group & can plan for backup and recovery strategies. Multi AZ. You can reduce the load on your source DB Instance by routing read queries from your applications to the *read replica*.

AWS Multiple Availability Zone deployments allows for AWS to failover to a secondary database in case the primary one fails.

### Amazon Aurora
An enterprise-class relational database. It is faster than standard MySQL and PostgreSQL databases. Amazon Aurora helps to reduce your database costs by reducing unnecessary input/output (I/O) operations, while ensuring that your database resources remain reliable and available. Can auto-scale up to 128 TB.

Consider Amazon Aurora if your workloads require high availability. It replicates six copies of your data across three Availability Zones and continuously backs up your data to Amazon S3.

## Nonrelational databases
Place to create tables, where you can store and query data. Nonrelational databases are sometimes referred to as “NoSQL databases” because they use structures other than rows and columns to organize data. One type of structural approach is key-value pairs, where data is organized into items (keys), and items have attributes (values).

In a key-value database, you can add or remove attributes from items in the table at any time. Additionally, not every item in the table has to have the same attributes.

### Amazon DynamoDB
A key-value database service. It delivers single-digit millisecond performance at any scale. Is serverless, so you don’t have to provision, manage, install nor maintain any servers. DynamoDB automatically scales to adjust for changes in capacity while maintaining consistent performance. Dynamo DB chooses Performance over Consistency while delivering reads (“Eventually consistent”).

### Amazon Redshift
A data warehousing service that you can use for big data analytics. It offers the ability to collect data from many sources and helps you to understand relationships and trends across your data. Leader node: Receive queries and manage client connections.

## AWS Database Migration Service (AWS DMS)
Enables you to migrate relational databases, nonrelational databases, and other types of data stores.

With AWS DMS, you move data between a source database and a target database that can be of the same type or different types. During the migration, your source database remains operational, reducing downtime for any applications that rely on the database. Uses *AWS Schema Conversion tool* for heterogeneous database migrations where source database & destination database is different.

## Additional database services
- **DocumentDB:** Document database service that supports MongoDB workloads.
- **Neptune:** A graph database service. You can use Amazon Neptune to build and run applications that work with highly connected datasets
- **Quantum Ledger Database (Amazon QLDB):** Ledger database service. You can use it to review a complete history of all the changes that have been made to your application data.
- **Managed Blockchain:** A service that you can use to create and manage blockchain networks with open-source frameworks. Blockchain is a distributed ledger system that lets multiple parties run transactions and share data without a central authority.
- **ElastiCache:** A service that adds caching layers on top of your databases to help improve the read times of common requests.
- **DynamoDB Accelerator:** Is an in-memory cache for DynamoDB. It helps improve response times.

## Other services
**EMR:** is a cloud big data platform for processing vast amounts of data using open-source tools.
