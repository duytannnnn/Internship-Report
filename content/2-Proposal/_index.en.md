+++
title = "Proposal"
date = 2026-06-01
weight = 2

pre = " <b> 2. </b> "
+++

---

#  __Serverless AI Invoice Scanner – An AI-Powered Solution for Automated Invoice Extraction and Management on AWS__

> 🔍 *An intelligent system that enables users to upload invoice images or PDF files, automatically extracts invoice data using Amazon Textract, standardizes the extracted information with the OpenAI API, stores structured data in Amazon DynamoDB, and provides a web-based invoice management interface built with React and deployed using AWS Amplify Hosting.*

---

### 📝 Project Summary

In the era of digital transformation, automating the processing of incoming invoices has become an essential requirement for many organizations. Invoices are often received in various formats, including PDF documents, scanned files, photographs, and other unstructured documents. This diversity makes it challenging to extract, validate, store, and retrieve invoice data efficiently.

**Serverless AI Invoice Scanner** was developed to address this challenge by leveraging artificial intelligence and a serverless architecture on AWS. The system enables users to upload invoice files, automatically extracts text using Amazon Textract, and then utilizes the OpenAI API to analyze and standardize the extracted information into a structured format. The resulting data includes fields such as invoice number, customer name, invoice date, total amount, currency, and other relevant invoice details.

After processing, the structured data is stored in Amazon DynamoDB, allowing fast and scalable data retrieval through RESTful APIs built with Amazon API Gateway and AWS Lambda. The frontend is developed using ReactJS, deployed with AWS Amplify Hosting, and integrated with Amazon Cognito to provide secure user authentication, including user registration and sign-in.

{{% notice info %}}
In the current version of this project, the system uses the OpenAI API instead of Amazon Bedrock for AI-powered data processing. Since the OpenAI API is an external service outside the AWS ecosystem, its API key must be securely stored on the backend, such as in AWS Lambda environment variables or AWS Secrets Manager.
{{% /notice %}}

### 🎯 Key Benefits

- **Automated Data Entry**: Eliminates manual invoice processing, significantly reducing the time required to extract and enter invoice information.
- **Improved Accuracy**: Combines the OCR capabilities of Amazon Textract with the semantic understanding of the OpenAI API to deliver more accurate and reliable invoice data.
- **Efficient Data Retrieval**: Stores invoices as structured records in Amazon DynamoDB, enabling fast and scalable querying.
- **Intuitive Invoice Management**: Provides a user-friendly frontend for viewing invoice lists, inspecting details, searching records, organizing invoices with tags, marking favorites (starred), and exporting data to Excel.
- **Secure User Authentication**: Integrates Amazon Cognito to support secure user registration, sign-in, and identity management.
- **Highly Scalable Architecture**: Built on a serverless architecture, allowing the system to automatically scale based on incoming request volume while minimizing infrastructure management.

---

##  1. Problem statement

###  Current situation

Many organizations, especially small and medium-sized enterprises (SMEs), still process incoming invoices manually or through semi-automated workflows. Accounting staff are often required to open each invoice individually, identify key information such as the invoice number, issue date, customer name, total amount, tax, and vendor details, and then manually re-enter this information into the company's accounting or management system.


This process presents several limitations:

- Time-consuming: Processing becomes increasingly inefficient as the number of invoices grows.
- Prone to Human Error: Manual data entry can lead to inaccuracies and inconsistencies.
- Limited Searchability: Invoice information is difficult to search and retrieve when stored only as image or PDF files.
- Difficult to Audit and Reconcile: Manual records make reporting, reconciliation, and auditing more complex.
- Poor System Integration: Unstructured invoice data is difficult to integrate with management systems or business reporting tools.

➡️ **Identified needs** It involves building a system capable of accepting multi-format invoices, automatically extracting content, standardizing data using AI, storing it centrally, and supporting rapid retrieval.

###  Key challenges

1. **Diverse invoice formats**  
   Invoices can be PDFs, photos, scans, or images of varying quality.

