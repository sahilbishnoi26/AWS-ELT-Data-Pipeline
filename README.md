# AWS Data Pipeline for Structured Data Processing

## Overview
This project demonstrates an end-to-end data pipeline using AWS services to process structured data efficiently. The pipeline extracts data from S3, transforms it using AWS Glue, stores results in an Athena-accessible format, and visualizes insights in QuickSight. Lambda functions automate workflow execution.

![alt text](https://github.com/sahilbishnoi26/AWS-ELT-Data-Pipeline/blob/main/data/img0.png)

## Architecture
1. **Data Source:** Raw structured data stored in AWS S3.
2. **AWS Glue Crawler:** Identifies schema and creates metadata in the AWS Glue Data Catalog.
![alt text](https://github.com/sahilbishnoi26/AWS-ELT-Data-Pipeline/blob/main/data/img1.png)
3. **AWS Lambda:** Transformed json file into format that can be parsed by Glue crawler to create a strutured table that can be queried by Athena.
![alt text](https://github.com/sahilbishnoi26/AWS-ELT-Data-Pipeline/blob/main/data/img2.png)
![alt text](https://github.com/sahilbishnoi26/AWS-ELT-Data-Pipeline/blob/main/data/img3.png)
5. **AWS Glue ETL Job:** Processes raw data, applies transformations, and stores results in S3 in a queryable format (e.g., Parquet).
6. **AWS Athena:** Runs SQL queries on processed data using Glue Catalog as a metadata store.
7. **AWS QuickSight:** Provides data visualization and reporting.

## Setup Instructions
### Prerequisites
- AWS account with access to S3, Glue, Athena, Lambda, and QuickSight.
- IAM roles with necessary permissions for Glue, Lambda, and S3 access.

### Deployment Steps
1. **Upload Data to S3:**
   - Store raw data in an S3 bucket.

2. **Create Glue Crawler:**
   - Define a crawler to infer the schema and populate the Glue Data Catalog.
   
3. **Develop and Run Glue ETL Job:**
   - Use AWS Glue Studio or a Python script to process data.
   - Output transformed data to an S3 location in Parquet format.

4. **Query Data with Athena:**
   - Create an Athena table using Glue Catalog metadata.
   - Execute SQL queries to analyze the transformed data.

5. **Automate with Lambda:**
   - Create a Lambda function to trigger Glue jobs on a schedule or event.
   - Use CloudWatch to monitor and log executions.

6. **Visualize with QuickSight:**
   - Connect QuickSight to Athena.
   - Build dashboards for insights and reporting.

## Key Features
- **Serverless Data Processing:** Uses AWS Glue for ETL without infrastructure management.
- **Cost-Efficient Querying:** Leverages Athena for pay-per-query analysis.
- **Scalability:** Handles large datasets with AWS-managed services.
- **Automation:** Lambda functions streamline job execution.
- **Visualization:** QuickSight provides interactive analytics.

## Usage
- Perform automated ETL processing on structured data.
- Run SQL queries on transformed data via Athena.
- Generate real-time dashboards in QuickSight.
- Extend the pipeline with additional AWS services as needed.



