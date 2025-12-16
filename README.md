# AWS Face Recognition System (Serverless)

### A serverless face recognition project built using Amazon Rekognition, S3, AWS Lambda, DynamoDB, IAM, and CloudWatch. The system automatically detects and indexes faces when images are uploaded to S3, stores face metadata in DynamoDB, and logs all activity via CloudWatch.

## 🏗️ Architecture Overview
![img](https://github.com/riyaj-2002/Facial-Recognition-System/blob/51e21b1d24241b3829e15300454a868c9f1d3723/architect%20flow.png)


## 🛠️ AWS Services Used
![img](https://github.com/riyaj-2002/Facial-Recognition-System/blob/51e21b1d24241b3829e15300454a868c9f1d3723/aws%20services.png)

## 🔧 Step-by-Step: AWS Face Recognition Project

###  1. Create S3 Bucket 
#### Purpose: Store images that will be processed
![img](https://github.com/riyaj-2002/Facial-Recognition-System/blob/51e21b1d24241b3829e15300454a868c9f1d3723/S3%20bucket.png)

#### 📌 This bucket will trigger Lambda when an image is uploaded.

###  2. Create Rekognition Face Collection

#### Purpose: Store indexed faces
```bash
aws rekognition create-collection --collection-id employees --region us-east-1
```

#### 📌 Rekognition uses this collection to store and compare faces.

###  3. Create IAM Role for Lambda
#### Purpose: Allow Lambda to access AWS services
![img](https://github.com/riyaj-2002/Facial-Recognition-System/blob/51e21b1d24241b3829e15300454a868c9f1d3723/IAM%20role.png)

###  4. Create Lambda Function

#### Purpose: Add Lambda Code
![img](https://github.com/riyaj-2002/Facial-Recognition-System/blob/51e21b1d24241b3829e15300454a868c9f1d3723/lambda.png)

#### 📌Detect and index faces

###  5. Create DynamoDB Table

#### Purpose: Store face metadata
![img](https://github.com/riyaj-2002/Facial-Recognition-System/blob/51e21b1d24241b3829e15300454a868c9f1d3723/dynamoDB.png)

#### 📌 Additional attributes (first_name, last_name) are added automatically by Lambda.

###  6. Enable CloudWatch Logging

#### Purpose: Debug and monitor execution
![img](https://github.com/riyaj-2002/Facial-Recognition-System/blob/51e21b1d24241b3829e15300454a868c9f1d3723/cloudwatch.png)

####📌 Used for error checking and monitoring.