2. **Unstructured data**  
   Invoice content typically does not follow a fixed format, making information extraction difficult.

3. **Errors during manual data entry**  
   People may enter incorrect amounts, dates, invoice codes, or customer names.

4. **Difficult to search and categorize**  
   If invoices are stored solely as files, searching for them by customer, date, amount, or processing status becomes difficult.

5. **Data security requirements**  
   Invoices may contain sensitive financial or business information that requires protection during storage and transmission.

6. **Need to expand the system**  
   As the number of users or invoices increases, the system needs to be scalable without requiring manual server management.

### 👥 Impact on stakeholders

| Stakeholder | Impact |
|---|---|
| **Accounting & Finance** | Reduces repetitive data entry; saves time on invoice processing. |
| **Business Management** | Provides centralized invoice data that is easy to review and track. |
| **Internal Audit** | Facilitates easy retrieval of invoices and related data for reconciliation. |
| **IT Department** | Offers a serverless system that is easy to deploy and maintain, eliminating the need for server operations. |
| **End Users** | Provides an intuitive interface for uploading, viewing, searching, and managing invoices. |

### 💥 Consequences of failing to address the issue

- Increased operating costs due to heavy reliance on manual data entry.
- Risk of accounting data discrepancies.
- Difficulty locating past invoices for reconciliation purposes.
- Delays in review and approval processes.
- Scalability challenges as invoice volumes rise.
- Obstacles to the business's digital transformation.

---

## 🏗️ 2. Solution Architecture

### 🧩 Architectural Overview
The **Serverless AI Invoice Scanner** system is built using a serverless and event-driven architecture on AWS. The main processing workflow consists of:
```txt
React Frontend
    ↓
Amazon Cognito
    ↓
Amazon API Gateway
    ↓
UploadInvoiceFileFunction
    ↓
Amazon S3 /uploads
    ↓
S3 Event Trigger
    ↓
ProcessInvoiceFunction
    ↓
Amazon Textract
    ↓
OpenAI API
    ↓
Amazon DynamoDB
    ↓
InvoiceManagementFunction
    ↓
API Gateway
    ↓
React Frontend
```

This architecture ensures a clear separation of functions:

- Frontend: Handles user interaction.
- API Gateway: Serves as the backend entry point.
- Lambda: Processes business logic.
- S3: Stores original invoice files.
- Textract: Extracts text.
- OpenAI API: Standardizes data.
- DynamoDB: Stores invoice data.
- CloudWatch: Supports log monitoring and debugging.

### 🎯 Architectural Design Goals

- Automate the invoice processing workflow from upload to storage.
- Eliminate the need to manage physical servers or EC2 instances.
- Decouple the frontend, API, AI processing, and data storage components.
- Ensure scalability based on request volume and the number of invoices.
- Facilitate easy testing using Postman, the AWS Console, and the React frontend.
- Enable the addition of advanced features such as tagging, starring, search functionality, and Excel export.
---

## 🔄 3. Data processing pipeline

### 3.1. User login flow

1. Users access the frontend deployed using **AWS Amplify Hosting**.
2. The frontend utilizes **Amazon Cognito User Pools** to handle registration and login.
3. Upon successful login, users can access system functions such as uploading invoices, viewing the invoice list, and searching for invoices.

{{% notice info %}}
In the current project, Cognito is primarily used for frontend authentication. API Gateway is protected by Cognito only if a dedicated Cognito Authorizer is configured.
{{% /notice %}}

### 3.2. Invoice upload workflow

1. The user selects an invoice file via the React interface.
2. The frontend converts the file to Base64.
3. The frontend sends a request to the API Gateway:

```txt
POST /uploads
```

4. API Gateway forwards the request to Lambda:

```txt
UploadInvoiceFileFunction
```

5. Lambda decodes the Base64 content and uploads the file to Amazon S3, typically into the following directory:

```txt
uploads/
```

6. After the file is saved to S3, an S3 Event Notification triggers Lambda to process the invoice.

### 3.3. AI-based invoice processing workflow

