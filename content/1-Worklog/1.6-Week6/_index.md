---
title: "Week 6 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives
* Understand serverless architecture on AWS.
* Learn AWS Lambda, Amazon API Gateway, Amazon SQS, Amazon SNS and Amazon EventBridge.
* Build a small serverless REST API end to end.

### Tasks carried out this week
| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| Mon | - Lambda concepts: functions, triggers, execution role, cold start | 25/05/2026 | 25/05/2026 | <https://docs.aws.amazon.com/lambda/> |
| Tue | - API Gateway (REST/HTTP APIs), integrations, stages | 26/05/2026 | 26/05/2026 | <https://docs.aws.amazon.com/apigateway/> |
| Wed | - **Practice:** API Gateway + Lambda + DynamoDB REST API | 27/05/2026 | 27/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| Thu | - Decoupling with SQS (queues) and SNS (pub/sub) | 28/05/2026 | 28/05/2026 | <https://docs.aws.amazon.com/sqs/> |
| Fri | - EventBridge rules & event-driven patterns | 29/05/2026 | 29/05/2026 | <https://docs.aws.amazon.com/eventbridge/> |

### Week 6 Achievements
* Wrote AWS Lambda functions with least-privilege execution roles and understood the pricing and cold-start trade-offs.
* Built a working REST API using API Gateway → Lambda → DynamoDB, tested it with `curl` and Postman.
* Used SQS to decouple producers from consumers and SNS for fan-out notifications, understanding when to use each.
* Learned event-driven design with EventBridge rules to route events between services.
* These patterns are reused for the capstone's serverless functions (for example order-processing and notifications).
