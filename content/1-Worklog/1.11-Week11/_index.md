---
title: "Week 11 Worklog"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---

### Week 11 Objectives
* Continue building the capstone (part 2).
* Deploy the ECS/Fargate backend behind an ALB, add Route 53 + ACM and Cognito, serverless functions, and a CloudFront distribution.

### Tasks carried out this week
| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| Mon | - Build backend image, push to ECR, deploy ECS service on Fargate behind an ALB | 29/06/2026 | 29/06/2026 | [Workshop 5.4](../../5-Workshop/5.4-backend-ecs/) |
| Tue | - Configure Route 53 domain + ACM certificate; add Cognito for auth | 30/06/2026 | 30/06/2026 | [Workshop 5.4](../../5-Workshop/5.4-backend-ecs/) |
| Wed | - Add serverless functions (Lambda) for order processing | 01/07/2026 | 01/07/2026 | [Workshop 5.5](../../5-Workshop/5.5-serverless/) |
| Thu | - Create a CloudFront distribution in front of frontend + API | 02/07/2026 | 02/07/2026 | [Workshop 5.7](../../5-Workshop/5.7-cloudfront/) |
| Fri | - End-to-end smoke test of the full flow | 03/07/2026 | 03/07/2026 | |

### Week 11 Achievements
* Deployed the containerized backend on ECS/Fargate behind an Application Load Balancer with health checks.
* Attached a custom domain via Route 53 and enabled HTTPS with an ACM certificate; integrated Cognito for sign-up/sign-in.
* Added Lambda functions for order processing and connected them into the flow.
* Put CloudFront in front of the frontend and API to reduce latency and serve everything over HTTPS.
* Completed a full end-to-end smoke test; documentation became Workshop sections 5.4, 5.5 and 5.7.