1. **ProcessInvoiceFunction** is triggered when a new file appears in S3.
2. The Lambda function reads the file from S3.
3. The Lambda function calls **Amazon Textract** to extract text from the invoice.
4. The OCR results are sent to the **OpenAI API** for analysis and normalization.
5. The normalized data is saved to a DynamoDB table:

```txt
InvoiceData
```

The data may include:

| Data Field | Description |
|---|---|
| `InvoiceId` | Unique identifier for the invoice. |
| `CustomerName` | Name of the customer or associated entity. |
| `InvoiceNumber` | Invoice number. |
| `InvoiceDate` | Date the invoice was issued. |
| `TotalAmount` | Total invoice amount. |
| `Currency` | Currency type, such as `VND`, `USD`, or `EUR`. |
| `Tags` | List of user-assigned tags for the invoice. |
| `Starred` | Status indicating if the invoice is marked as important. |
| `ProcessStatus` | Processing status, e.g., `SUCCESS` or `FAILED`. |
| `ExtractedData` | Extracted and normalized invoice data. |

### 3.4.Invoice retrieval and management workflow

Users can call the APIs via the frontend or Postman:

```txt
GET /invoice
GET /invoice/{id}
GET /invoice?name=<customer_name>
PATCH /invoice/tags/{id}
PATCH /invoice/starred/{id}
```

These requests are routed by the API Gateway to:

```txt
InvoiceManagementFunction
```

This Lambda function queries or updates data in DynamoDB and then returns the result to the frontend.

---

## 🧱 4. Key Functional Components

### 4.1. Frontend Layer

The frontend is built using **ReactJS** and deployed via **AWS Amplify Hosting**. The interface supports:

- Registration and login via Cognito.
- Invoice uploading via file selection or drag-and-drop.
- Viewing the list of processed invoices.
- Viewing invoice details.
- Searching for invoices by ID or customer name.
- Filtering by tags.
- Filtering by date.
- Sorting by date or total amount.
- Tagging invoices.
- Marking invoices as important (starring).
- Exporting invoice data to Excel.
- Displaying connection status for Cognito, the upload API, and the invoice API.

### 4.2. Authentication Layer

Amazon Cognito provides the following functionality:

- User Pool.
- Sign up.
- Sign in.
- Sign out.
- User session management.
- Frontend integration via `aws-amplify` and `@aws-amplify/ui-react`.

### 4.3. API Gateway Layer

API Gateway provides REST APIs for the frontend and Postman.

Key APIs:

| Method | Route | Functionality |
|---|---|---|
| `POST` | `/uploads` | Upload invoice file. |
| `GET` | `/invoice` | Retrieve list of invoices. |
| `GET` | `/invoice/{id}` | Retrieve invoice details by ID. |
| `GET` | `/invoice?name=<customer_name>` | Search for invoices by customer name. |
| `PATCH` | `/invoice/tags/{id}` | Update invoice tags. |
| `PATCH` | `/invoice/starred/{id}` | Update starred status. |

### 4.4. Lambda Layer

The system utilizes three main Lambda functions:

| Lambda Function | Role |
|---|---|
| `UploadInvoiceFileFunction` | Receives a Base64 file from the frontend, decodes it, and uploads it to S3. |
| `ProcessInvoiceFunction` | Processes the new file from S3, calls Textract and the OpenAI API, and saves the data to DynamoDB. |
| `InvoiceManagementFunction` | Handles API requests for listing, viewing details, searching, and updating tags and "starred" status. |

### 4.5. AI Processing Layer

The AI ​​Processing Layer consists of two components:

| Component | Role |
|---|---|
| Amazon Textract | Performs OCR and extracts text from invoices. |
| OpenAI API | Analyzes OCR content and normalizes it into structured JSON. |

Example of normalized data:

```json
{
  "InvoiceNumber": "INV-001",
  "CustomerName": "John Smith",
  "InvoiceDate": "2025-06-20",
  "TotalAmount": 125.50,
  "Currency": "USD"
}
```

### 4.6. Storage Layer

