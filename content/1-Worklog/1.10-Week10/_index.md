---
title: "Week 10 Worklog"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---

### Week 10 Objectives
* Start building the capstone — Serverless E-commerce Platform (part 1).
* Set up IAM roles, the S3 static frontend, and the DynamoDB data layer.

### Tasks carried out this week
| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| Mon | - Create project IAM roles (ecsTaskExecutionRole, Lambda roles) with least privilege | 22/06/2026 | 22/06/2026 | [Workshop 5.2](../../5-Workshop/5.2-IAM/) |
| Tue | - Build and deploy the frontend to S3 static hosting | 23/06/2026 | 23/06/2026 | [Workshop 5.3](../../5-Workshop/5.3-database-storage/) |
| Wed | - Create DynamoDB tables for products/orders; seed sample data | 24/06/2026 | 24/06/2026 | [Workshop 5.3](../../5-Workshop/5.3-database-storage/) |
| Thu | - Wire the frontend upload/list flow to storage | 25/06/2026 | 25/06/2026 | |
| Fri | - Review, fix issues, and document progress | 26/06/2026 | 26/06/2026 | |

### Week 10 Achievements
* Created least-privilege IAM roles for the ECS tasks and Lambda functions used by the project.
* Deployed the static frontend to an S3 bucket and verified the site loads correctly.
* Created and seeded the DynamoDB tables for products and orders, and connected the frontend's list/upload flow to storage.
* Documented each step with screenshots, which later became sections 5.2 and 5.3 of the Workshop.
