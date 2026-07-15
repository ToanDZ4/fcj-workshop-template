---
title: "Week 9 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---

### Week 9 Objectives
* Learn Infrastructure as Code (IaC) and CI/CD basics.
* Design the architecture for the capstone project — the Serverless E-commerce Platform.

### Tasks carried out this week
| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| Mon | - IaC concepts; AWS CloudFormation templates, stacks | 15/06/2026 | 15/06/2026 | <https://docs.aws.amazon.com/cloudformation/> |
| Tue | - **Practice:** deploy a small stack from a CloudFormation template | 16/06/2026 | 16/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| Wed | - CI/CD overview: CodeBuild, CodePipeline, GitHub Actions | 17/06/2026 | 17/06/2026 | <https://docs.aws.amazon.com/codepipeline/> |
| Thu | - Draw the capstone architecture diagram; list required services | 18/06/2026 | 18/06/2026 | |
| Fri | - Define scope, cost estimate, and build plan for the capstone | 19/06/2026 | 19/06/2026 | |

### Week 9 Achievements
* Understood Infrastructure as Code and deployed a small stack with CloudFormation, learning stacks, parameters, and outputs.
* Got an overview of CI/CD pipelines and how source → build → deploy stages work.
* Designed the capstone architecture end to end: S3 + CloudFront frontend, Cognito auth, ALB + ECS/Fargate backend, DynamoDB data, Lambda for serverless tasks, Route 53 + ACM for domain/HTTPS, and CloudWatch for monitoring.
* Produced an architecture diagram, a rough cost estimate, and a two-week build plan (Weeks 10–11) with testing and cleanup in Week 12.