The system uses two types of storage:

| Service | Purpose |
|---|---|
| Amazon S3 | Stores original invoice files. |
| Amazon DynamoDB | Stores processed invoice data. |

Main DynamoDB table:
```txt
InvoiceData
```

Available indexes:

```txt
CustomerName-index
StarredInvoicesIndex
```

### 4.7. Monitoring Layer

Amazon CloudWatch is used to:

- Monitor Lambda logs.
- Debug upload errors.
- Debug Textract errors.
- Debug OpenAI API errors.
- Debug DynamoDB errors.
- Check for CORS or API Gateway errors.
- Monitor invoice processing status.

---

## 🧰 5. Services Used

| Service | Role in the project |
|---|---|
| **AWS Amplify Hosting** | Deploys the React frontend from GitHub. |
| **Amazon Cognito** | Handles user authentication for the frontend. |
| **Amazon API Gateway** | Provides REST API endpoints. |
| **AWS Lambda** | Executes backend logic using a serverless model. |
| **Amazon S3** | Stores original invoice files in the `uploads/` directory. |
| **Amazon Textract** | Extracts text and data from invoice files. |
| **OpenAI API** | Standardizes OCR data into structured JSON. |
| **Amazon DynamoDB** | Stores processed invoice data. |
| **Amazon CloudWatch** | Handles logging and system monitoring. |
| **AWS IAM** | Grants Lambda permissions to access S3, Textract, DynamoDB, and CloudWatch. |
| **AWS Secrets Manager** *(optional)* | Securely stores the OpenAI API key. |
| **Route 53** *(optional)* | Configures a custom domain if required. |

{{% notice warning %}}
Route 53 is an optional component. If the project does not use a custom domain, Route 53 does not need to be included in the mandatory deployment setup.
{{% /notice %}}

---

## 🔐 6. Security Architecture

### 6.1. User Authentication

- Users authenticate via Amazon Cognito.
- The frontend manages sessions using the AWS Amplify library.
- Configuration details such as User Pool ID, App Client ID, and Region are defined within the frontend.

### 6.2. API Protection

API Gateway can be secured using a Cognito Authorizer for production deployments. For demos or MVPs, the authorizer may be disabled to simplify testing.

{{% notice info %}}
If the Cognito Authorizer is enabled, the frontend must send an `Authorization` header, and the API Gateway CORS configuration must allow the `Authorization` header.
{{% /notice %}}

### 6.3. Data Protection

- S3 buckets should have "Block Public Access" enabled.
- DynamoDB is not exposed directly to the public internet.
- Lambda functions utilize IAM roles with least-privilege permissions.
- OpenAI API keys must not be hardcoded in the frontend.
- Avoid logging full requests if they contain tokens or sensitive data.

### 6.4. Operational Security

- CloudWatch is used for error monitoring.
- IAM roles are granted only the necessary permissions.
- AWS Secrets Manager can be used for secret management.
- CloudTrail or WAF can be implemented for production environments.
---

## ⚙️ 7. Technical Implementation

### 📌 Implementation Phases

#### Phase 1: AWS Environment Setup

- Create an S3 bucket to store invoices.
- Create the `InvoiceData` DynamoDB table.
- Create a Cognito User Pool.
- Create Lambda functions.
- Configure IAM Roles.
- Configure API Gateway routes.
- Prepare the OpenAI API key for the backend.

#### Phase 2: Building the Upload Flow

- Create the `POST /uploads` route on API Gateway.
- Create the `UploadInvoiceFileFunction`.
- Frontend converts the file to Base64.
- Lambda decodes the Base64 and uploads the file to S3.
- Test the upload process using the frontend and Postman.

#### Phase 3: Building the AI ​​Processing Flow

- Configure S3 Event Notifications.
- Create the `ProcessInvoiceFunction`.
- Lambda calls Amazon Textract for OCR.
- Lambda sends OCR results to the OpenAI API.
- Lambda saves normalized data to DynamoDB.
- Log processing activities to CloudWatch.

