# AWS Serverless Image Processing & Database Integration

This project demonstrates a robust cloud architecture using **AWS Serverless** technologies. It combines event-driven image processing with a highly scalable database layer using **Amazon Aurora Serverless**.

## 🚀 Architecture Overview

The system is designed to handle automated workflows without managing physical servers:
1.  **Storage layer:** Images are uploaded to an **Amazon S3** source bucket.
2.  **Compute Layer:** An **AWS Lambda** function is triggered by S3 events.
3.  **Database Layer:** An **Amazon Aurora (MySQL/PostgreSQL) Serverless V2** instance manages the data backend, providing high availability and auto-scaling capabilities.

## 🛠 Tech Stack

* **Cloud Provider:** Amazon Web Services (AWS)
* **Compute:** AWS Lambda (Python 3.x)
* **Database:** Amazon Aurora Serverless V2
* **Storage:** Amazon S3
* **Security:** AWS IAM (Identity and Access Management)
* **Monitoring:** Amazon CloudWatch

## 📌 Key Features

-   **Event-Driven Workflow:** Automatic triggering of functions upon file uploads.
-   **Automated Scaling:** Database capacity adjusts dynamically based on the application's needs.
-   **Serverless Efficiency:** Cost-effective execution with zero idle time maintenance.
-   **Fine-Grained Permissions:** Secure resource access using custom IAM roles (e.g., `lambda-s3-resizer-role`).

## 📸 Project Evidence


Below is a snapshot of the successfully provisioned **Aurora Serverless Cluster**:

![Database Screenshot](file:///C:/Users/M%20S%20I/Pictures/project/Screenshot%202026-04-20%20112619.png)

> *Note: This screenshot confirms the successful creation and 'Available' status of the database-1 instance.*

## 📜 Lambda Function Logic (Sneak Peek)

The core logic uses the `boto3` library to handle object events:

```python
import boto3

def lambda_handler(event, context):
    # Logic to process S3 event and interact with database/target bucket
    print("Processing event...")
