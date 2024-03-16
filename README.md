## Compute

### EC2 (Amazon Elastic Compute Cloud)
- **Features:**
  - **Instance Types:** Variety optimized for various use cases such as general purpose, compute, memory, storage, accelerated computing.
  - **Purchasing Options:** On-Demand, Reserved Instances, Spot Instances, Savings Plans, Dedicated Hosts, Dedicated Instances.
  - **Elastic Load Balancing:** Automatically distributes incoming traffic across multiple EC2 instances.
  - **Auto Scaling:** Dynamically adjusts EC2 capacity according to conditions.
  - **Launch Configurations and Templates:** Templates specify instance configuration settings; Launch Configurations are deprecated in favor of Templates.
  - **Placement Groups:** Options include Cluster (low-latency, high-throughput), Spread (isolated instances), and Partition (multiple partitions for large distributed applications).
  - **EBS Integration:** Attach persistent storage volumes to instances.
  - **Networking:** Supports multiple network interfaces, private IP addresses, and Elastic IPs.
  - **Security:** Utilize security groups and network ACLs for access control.
  - **Backups:** EBS volumes can be snapshotted for backups, featuring EBS fast snapshot restore for quicker recovery.
- **Storage Options:**
  - **Instance Store:** Temporary, block-level storage for an instance. Most cost-effective but data is lost if the instance is stopped or terminated.
  - **EBS (Elastic Block Store):** Persistent storage volume for data retention, attachable to one instance at a time.
  - **EFS (Elastic File System):** Scalable file storage for use with multiple EC2 instances.
- **Cost Optimization Tips:**
  - **Reserved Instances:** Commit to EC2 capacity for a term to receive a lower rate compared to On-Demand.
  - **Spot Instances:** Request unused EC2 capacity at steep discounts. Suitable for flexible, fault-tolerant applications.
  - **Savings Plans:** Offers significant savings over On-Demand in exchange for a commitment to a consistent amount of usage (compute or EC2 instance) for a 1 or 3-year period.
  - **EC2 Instance Savings Plans:** Specifically for EC2 instances, allowing savings while retaining flexibility to change instance families, OS, and tenancy.
  - **Compute Savings Plans:** Broadly applicable across EC2, Fargate, and Lambda, providing flexibility and savings.
  - **Dedicated Hosts:** Ideal for using existing server-bound software licenses or regulatory requirements that forbid multi-tenant hosting.
  - **Dedicated Instances:** Physically isolated at the hardware level from instances that belong to other AWS accounts.
- **Performance Optimization Tips:**
  - **Enhanced Networking:** Utilize for higher performance (more PPS, lower latency).
  - **EBS-Optimized Instances:** Provides dedicated bandwidth to EBS volumes.
  - **Placement Groups:** Choose based on the specific needs of your application for performance optimization.

### Lambda (AWS Lambda)
- **Features:**
  - **Serverless Execution:** Automatically manages the computing resources.
  - **Event-driven:** Runs code in response to triggers such as changes in data, system state, or actions by users.
  - **Scaling:** Automatically scales with the size of the workload.
  - **Runtime Support:** Wide range of programming languages supported.
  - **Stateless:** Each function execution is independent with no affinity to the underlying infrastructure.
  - **Execution Time Limit:** Max duration for a Lambda function execution is 15 minutes.
  - **Direct URL Access:** As of 2021, Lambda functions can be invoked directly via HTTPS requests without needing an API Gateway.
  - **Lambda Layers:** Reuse shared components across multiple Lambda functions.
  - **Lambda@Edge:** Run Lambda functions at AWS Edge locations for improved latency.
  - **SnapStart:** Reduces cold start times for Java functions.
- **Cost Optimization Tips:**
  - **Provisioned Concurrency:** Minimize latency for predictable workloads.
  - **Memory Size Optimization:** Adjust function's memory size for cost efficiency without compromising on performance.
- **Performance Optimization Tips:**
  - **Reduce Cold Starts:** Utilize SnapStart (for Java functions), keep functions warm, and optimize initialization code.
  - **Use Lambda Layers:** For sharing common components between functions, reducing deployment package size and possibly cold start time.
  - **RDS Proxy:** For Lambda functions accessing RDS, use RDS Proxy to manage connections efficiently, improving performance.
  - **Running Lambda@Edge:** For applications needing lower latency by running code closer to users' locations.

### Computer - Supplemental Services

#### ECS, EKS, Fargate
- **Key for container management and orchestration.** Understand the distinctions among these services in terms of container management. ECS (Elastic Container Service) and EKS (Elastic Kubernetes Service) provide comprehensive solutions for container orchestration, with ECS being AWS-native and EKS for those preferring Kubernetes. Fargate offers a serverless container execution environment, removing the need to manage servers or clusters.
- **For those looking for the least overhead in container support,** Fargate is the likely solution, offering a simplified operational model by abstracting the server and cluster management aspect.

#### Elastic Beanstalk
- **Simplifies deploying applications** by handling various provisioning and management tasks such as load balancing, auto-scaling, and application health monitoring. It's an ideal choice for developers who want to deploy their applications without delving into the underlying infrastructure details.

#### Batch
- **Essential for efficiently running batch computing jobs** on AWS, capable of managing hundreds to thousands of jobs. This service automates job scheduling, making it easier to run large-scale batch processes.

### Compute - Exam Preparation Tips

- **Focus on EC2's detailed options for cost and performance optimization.** Placement groups and their specific use cases are critical to understand for performance-sensitive applications.
- **Lambda's pricing model** is influenced by the number of requests and the duration of code execution. Optimizing Lambda functions to minimize cold starts and leveraging RDS Proxy for efficient database interactions are key strategies for enhancing performance.
- **For supplemental services like ECS, EKS, and Fargate,** it's crucial to grasp their primary use cases. Understanding container orchestration and the scenarios where serverless computing with Fargate reduces overhead can be beneficial.
- **Real-world applications** often combine these compute services to address complex architectural challenges efficiently and cost-effectively. Recognizing when and how to integrate these services is essential for designing optimal AWS solutions.