#### Phase 4: Building the Invoice Management API

- Create the `InvoiceManagementFunction`.
- Create API routes:
  - `GET /invoice`
  - `GET /invoice/{id}`
  - `GET /invoice?name=<customer_name>`
  - `PATCH /invoice/tags/{id}`
  - `PATCH /invoice/starred/{id}`
- Test the API using Postman.
- Standardize data returned to the frontend.

#### Phase 5: Building the Frontend

- Build the React application.
- Integrate Cognito using `aws-amplify`.
- Integrate API Gateway endpoints using `.env` variables.
- Create interfaces for upload, list view, details, search, tagging, starring, sorting, filtering, and Excel export.
- Deploy the frontend using AWS Amplify Hosting.

#### Phase 6: Testing and Finalization

- Test invoice upload.
- Test invoice list retrieval.
- Test search by ID and customer name.
- Test updating tags and starred status.
- Test CORS.
- Check CloudWatch Logs.
- Fix data issues (e.g., `Tags/tags`, `Starred/IsStarred`, `CustomerName` placement at the top level vs. within `ExtractedData`).

---

## 🧪 8. Testing Strategy

### 8.1. Functional Testing

| Function | Expected Result |
|---|---|
| Invoice upload | File saved to S3. |
| S3 trigger | Lambda processing function triggered. |
| Textract OCR | Text extracted from invoice. |
| OpenAI normalization | Structured invoice JSON returned. |
| DynamoDB save | Item saved to `InvoiceData` table. |
| GET `/invoice` | List of invoices returned. |
| GET `/invoice/{id}` | Invoice details returned. |
| GET `/invoice?name=` | Invoice found by customer name. |
| PATCH tags | Tags updated successfully. |
| PATCH starred | Starred status updated successfully. |

### 8.2. Security Testing

- Check CORS configuration.
- Verify OpenAI API key is not exposed on the frontend.
- Check Lambda IAM Role.
- Verify S3 bucket is not public.
- Check Cognito login/logout.
- If using Cognito Authorizer, test requests with and without the token.

### 8.3. Error Testing

| Error Scenario | Handling Method |
|---|---|
| Invalid file | Frontend displays an error message. |
| API Gateway incorrect route | Check for `Missing Authentication Token` error. |
| Lambda missing environment variable | Check CloudWatch Logs. |
| DynamoDB item missing | Return appropriate 404 error. |
| Textract error | Record `ProcessStatus = FAILED`. |
| OpenAI API error | Log the error and return a processing failure status. |

---

## 🗺️ 9. Roadmap and Milestones

### 📆 Project Roadmap

| Week | Phase | Objective |
|---|---|---|
| Week 1 | Architecture design & AWS setup | Create S3, DynamoDB, Lambda, Cognito, API Gateway. |
| Week 2 | Upload flow | Frontend uploads file via API Gateway to S3. |
| Week 3 | AI processing flow | S3 triggers Lambda; Textract OCR; OpenAI API normalization. |
| Week 4 | Invoice management API | GET/PATCH APIs; DynamoDB query/update. |
| Week 5 | Frontend completion | Upload, list, detail, search, tags, starred, export to Excel. |
| Week 6 | Testing & deployment | Postman testing, CloudWatch debugging, deploy via Amplify Hosting. |

### 📌 Key Milestones

| No. | Milestone | Output |
|---|---|---|
| 1 | Finalize architecture diagram | Diagram showing correct AWS + OpenAI API flow. |
| 2 | Successful invoice upload | File saved in S3 `uploads/` folder. |
| 3 | Successful invoice processing | Textract + OpenAI return structured data. |
| 4 | Successful DynamoDB save | Item appears in `InvoiceData` table. |
| 5 | Functional retrieval API | GET and PATCH endpoints working via Postman. |
| 6 | Frontend fully integrated | Users can manage invoices via the web interface. |
| 7 | Deploy Amplify Hosting | Public URL available to access the frontend. |
| 8 | Finalize documentation | Deployment, testing, and cleanup guides included. |

---

