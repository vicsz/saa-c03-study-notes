## COMPUTE

### AWS EC2 
Amazon EC2 offers a scalable environment in AWS to launch virtual servers, configure security and networking, and manage storage. EC2 provides various options for flexibility, efficiency, and cost-effectiveness in cloud computing needs.

#### Features
- **AMI / AMI Builder**: Facilitates creating, configuring, and managing Amazon Machine Images (AMIs), which are templates used to launch new EC2 instances efficiently.
- **Instance Storage**: Delivers high-performance, temporary, non-persistent local storage directly attached to an instance. Ideal for temporary data processing.
- **EFS/EBS Connectivity**: Allows instances to connect to Amazon Elastic File System (EFS) for scalable file storage and Amazon Elastic Block Store (EBS) for block storage.
- **Launch Templates over Launch Configurations**: Modern method for launching instances, offering broader functionality and flexibility compared to the older Launch Configurations.
- **Hibernating EC2 Instances**: Enables instances to pause operations and save the in-memory state to EBS, allowing for quick resumption without data loss.

#### Cost Options
- **On-Demand Instances**: Best for short-term, irregular workloads without any upfront payment.
- **On-Demand Capacity Reservations**: Offers guaranteed capacity in a specific AWS region and Availability Zone with flexibility and without long-term commitments.
- **Reserved Instances**: Provides a significant discount over On-Demand pricing for a commitment to use EC2 over a one or three-year term.
- **Spot Instances**: Allows users to take advantage of unused EC2 capacity at a substantial discount but with the possibility of instances being interrupted.
- **Savings Plans**: Offers lower prices in exchange for a commitment to a consistent amount of usage over a one or three-year period.
- **Compute Savings Plans and EC2 Instance Savings Plans**: Provide flexible pricing options for consistent usage across instance families or specific to instance families in a region.
- **Defined Duration Spot Instances**: Temporary spot capacity with set durations.
- **Dedicated Hosts and Dedicated Instances**: Cater to specific needs requiring dedicated physical servers, such as compliance requirements or software licenses.

#### Network Options
- **ENI (Elastic Network Interface)**: Standard network interface for EC2 instances.
- **EFI (Enhanced Networking)**: Provides higher performance networking capabilities for demanding applications.
- **EFA (Elastic Fabric Adapter)**: Optimized for high-performance computing (HPC) and machine learning workloads, offering low-latency, high-bandwidth connections.

#### Placement Groups
- **Cluster**: Positions instances close to each other inside an Availability Zone to benefit from low network latency and high throughput.
- **Spread**: Distributes instances across different hardware to minimize correlated failures.
- **Partition**: Segregates instances into logical partitions, suitable for large distributed and replicated workloads across many instances.

#### Scaling Considerations
- **Autoscaling**: Dynamically adjusts EC2 capacity according to predefined conditions to maintain application performance.
- **Scaling Options**: Includes manual scaling, predictive scaling based on machine learning, scheduled scaling for known event times, and automatic scaling.
- **Normal vs Step-Scaling**: Distinguishes between gradual scaling (normal) and more responsive scaling (step) to handle sudden changes in workload.
- **Lifecycle Hooks**: Offers the ability to perform custom actions by pausing instances as Auto Scaling launches or terminates them.
- **Cooldown Periods**: Prevents the scaling process from launching or terminating additional instances before the previous scaling activity takes effect.
- **AWS Recommendations**: Suggests using target tracking scaling as the most straightforward and effective method to scale automatically.

#### Performance Considerations
- Utilizing placement groups for applications that benefit from low latency and/or high throughput.
- Choosing the correct instance type based on the workload requirements to optimize performance.
- Selecting the right network option, such as EFA for HPC, to enhance networking performance.

#### Cost Considerations
- Matching the instance size and type to the workload to avoid over-provisioning.
- Implementing scaling policies to adjust the number of instances dynamically, ensuring you pay only for what you need.
- Utilizing additional monitoring metrics through CloudAgent installation to make informed decisions about scaling and instance types, further optimizing costs.

