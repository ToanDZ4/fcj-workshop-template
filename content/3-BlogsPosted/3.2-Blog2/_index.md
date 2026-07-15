---
title: "Blog 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

# Building a Serverless REST API with API Gateway, Lambda and DynamoDB

In this lab I built a fully **serverless REST API**. There are no servers to manage: Amazon API Gateway receives HTTP requests, AWS Lambda runs the business logic, and Amazon DynamoDB stores the data. You pay only per request.

## Architecture

```
Client → API Gateway → Lambda functions → DynamoDB table
```

- **Amazon API Gateway** exposes REST endpoints (for example `GET /items`, `POST /items`).
- **AWS Lambda** holds one function per operation (list, get, create, delete).
- **Amazon DynamoDB** is the NoSQL data store with a partition key `id`.

## Main steps

1. **Create a DynamoDB table** (`items`) with partition key `id`.
2. **Write Lambda functions** for each operation and give each an **execution role** with least-privilege access to only that table.
3. **Create an API Gateway REST API** and connect each route/method to the matching Lambda using proxy integration.
4. **Deploy the API** to a stage (for example `prod`) to get an invoke URL.
5. **Test** with `curl` / Postman:
   ```bash
   curl -X POST https://<api-id>.execute-api.<region>.amazonaws.com/prod/items \
     -H "Content-Type: application/json" \
     -d '{"id":"1","name":"Sample"}'
   ```
6. (Optional) **Secure the API** with an Amazon Cognito authorizer so only signed-in users can call it.

## Lessons learned

- Serverless removes server management and scales automatically with traffic.
- Least-privilege execution roles are important — each function should only touch the resources it needs.
- Watch out for **Lambda cold starts** on the first request; keep functions small and dependencies light.

> I reused this API Gateway + Lambda + DynamoDB pattern for the order and product APIs of my capstone project.