## 💰 10. Budget Estimate

### 📦 AWS Infrastructure Costs

| Service | Estimated Cost/Month | Notes |
|---|---:|---|
| Amazon S3 | ~$0.23 | Storing small-sized invoice files. |
| AWS Lambda | ~$1 – $3 | Depends on invocation count and execution time. |
| Amazon Textract | ~$4 – $6 | Depends on the number of pages processed monthly. |
| Amazon DynamoDB | ~$1 – $3 | On-Demand mode used for MVP. |
| API Gateway | ~$1 – $3 | Depends on request volume. |
| Amazon Cognito | ~$0 – $1 | Suitable for MVP with a small user base. |
| Amplify Hosting | ~$1 – $3 | Frontend hosting and low bandwidth usage. |
| CloudWatch Logs | ~$0 – $2 | Depends on log volume. |
| Secrets Manager *(optional)* | ~$0.40/secret/month | If used to store the OpenAI API key. |
| Route 53 *(optional)* | ~$0.50/month + domain | Use only if a custom domain is used. |

### 🤖 OpenAI API Costs

The OpenAI API is a service external to AWS. Costs depend on:

- The model used.
- The number of invoices processed.
- The length of the OCR content sent to the model.
- The number of input and output tokens.

During the MVP phase, you can limit prompts and send only the necessary OCR data to reduce costs.

{{% notice info %}}
OpenAI API costs should be tracked separately in the OpenAI dashboard, as they do not appear in AWS Billing.
{{% /notice %}}

### 👉 Estimated Total Cost

For a small-scale MVP, AWS costs may range from:

```txt
~$10 – $30 USD/month
```

This excludes OpenAI API costs and optional domain fees.

---

## ⚠️ 11. Risk Assessment

### 📋 Risk Matrix

| ID | Risk | Impact Level | Likelihood | Risk Level |
|---|---|---|---|---|
| R1 | Textract misreads blurry invoices or skewed scans | Medium | High | High |
| R2 | OpenAI API incorrectly normalizes data fields | High | Medium | High |
| R3 | OpenAI API key exposure | Very High | Low | High |
| R4 | Lambda error due to missing IAM permissions | High | Medium | High |
| R5 | API Gateway CORS error or incorrect route | Medium | High | High |
| R6 | DynamoDB stores incorrect fields (e.g., `Tags/tags`, `Starred/IsStarred`) | Medium | Medium | Medium |
| R7 | Increased costs due to excessive logging or requests | Medium | Medium | Medium |
| R8 | User uploads oversized files or incorrect formats | Medium | Medium | Medium |

### 🛡️ Mitigation Strategies

| Risk | Measure |
|---|---|
| R1 | Provide instructions for uploading clear files; support pre-processing file validation. |
| R2 | Design clear prompts, validate returned JSON, and log error states if parsing fails. |
| R3 | Do not store keys on the frontend; use Lambda environment variables or Secrets Manager. |
| R4 | Assign IAM Roles based on the principle of least privilege. |
| R5 | Configure CORS fully; test using Postman and the frontend. |
| R6 | Standardize fields in Lambda before sending data to the frontend. |
| R7 | Configure logging appropriately; clean up CloudWatch Logs after the lab. |
| R8 | Limit file types and upload sizes. |

---

## 🎯 12. Expected Outcomes

Upon project completion, the system achieves the following results:

- Users can register and log in using Amazon Cognito.
- The React frontend is deployed on AWS Amplify Hosting.
- Users can upload invoices via the web interface.
- Invoice files are stored in Amazon S3.
- An S3 trigger initiates a Lambda function to process the invoice.
- Amazon Textract extracts the invoice content.
- The OpenAI API standardizes the OCR content into structured data.
- Data is stored in the DynamoDB table `InvoiceData`.
- Users can view lists and details of invoices.
- Users can search by ID or customer name.
- Users can update tags and "starred" status.
- Users can filter, sort, and export data to Excel.
- CloudWatch supports log monitoring and error debugging.

### 📊 Success Metrics

