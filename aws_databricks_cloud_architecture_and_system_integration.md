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
- With read only can mount and read, but not change
  - Usually the right level of permissions for most users

## AWS Integrations

### Streaming with Kinesis

- Subscribe to structured stream
- Parse JSON

### Redshift

- Install custom jar onto cluser
- Need drivers from Amazon

## MLFLow / Sagemaker

- [Set up AWS Authenticator for SageMaker](https://docs.databricks.com/administration-guide/cloud-configurations/aws/sagemaker.html)
- [x] [Pip instal MLflow](https://mlflow.org/docs/latest/quickstart.html#installing-mlflow)
- [x] [Install  AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
- [ ] [Configure AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html)
- [ ] [Grant User Access to ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/what-is-ecr.html)
- [ ] [Build and Push pyfunc Container](https://mlflow.org/docs/latest/cli.html#mlflow-sagemaker-build-and-push-container)


- Train and run
- Model deployed in Docker Image
- Deploy (~8 min)

## Glue and Athena

- Data catalogue to replace hive metastore
- Query DeltaLake files with Athena
- IAM role
- Spark configuration on cluster