---

### AWS Lambda 
AWS Lambda is a serverless computing service that runs code in response to events, automatically managing the underlying compute resources. It enables running code for virtually any type of application or backend service with zero administration.

#### Features
- **AWS Lambda Pricing**: Charges are based on the number of requests served and the execution duration of the code.
- **Lambda Function URLs**: Direct invocation of Lambda functions via HTTPS endpoints.
- **Execution Limit**: Supports up to a 15-minute maximum execution time per request.
- **Runs in its own VPC**: Ensures security and isolation by running functions in a managed VPC by Lambda.

#### Concurrency Management
- **Provisioned Concurrency**: Pre-allocates a specified number of Lambda instances for immediate response to events.
- **Reserved Concurrency**: Guarantees a minimum number of Lambda instances are reserved exclusively for a function, ensuring its availability.

#### Performance Considerations
- **Cold Start Mitigation**: Utilize Lambda Layers for shared code and libraries, Provisioned Concurrency for pre-warmed functions, and SnapStart for Java functions to reduce initialization times.
- **Database Connections**: Employ RDS Proxy for efficient and scalable database connections, reducing the overhead of managing connections directly from Lambda functions.
- **Lambda@Edge**: Execute Lambda functions at AWS Edge locations to reduce latency by processing requests closer to the end user.

#### Cost Considerations
- Eligible for Compute Savings Plans, allowing for reduced costs through a commitment to a consistent level of compute usage.

#### Compute Supplemental Services
- **Fargate**: Provides a serverless compute engine for containers, eliminating the need to manage servers or clusters.
- **EKS**: Amazon Elastic Kubernetes Service is a managed service that makes it easy to run Kubernetes on AWS without needing to install and operate your own Kubernetes control plane.
- **ECS**: Amazon Elastic Container Service is a fully managed container orchestration service, providing an easy way to run and scale containerized applications on AWS.
- **Batch**: AWS Batch enables developers, scientists, and engineers to easily and efficiently run hundreds of thousands of batch computing jobs on AWS.
- **Glue**: A fully managed extract, transform, and load (ETL) service that makes it easy for customers to prepare and load their data for analytics.
- **Beanstalk**: AWS Elastic Beanstalk is an easy-to-use service for deploying and scaling web applications and services developed with Java, .NET, PHP, Node.js, Python, Ruby, Go, and Docker on familiar servers such as Apache, Nginx, Passenger, and IIS.

---

## STORAGE

### AWS S3
Amazon S3 is a key/value bucket store designed for storing large files with high durability without the need for traditional backups, providing the most cost-effective storage solution on AWS.

#### Features
- **S3 Storage Classes**: Includes S3 Standard, S3 Express One Zone, S3 Standard-Infrequent Access, S3 Glacier Instant Retrieval, S3 Glacier Flexible Retrieval, and S3 Glacier Deep Archive for diverse storage needs and access patterns.
- **S3 Select**: Allows retrieval of specific data from objects using SQL expressions, enhancing performance and reducing costs by minimizing the amount of data loaded and processed.
- **S3 Pre-signed URLs**: Generate temporary URLs for secure sharing or uploading of files without revealing bucket contents.
- **S3 Multipart Upload**: Enables large files to be uploaded in parts, improving transfer speeds and reliability.
- **S3 Transfer Acceleration**: Speeds up file transfers to and from S3 using Amazon CloudFront's globally distributed edge locations.
- **S3 Lifecycle Management**: Automates moving files between different storage classes and managing expiration of objects.
- **S3 Versioning**: Keeps multiple versions of an object in a bucket, protecting against unintended overwrites and deletions. It is disabled by default.
- **S3 CORS**: Enables web applications to request resources from a different domain.
- **S3 Encryption**: Offers methods for encrypting objects stored in S3, enhancing data security.
- **S3 Object Lock**: Allows users to store objects using a write-once-read-many (WORM) model with two modes: Governance and Compliance Mode, supporting legal holds and retention periods.
- **S3 Glacier**: A secure, durable, and low-cost storage class for data archiving and long-term backup.
- **MFA Delete**: Adds an additional layer of security by requiring MFA to delete objects.
- **Requester Pays**: Enables bucket owners to shift data transfer charges to requesters.
- **Amazon S3 Intelligent Tiering**: Automatically moves objects between different tiers based on access patterns.
- **S3 Object Lambda**: Allows adding custom code to S3 GET, HEAD, and LIST requests for processing data on retrieval.
- **AWS Athena**: Provides SQL querying of S3 data in place, ideal for analyzing data directly in S3.
- **CloudFront**: Can host static websites directly from S3 buckets.
- **S3 Storage Lens**: Offers insights into access patterns and identifies opportunities for cost optimization.
- **S3 Analytics**: Tools for analyzing storage access patterns, aiding in lifecycle policy decisions.
- **S3 Outposts**: Brings S3 to on-premises AWS Outposts environments for a consistent hybrid experience.

