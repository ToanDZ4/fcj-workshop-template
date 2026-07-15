---
title: "Week 5 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives
* Deepen understanding of compute on AWS: Amazon EC2, Elastic Load Balancing and Auto Scaling.
* Learn containers: Docker, Amazon ECR, Amazon ECS and AWS Fargate.

### Tasks carried out this week
| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| Mon | - EC2 deep dive: instance families, pricing models (On-Demand, Spot, Savings Plans) | 18/05/2026 | 18/05/2026 | <https://docs.aws.amazon.com/ec2/> |
| Tue | - Application Load Balancer & target groups <br> - Health checks | 19/05/2026 | 19/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| Wed | - Auto Scaling groups, launch templates, scaling policies | 20/05/2026 | 20/05/2026 | <https://docs.aws.amazon.com/autoscaling/> |
| Thu | - Docker fundamentals, build an image, push to Amazon ECR | 21/05/2026 | 21/05/2026 | <https://docs.aws.amazon.com/ecr/> |
| Fri | - Amazon ECS & AWS Fargate <br> - **Practice:** run a container task on Fargate | 22/05/2026 | 22/05/2026 | <https://docs.aws.amazon.com/ecs/> |

### Week 5 Achievements
* Learned to choose EC2 instance families and pricing models to balance performance and cost.
* Configured an Application Load Balancer with target groups and health checks, and an Auto Scaling group with launch templates and scaling policies.
* Built a Docker image locally, pushed it to Amazon ECR, and understood image tags and repository lifecycle policies.
* Ran a containerized task on AWS Fargate without managing servers, and understood ECS task definitions, services, and the `ecsTaskExecutionRole`.
* Confirmed that ECS on Fargate behind an ALB is the right compute choice for the capstone backend.
