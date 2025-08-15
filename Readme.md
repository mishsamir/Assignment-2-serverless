# CST8917 – Serverless Applications
## Assignment 2 – Serverless Service Alternatives Report
**Name:** Samir Mishra  
**Student ID:** 041165199  
**Date:** August 15, 2025  

---

## Objective
This report compares key Azure serverless and event-driven services studied in CST8917 with their closest equivalents in **Amazon Web Services (AWS)** and **Google Cloud Platform (GCP)**. It includes service overviews, triggers/bindings, integration options, monitoring, pricing, and a strengths/weaknesses perspective from a serverless architecture viewpoint.

---

## 1. Service Mapping Table (Quick Reference)

| Azure Service | AWS Equivalent | GCP Equivalent |
|---------------|---------------|----------------|
| **Azure Functions** | AWS Lambda | Google Cloud Functions |
| **Azure Durable Functions** | AWS Step Functions | Google Cloud Workflows |
| **Azure Logic Apps** | AWS Step Functions + AWS AppFlow | Google Cloud Workflows + Application Integration |
| **Azure Service Bus** | Amazon Simple Queue Service (SQS) + Amazon Simple Notification Service (SNS) | Google Cloud Pub/Sub |
| **Azure Event Grid** | Amazon EventBridge | Eventarc |
| **Azure Event Hubs** | Amazon Kinesis Data Streams | Google Cloud Pub/Sub |

---

## 2. Service Comparisons

### **1. Azure Functions**
**AWS Equivalent:** AWS Lambda  
**GCP Equivalent:** Google Cloud Functions  

**Overview:**  
Azure Functions, AWS Lambda, and Google Cloud Functions are Function-as-a-Service (FaaS) offerings enabling event-driven execution without infrastructure management.

**Core Features:**
- Multiple triggers (HTTP, Timer, Storage, Messaging)
- Bindings for data in/out without boilerplate code
- Multi-language runtime support

**Integration Options:**
- Azure Functions: Native integration with Azure Storage, Event Hub, Service Bus, Cosmos DB
- AWS Lambda: Integrates with over 200 AWS services (via EventBridge, API Gateway, S3, DynamoDB)
- GCP Cloud Functions: Tight integration with Cloud Storage, Firestore, Pub/Sub

**Monitoring & Observability:**
- Azure: Azure Monitor + Application Insights
- AWS: CloudWatch Metrics, Logs, X-Ray
- GCP: Cloud Monitoring + Cloud Logging

**Pricing Model:**
- Pay-per-execution + execution time
- Free tier for monthly executions and compute time

**Strengths & Weaknesses:**
- Azure: Deep Azure service integration, but cold start times can be longer in Consumption plan
- AWS: Largest ecosystem, high scalability, but concurrency limits by default
- GCP: Easy integration with GCP services, fewer supported triggers than AWS

---

### **2. Azure Durable Functions**
**AWS Equivalent:** AWS Step Functions  
**GCP Equivalent:** Google Cloud Workflows  

**Overview:**  
Durable Functions extend Azure Functions with stateful orchestration, enabling chaining, fan-out/fan-in, async HTTP APIs, and human interaction workflows.

**Core Features:**
- Built-in state management
- Long-running workflows with Durable Timers
- Patterns: Function chaining, fan-out/fan-in, monitor, human interaction

**Integration Options:**
- Azure: Directly orchestrates Azure Functions and connectors
- AWS: Step Functions integrate with Lambda, ECS, and on-prem services via API Gateway
- GCP: Workflows integrate with Cloud Functions, Run, and external APIs

**Monitoring & Observability:**
- Azure: Application Insights tracing for orchestrations
- AWS: Step Functions console with visual workflow
- GCP: Cloud Logging and Workflows execution logs

**Pricing Model:**
- Pay-per-orchestration and state transition
- All platforms have free tier thresholds

**Strengths & Weaknesses:**
- Azure: Simplifies complex workflows; limited to Azure Functions unless using APIs
- AWS: Rich integration library; slightly higher cost per state transition
- GCP: Lightweight and easy, but fewer built-in patterns

---