#### Cost Considerations
- **Intelligent Tiering**: Best for unpredictable file access patterns, automatically optimizing costs.
- **Lifecycle Management**: Transition objects to less expensive storage classes based on access patterns and retention policies to reduce costs.
- **CloudFront**: Reduces costs by minimizing S3 access charges.

#### Performance Considerations
- **Cross-Region Replication**: Enhances data availability and accessibility across geographies.
- **CloudFront**: Lowers latency by caching content closer to the end users.

#### Security Considerations
- **Encryption at Rest**: Offers several encryption options including SSE-S3 (AES-256), SSE-KMS (for key management control), and SSE-C (customer-provided keys).
- **Origin Access Identity (OAI)**: Restricts access to S3 content, ensuring it can only be accessed via CloudFront.

---

### AWS DynamoDB
Amazon DynamoDB is a NoSQL database service known for its key/value storage, millisecond latency, and high throughput capabilities, suitable for real-time applications. Backups are recommended to ensure data durability.

#### Features
- **DynamoDB Accelerator (DAX)**: In-memory caching for DynamoDB, reducing response times from milliseconds to microseconds.
- **DynamoDB Streams**: Captures item-level modifications in DynamoDB tables, enabling integration with other AWS services.
- **Read Types**: Supports eventually consistent and conditional writes for efficient data retrieval and management.
- **Queries vs Scans**: Queries retrieve data using the primary key attribute for efficient access, whereas Scans examine all items, which can be less efficient.
- **Time To Live (TTL)**: Automatically deletes items after a specified period, helping manage expirable data and reduce storage costs.
- **Global Tables**: Provides fully managed, multi-region, and multi-master database tables for global applications.
- **Capacity Models**: Offers Provisioned Throughput for predictable workloads and On-Demand for flexible scaling.
- **Point-in-Time Recovery (PITR)**: Enables recovery to any second in the last 35 days, enhancing data protection.

#### Cost Considerations
- Consider on-demand capacity for unpredictable workloads.
- Use provisioned capacity for predictable workloads with consistent throughput needs.

#### Performance Considerations
- Use DAX for caching frequently accessed items.
- Optimize query and scan operations to minimize response times and consumed capacity.

#### High Availability Considerations
- Utilize Global Tables for cross-region redundancy.

#### Backup Options
- **DynamoDB Backups**: Enable point-in-time recovery for continuous backups and restoration.
- **AWS Backup**: Centralized backup service that also supports DynamoDB for managing backups across AWS services.

---

#### AWS RDS
Amazon RDS is a managed relational database service that simplifies setting up, operating, and scaling a relational database in the cloud. It supports several database engines and combines the reliability of EBS-backed storage with the convenience of automated backups.

