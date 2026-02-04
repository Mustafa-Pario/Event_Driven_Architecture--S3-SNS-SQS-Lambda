# AWS Event-Driven Architecture (S3–SNS–SQS–Lambda)

This project demonstrates an event-driven architecture on AWS, where events are used to decouple application components and enable scalable, asynchronous processing.

## 📌 Overview

Event-driven architectures allow services to communicate through events instead of direct calls. This improves scalability, fault tolerance, and flexibility.

In this implementation, an event generated in Amazon S3 flows through SNS and SQS before being processed by AWS Lambda.

## 🧩 Sample Use Case

- Event Producer: Amazon S3

  - Object-level events (e.g., file uploads) trigger notifications.

- Event Ingestion: Amazon SNS

  - Receives events from S3 and fans them out to subscribers.

- Event Stream: Amazon SQS

  - Buffers events and ensures reliable, decoupled message delivery.

- Event Consumer: AWS Lambda

  - Processes messages pulled from the SQS queue.
  - 

## 🏗 Architecture Flow

1. An object is created in an S3 bucket.

2. S3 publishes an event to an SNS topic.

3. SNS delivers the event to an SQS queue (with optional filter policies).

4. Lambda polls the SQS queue and processes the event.


## 📂 Repository Contents

This repository includes the policies required to securely implement the architecture:

- SNS access policy – Allows S3 to publish events to SNS

- SQS access policy – Allows SNS to send messages to SQS

- SNS subscription filter policy – Filters events before they reach SQS

- Lambda policies – Permissions for Lambda to read from SQS and access required AWS resources
- 