### **3. Azure Logic Apps**
**AWS Equivalent:** AWS Step Functions + AWS AppFlow  
**GCP Equivalent:** Google Cloud Workflows + Application Integration  

**Overview:**  
Low-code/no-code workflow automation platform integrating hundreds of services via connectors.

**Core Features:**
- Visual designer
- Prebuilt connectors (Office 365, Salesforce, etc.)
- Triggers & actions for event-based automation

**Integration Options:**
- Azure: 400+ connectors, hybrid connectors for on-prem systems
- AWS: AppFlow for SaaS integration, Step Functions for orchestration
- GCP: Application Integration for SaaS, Workflows for orchestration

**Monitoring & Observability:**
- Azure: Run history, Azure Monitor
- AWS: CloudWatch Logs for executions
- GCP: Cloud Logging, Integration Insights

**Pricing Model:**
- Pay-per-execution/action
- Connector-specific costs

**Strengths & Weaknesses:**
- Azure: Best for Azure-centric automation; costs can spike with high-volume triggers
- AWS: Requires combining services for equivalent features
- GCP: Fewer connectors than Azure

---

### **4. Azure Service Bus (Queues & Topics)**
**AWS Equivalent:** Amazon SQS + Amazon SNS  
**GCP Equivalent:** Google Cloud Pub/Sub  

**Overview:**  
Enterprise-grade messaging broker supporting queues (point-to-point) and topics (pub/sub).

**Core Features:**
- Queues: FIFO, guaranteed delivery
- Topics: Multiple subscribers, filters
- Dead-letter queues

**Integration Options:**
- Azure: Integrated with Functions, Logic Apps
- AWS: SQS/SNS with Lambda, EventBridge
- GCP: Pub/Sub triggers Cloud Functions

**Monitoring & Observability:**
- Azure: Monitor queue/topic metrics in Azure Monitor
- AWS: CloudWatch metrics for SQS/SNS
- GCP: Cloud Monitoring for Pub/Sub

**Pricing Model:**
- Pay per operation and message size
- All have free tier messages

**Strengths & Weaknesses:**
- Azure: Rich filtering rules, but slightly more complex setup than SQS
- AWS: Very high reliability, simple to use
- GCP: Unified service (Pub/Sub) simplifies architecture

---

### **5. Azure Event Grid**
**AWS Equivalent:** Amazon EventBridge  
**GCP Equivalent:** Eventarc  

**Overview:**  
Fully managed event routing service for discrete events, using a push model.

**Core Features:**
- Filters and event routing
- Native integration with Azure services
- Supports custom events

**Integration Options:**
- Azure: Functions, Logic Apps, Event Hubs
- AWS: EventBridge rules trigger Lambda, Step Functions
- GCP: Eventarc triggers Cloud Run, Functions

**Monitoring & Observability:**
- Azure: Azure Monitor event metrics
- AWS: CloudWatch Events logs
- GCP: Cloud Logging for event delivery

**Pricing Model:**
- Pay per million operations
- Free tier for low event volume

**Strengths & Weaknesses:**
- Azure: Very tight Azure integration
- AWS: Cross-account and SaaS integration strengths
- GCP: Strong for GKE/Cloud Run integration

---

### **6. Azure Event Hubs**
**AWS Equivalent:** Amazon Kinesis Data Streams  
**GCP Equivalent:** Google Cloud Pub/Sub  

**Overview:**  
High-throughput event ingestion and streaming platform.

**Core Features:**
- Partitioned consumer model
- Replay capability
- Capture to storage

**Integration Options:**
- Azure: Functions, Stream Analytics, Databricks
- AWS: Lambda, Firehose, Analytics
- GCP: Dataflow, Functions, BigQuery

**Monitoring & Observability:**
- Azure: Monitor throughput, lag in Azure Monitor
- AWS: Kinesis metrics in CloudWatch
- GCP: Pub/Sub backlog and delivery metrics

**Pricing Model:**
- Pay per throughput unit and retention
- AWS/GCP charge based on data volume and retention

**Strengths & Weaknesses:**
- Azure: Seamless integration with analytics tools
- AWS: Mature ecosystem with Kinesis family
- GCP: Simpler pricing but fewer partition controls

