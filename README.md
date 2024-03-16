# AWS Certified Solutions Architect (SAA-C03) Study Notes: S3

## Overview

- **Amazon S3** is a highly durable, object storage service designed for storing large, unstructured data sets like files.
- Use cases include serving website static assets, content storage, and backup.
- It is the cheapest storage option compared to AWS services like EFS, EBS, RDS, and DynamoDB.
- Pricing is based on storage used, requests made, and data transferred.

## Use Cases and Features

### AWS Athena
- **Use case:** Ad-hoc querying of S3 data.
- **Feature:** Works directly on data stored in S3.

### S3 Select
- **Use case:** Reduces data transfer costs by retrieving only a subset of data from an object.
- **Data types:** Works on CSV, JSON, and Parquet.

### S3 Pre-signed URLs
- **Use case:** Securely share private files temporarily.

### S3 Multipart Upload
- **Use case:** Consider for files over 100 MB; required for files over 5 GB.

### S3 Transfer Acceleration
- **Use case:** Speeds up file transfers to and from S3 globally.

### Cross-Region Replication
- **Use case:** Synchronizes data across regions for disaster recovery.

### S3 Lifecycle Management
- **Use case:** Automatically manage objects' lifecycle to reduce costs.

### Glacier
- **Use case:** Long-term archival storage.

### S3 Cost
- **Cost order:** Standard > Infrequently Accessed > Glacier.

### S3 Versioning
- **Feature:** Disabled by default; maintains multiple versions of an object.

### S3 CORS
- **Use case:** Allows resources in one domain to request resources from another domain.

### S3 Encryption
- **Feature:** Protects data at rest.

### MFA Delete
- **Feature:** Enhances security by requiring MFA for deletion.

### Requester Pays
- **Feature:** Option for requester to bear the cost of data download.

### Amazon S3 Intelligent Tiering
- **Feature:** Automatically moves objects between tiers without manual intervention.

### CloudFront and S3
- **Use case:** Cost-efficient hosting of static websites with high durability.

### Origin Access Identity (OAI)
- **Use case:** Restricts bucket access, ensuring only designated CloudFront distributions can access.

### S3 Event Notifications
- **Feature:** Triggers actions in response to changes.

### S3 Object Lambda
- **Use case:** Modify and process data on-the-fly during retrieval.

### S3 Storage Lens
- **Feature:** Provides analytics to manage storage efficiently.

### S3 Batch Operations
- **Use case:** Perform large-scale operations across objects.

## S3 Object Lock

- **Use case:** Immutable storage; prevents object deletion.
- **Modes:** Governance, Compliance.
- **Features:** Retention Period, Legal Hold.

## Encryption

- **SSE-S3:** Automatic key rotation managed by AWS.
- **SSE-KMS:** Provides control over key rotation.
- **SSE-C:** Customer-managed keys without automatic rotation.

## Cost Optimization

- **Unpredictable usage:** Use Intelligent Tiering.
- **Known usage patterns:** Apply Lifecycle Management policies for cost savings.
- **Storage tiers by cost:** Standard > Infrequently Accessed > Glacier.
- **Cross-Region Replication** can optimize costs between regions.
- **CloudFront:** Reduces costs by caching content at edge locations.

## Performance Optimization

- **Tier performance order:** Standard > Infrequently Accessed > Glacier.
- **S3 Transfer Acceleration:** Use for faster uploads/downloads.
- **CloudFront:** Improves content delivery speed.

## Backup

- **Use case:** S3 can store backups for RDS, EBS snapshots cheaply.
- **Note:** Direct backup of S3 itself is not typically required.
