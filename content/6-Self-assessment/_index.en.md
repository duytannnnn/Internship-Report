+++
title = "Self-Assessment"
date = 2026-06-01
weight = 6
pre = " <b> 6. </b> "
+++

## Overview

As the member of the project team, I was responsible for developing the AI-powered invoice processing workflow. My primary responsibility was to build an automated pipeline capable of extracting information from uploaded invoices, processing the extracted text using Artificial Intelligence, and storing structured data into Amazon DynamoDB.

This role required a solid understanding of event-driven serverless architecture, AWS cloud services, and reliable data processing techniques. Throughout the project, I collaborated closely with backend and frontend developers to ensure the AI processing pipeline integrated seamlessly into the overall system.

## Responsibilities

My main responsibilities included:

- Configuring Amazon S3 ObjectCreated event triggers.
- Integrating Amazon Textract for OCR (Optical Character Recognition).
- Cleaning and preprocessing OCR output before AI processing.
- Connecting to the OpenAI API to convert raw OCR text into structured JSON.
- Normalizing invoice information into a consistent format.
- Saving processed invoice data into Amazon DynamoDB.
- Implementing exception handling and CloudWatch logging.

## AI Processing Workflow

The invoice processing pipeline follows these steps:

1. Users upload invoice files to Amazon S3.
2. The S3 ObjectCreated event automatically triggers an AWS Lambda function.
3. Lambda sends the uploaded invoice to Amazon Textract.
4. Textract extracts all readable text from the document.
5. The extracted text is cleaned and preprocessed.
6. The cleaned text is sent to the OpenAI API.
7. OpenAI converts the OCR result into a structured JSON object.
8. The normalized invoice data is stored in Amazon DynamoDB.
9. Amazon CloudWatch records logs for monitoring and debugging.

## Technologies Used

During implementation, I worked with:

- AWS Lambda
- Amazon S3
- Amazon Textract
- Amazon DynamoDB
- Amazon CloudWatch
- AWS IAM
- OpenAI API
- JSON Data Processing
- Python

## Challenges and Solutions

Several technical challenges were encountered during development.

### OCR Accuracy

Some invoices contained low-quality images or complicated layouts, resulting in inaccurate OCR results.

To improve extraction quality, text-cleaning and preprocessing techniques were applied before sending the content to the AI model.

### Data Standardization

Invoices from different vendors contained different formats and field names.

OpenAI API was used to convert inconsistent OCR outputs into a standardized JSON structure containing:

- Invoice Number
- Customer Name
- Invoice Date
- Total Amount

This significantly simplified data storage and retrieval.

### Error Handling

Failures may occur while calling Textract or OpenAI.

To improve reliability, exception handling, input validation, and CloudWatch logging were implemented throughout the processing pipeline.

## Knowledge and Skills Gained

This project provided valuable hands-on experience with cloud computing and serverless technologies.

Throughout the development process, I learned how different AWS services collaborate to build scalable cloud applications.

The knowledge and skills I gained include:

- Understanding AWS serverless architecture.
- Learning event-driven application design.
- Working with Amazon S3 for cloud storage.
- Using AWS Lambda for automatic event processing.
- Applying Amazon Textract for OCR document analysis.
- Managing NoSQL databases using Amazon DynamoDB.
- Monitoring cloud resources with Amazon CloudWatch.
- Configuring permissions through AWS IAM.
- Integrating third-party AI services such as OpenAI API.
- Processing and normalizing JSON data.
- Improving prompt engineering techniques for structured AI responses.
- Understanding cloud application deployment workflows.

Besides technical knowledge, I also improved my teamwork, communication, GitHub collaboration, and software development practices while working with other team members.

## Personal Reflection

Participating in this project allowed me to understand how Artificial Intelligence and AWS cloud services can be combined to automate real-world business processes.

Instead of manually entering invoice information, businesses can automatically extract, organize, and manage invoice data using serverless technologies. This reduces manual work, minimizes human errors, and improves overall efficiency.

As the AI Processing Developer, I gained practical experience in AWS cloud services, serverless architecture, OCR processing, AI integration, and distributed application development. This project has motivated me to continue learning more AWS services and developing cloud-native AI applications in the future.