#### Features
- **Database Engines**: Supports MySQL, PostgreSQL, MariaDB, Oracle, and SQL Server.
- **Amazon RDS Custom for Oracle**: Provides access to underlying Oracle instance settings for advanced configuration.
- **Aurora**: An AWS-designed database that offers compatibility with MySQL and PostgreSQL, featuring serverless scaling, global distribution, and efficient cloning capabilities.
- **RDS Event Notification**: Alerts users about changes to the database infrastructure.
- **RDS Proxy**: Manages database connections, improving scalability and security.
- **Read Replicas and Multi-AZ Deployments**: Enhances database performance and availability.
- **Auto-scaling**: Automatically adjusts storage capacity based on demand.
- **Backup Options**: Includes automated backups, cross-region backups, snapshot backups, AWS Backups, and replication to a standby database for comprehensive data protection.

#### Cost Considerations
- Reserved Instance pricing for the database engine (CPU, RAM) can provide significant savings.
- Optimize storage costs by adjusting allocation and using auto-scaling.

#### Performance Considerations
- Add Read Replicas to distribute read traffic.
- Use RDS Proxy to manage connections efficiently.

#### High Availability Considerations
- Deploy Multi-AZ or Aurora Global Database for enhanced availability and data durability.

#### Backup Options
- **Automated Backups**: Provides a daily snapshot and captures transaction logs.
- **Snapshot Backups**: User-initiated snapshots of your database instance that are retained until explicitly deleted.
- **AWS Backup**: Offers a centralized solution for backing up RDS and other AWS services.
- **Cross-Region Automated Backups**: Automates the replication of snapshots and transaction logs across AWS regions.

---

#### AWS EBS

#### Overview
Amazon Elastic Block Store (EBS) provides block-level storage volumes for use with EC2 instances, offering high availability and durability. EBS volumes can be used as primary storage for databases or file systems and support backups through AWS Backup and the Data Lifecycle Manager.

#### Features
- **Single Instance Attachment**: Typically, an EBS volume can be attached to only one EC2 instance at a time.
- **Fast Snapshot Restore**: Enables quick recovery of EC2 instances by providing faster access to snapshot data.
- **EBS Data Lifecycle Manager**: Automates the creation, retention, and deletion of snapshots, separate from AWS Backup.
- **EBS Multi-Attach**: Allows an EBS volume to be attached to multiple EC2 instances within the same Availability Zone.

#### Cost Considerations
- Optimize costs by selecting the appropriate volume type and size for your workload.

#### Performance Considerations
- Choose the right EBS volume type (e.g., Provisioned IOPS) for your workload requirements.

#### Backup Options
- **EBS Snapshots**: Create point-in-time snapshots of EBS volumes.
- **AWS Backup**: Centralized backup service for EBS volumes and other AWS resources.

---

#### AWS EFS
Amazon Elastic File System (EFS) is a fully managed, scalable file storage solution for use with AWS Cloud services and on-premises resources. It supports NFS and automatically scales without needing to provision storage or throughput.

#### Features
- **Compatibility**: Works with Linux-based AMIs but not with Windows instances.
- **Multi-Instance Connectivity**: Unlike EBS, EFS can be mounted on multiple EC2 instances simultaneously.
- **Automatic Scaling**: EFS scales automatically with the amount of stored data, removing the need for manual capacity management.

#### Cost Considerations
- Utilize EFS Infrequent Access (EFS IA) with Lifecycle Management to reduce costs for rarely accessed files.

---

### Storage Supplemental Services
- **Redshift**: Data warehousing service for running massive scale analytics.
- **EMR**: Managed Hadoop framework for processing large data sets across dynamically scalable Amazon EC2 instances.
- **DocumentDB**: Compatible with MongoDB, designed for modern application development needs.
- **Neptune**: Managed graph database service for building and running applications that work with highly connected datasets.
- **LakeFormation**: Simplifies the process of building, securing, and managing data lakes.
- **Amazon MQ**: Managed message broker service for Apache ActiveMQ and RabbitMQ, ideal for migrating traditional applications to the cloud.
- **ElastiCache**: In-memory caching service, supporting Redis and Memcached, enhances the performance of web applications by allowing retrieval of data from fast, managed, in-memory caches.
- **TimeStream**: Time series database service for IoT and operational applications.
- **AWS Backup**: Centralized backup service across AWS services.
- **AWS Schema Conversion Tool**: Facilitates database migration projects by converting the source database schema and a majority of the custom code to a format compatible with the target database.

