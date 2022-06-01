# AWS Databricks Cloud Architecture and System Integration Fundamentals

- While the Databricks Unified Analytics Platform provides a broad range of functionality to many members of data teams, it is through integrations with other services that most cloud-native applications will achieve results desired by customers.

## Goals

- [ ] Describe use cases for Databricks in an enterprise cloud architecture
- [ ] Configure secure connections from Databricks to data in S3
- [ ] Configure connections between Databricks and various first-party tools in an enterprise cloud architecture,  including Redshift and Kinesis
- [ ] Deploy an MLflow model to a Sagemaker endpoint for serving online model predictions
- [ ] Configure Glue as an enterprise data catalog

## Data Integration

- S3
  - Store processed results
  - Primary location
  - Use DeltaLake with parquet for ACID-compliance
- Kinesis
  - Streaming
  - Near-real-time
  - Also supports Kafka
- Glue
  - Option for enterprise-level data catalogue
  - Metastore
  - Share registered entities across environment
  - Query from Athena
- Redshift
  - Results for analytics processing
- RDS
  - Can add results
- DynamoDB
  - Low-latency row-level Access
- ML Flow
- SageMaker
  - Serve models at the edge
  - Image into ECR
  - Unpack model, configure, and deploy
  - Fast API results
- Athena
  - Powered by glue
- S3 Glacier
  - Cold storage from S3
- Databricks - cloud-native platform

## Accessing Data Securely

- IAM permissions for clusters to access resources
- Create cluster in Databricks
- Attach instance profile
  - Read-only permissions to certain S3 bucket
- Databricks documentation has walkthroughs for every integration
- Use cluster-mounted IAM roles
- Mount s3 Bucket
- 