| Metric | Target |
|---|---|
| Successful upload | ≥ 95% for valid files. |
| Successful OCR | ≥ 90% for clear invoices. |
| API stability | GET/PATCH/POST return correct responses. |
| Correct data structure | Includes `InvoiceId`, `ExtractedData`, `TotalAmount`, `Currency`. |
| Frontend usability | Users can complete the entire main workflow. |
| MVP cost | Kept low, suitable for demos/labs. |

---

## 📎 Appendix

### A. Technical Specifications

| Item | Technical Information | 
|---|---|
| Frontend | ReactJS, AWS Amplify Hosting |
| Authentication | Amazon Cognito User Pool |
| Frontend libraries | `aws-amplify`, `@aws-amplify/ui-react`, `xlsx` |
| Backend | AWS Lambda |
| Lambda runtime | Python với boto3 |
| API | Amazon API Gateway REST API |
| File storage | Amazon S3 |
| OCR | Amazon Textract |
| AI normalization | OpenAI API |
| Database | Amazon DynamoDB |
| Monitoring | Amazon CloudWatch |
| Optional secret storage | AWS Secrets Manager |
| Optional DNS | Amazon Route 53 |
| Architecture | Serverless, event-driven |

### B. API routes

| Method | Route | Lambda |
|---|---|---|
| `POST` | `/uploads` | `UploadInvoiceFileFunction` |
| `GET` | `/invoice` | `InvoiceManagementFunction` |
| `GET` | `/invoice/{id}` | `InvoiceManagementFunction` |
| `GET` | `/invoice?name=<customer_name>` | `InvoiceManagementFunction` |
| `PATCH` | `/invoice/tags/{id}` | `InvoiceManagementFunction` |
| `PATCH` | `/invoice/starred/{id}` | `InvoiceManagementFunction` |

### C. Environment variables frontend

```txt
REACT_APP_AWS_REGION=ap-southeast-1
REACT_APP_USER_POOL_ID=ap-southeast-1_xxxxxxxxx
REACT_APP_USER_POOL_CLIENT_ID=xxxxxxxxxxxxxxxxxxxxxxxxxx
REACT_APP_API_UPLOAD_URL=https://<api-id>.execute-api.ap-southeast-1.amazonaws.com/dev/uploads
REACT_APP_API_INVOICE_URL=https://<api-id>.execute-api.ap-southeast-1.amazonaws.com/dev/invoice
REACT_APP_API_UPDATE_TAGS_URL=https://<api-id>.execute-api.ap-southeast-1.amazonaws.com/dev/invoice/tags
REACT_APP_API_UPDATE_STARRED_URL=https://<api-id>.execute-api.ap-southeast-1.amazonaws.com/dev/invoice/starred
REACT_APP_SEND_AUTH_TOKEN=false
```

### D. DynamoDB table

```txt
Table name: InvoiceData
Primary key: InvoiceId
Optional GSI:
- CustomerName-index
- StarredInvoicesIndex
```

### E. References

1. Amazon Textract Documentation 
2. AWS Lambda Documentation 
3. Amazon API Gateway Documentation 
4. Amazon DynamoDB Documentation 
5. Amazon Cognito Documentation 
6. AWS Amplify Hosting Documentation 
7. OpenAI API Documentation 
8. AWS CloudWatch Documentation
---

## ✅ Conclusion

The **Serverless AI Invoice Scanner** proposal is suitable for building an automated invoice processing system that is easy to deploy and scale. Compared to the original proposal, this update has been adjusted to the actual project:

- Replaced Amazon Bedrock with OpenAI API.

- Clarified the role of AWS Amplify Hosting.

- Clarified Cognito's use for frontend authentication.

- Added three main Lambda functions.

- Added practical API routes.

- Added tags, starred, search, filter, sort, and Excel export.

- Updated processing flow: API Gateway → Upload Lambda → S3 → Processing Lambda → Texttract → OpenAI API → DynamoDB.

- Added cleanup and monitoring via CloudWatch.



![Policy](/images/8/architecture-log.png)