---

## APPLICATION INTEGRATION

### AWS SNS (Simple Notification Service)
Amazon SNS is an event-driven messaging service that follows the publish-subscribe (pub-sub) model, efficiently delivering messages using a push mechanism. It's designed for high-throughput, multi-subscriber messaging.

#### Features
- **Event-driven Computing**: Facilitates decoupled communication between producing and consuming services.
- **Pub-Sub Messaging**: Enables messages to be pushed to multiple subscribers, supporting a wide variety of communication patterns.
- **Message Fanout**: Allows a single message published to an SNS topic to be delivered to multiple subscribers, enabling parallel processing.
- **Reliability and Durability**: While SNS ensures message delivery to subscribers, it doesn't inherently guarantee message order or prevent duplicates, making it less suitable for applications requiring strict message sequencing or uniqueness.

---

### AWS SQS (Simple Queue Service)
Amazon SQS offers scalable message queuing services, supporting both standard and FIFO (First-In-First-Out) queues. It enables decoupled component interaction in distributed systems through a pull-based (polling) messaging mechanism.

#### Features
- **Standard vs. FIFO Queues**: Standard queues offer at-least-once delivery and best-effort ordering, while FIFO queues guarantee exactly-once processing and maintain order.
- **Pull-Based Messaging**: Consumers poll the queue for messages, allowing for controlled message processing.
- **VPC Integration**: SQS can be accessed within a VPC, ensuring secure and private message transactions.
- **Long Polling vs. Short Polling**: Controls how the queue is polled for messages, with long polling reducing the number of empty responses by allowing SQS to wait until a message is available.
- **Dead-letter Queues**: Help manage messages that can't be processed successfully, reducing the risk of losing messages.
- **Extended Client Library for Java**: Enables sending larger messages than the standard SQS size limit by storing message payloads in S3.
- **Visibility Timeout**: Ensures messages are not visible to other consumers after being polled, preventing duplicate processing.

---

### AWS EventBridge
AWS EventBridge is a serverless event bus that makes it easy to connect applications with data from a variety of sources. It is designed for event-driven architectures, offering a robust solution for routing events between AWS services, integrated SaaS applications, and custom applications.

#### Use Cases
- **Daily Triggers or AWS Events**: Ideal for applications requiring scheduled events or responding to AWS service actions rather than application-specific messages.
- **Application Integration**: Facilitates easy integration and decoupling of microservices, distributed systems, and serverless applications.

---

### AWS Kinesis
Amazon Kinesis makes it easy to collect, process, and analyze real-time, streaming data, allowing for timely insights and reactions.

#### Components
- **Kinesis Firehose**: Simplifies loading streaming data into AWS destinations such as S3, Redshift, Elasticsearch, etc. Best for straightforward data loading needs.
- **Kinesis Streams**: Offers more complex data processing capabilities, supporting detailed real-time analytics. Utilizes shards to manage data throughput and order.
- **Kinesis Analytics**: Enables real-time processing of streaming data, supporting filtering, aggregation, and transformation.

---

### Application Integration Supplemental Services

- **AppSync**: Allows for the creation of flexible, scalable applications on a GraphQL service that integrates data from multiple sources.
- **Step Functions**: Provides serverless orchestration for complex workflows, enabling applications to coordinate multiple AWS services into serverless workflows.
- **SWF (Simple Workflow Service)**: Deprecated in favor of Step Functions, which offer more advanced and flexible workflow orchestration capabilities.
- **AWS Data Pipeline**: Automates the movement and transformation of data. Unlike Kinesis, which is designed for real-time data processing, Data Pipeline is optimized for scheduled batch processing.

