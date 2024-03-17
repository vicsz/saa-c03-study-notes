## COMPUTE

### EC2 Overview
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

### Lambda Overview
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

#### Supplemental Services
- **Fargate**: Provides a serverless compute engine for containers, eliminating the need to manage servers or clusters.
- **EKS**: Amazon Elastic Kubernetes Service is a managed service that makes it easy to run Kubernetes on AWS without needing to install and operate your own Kubernetes control plane.
- **ECS**: Amazon Elastic Container Service is a fully managed container orchestration service, providing an easy way to run and scale containerized applications on AWS.
- **Batch**: AWS Batch enables developers, scientists, and engineers to easily and efficiently run hundreds of thousands of batch computing jobs on AWS.
- **Glue**: A fully managed extract, transform, and load (ETL) service that makes it easy for customers to prepare and load their data for analytics.
- **Beanstalk**: AWS Elastic Beanstalk is an easy-to-use service for deploying and scaling web applications and services developed with Java, .NET, PHP, Node.js, Python, Ruby, Go, and Docker on familiar servers such as Apache, Nginx, Passenger, and IIS.
