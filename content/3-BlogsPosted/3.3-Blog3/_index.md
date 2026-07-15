---
title: "Blog 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---

# Running Containers on Amazon ECS with AWS Fargate

In this lab I deployed a containerized web application on **Amazon ECS** using **AWS Fargate**, behind an **Application Load Balancer (ALB)**. Fargate is serverless for containers — you don't manage any EC2 hosts.

## Architecture

```
User → ALB → ECS Service (Fargate tasks) → (DynamoDB / RDS)
                      ↑ image pulled from Amazon ECR
```

- **Amazon ECR** stores the Docker image.
- **Amazon ECS** with the **Fargate** launch type runs the containers as tasks.
- **Application Load Balancer** distributes traffic across tasks and runs health checks.

## Main steps

1. **Build the Docker image** locally and **push it to Amazon ECR**:
   ```bash
   aws ecr get-login-password | docker login --username AWS --password-stdin <acct>.dkr.ecr.<region>.amazonaws.com
   docker build -t myapp .
   docker tag myapp:latest <acct>.dkr.ecr.<region>.amazonaws.com/myapp:latest
   docker push <acct>.dkr.ecr.<region>.amazonaws.com/myapp:latest
   ```
2. **Create an ECS cluster** (Fargate).
3. **Create a task definition** referencing the ECR image, CPU/memory, port mappings, and the **`ecsTaskExecutionRole`**.
4. **Create an ECS service** with the desired task count, placed in private subnets.
5. **Add an ALB** with a target group and health check pointing to the container port.
6. **Test** the ALB DNS name in the browser.

## Lessons learned

- Fargate removes the need to patch or scale EC2 hosts; you just define CPU/memory per task.
- The **`ecsTaskExecutionRole`** is required so ECS can pull the image from ECR and write logs to CloudWatch.
- Running tasks in **private subnets** behind an ALB is a secure, production-like layout.

> This is the exact backend design of my capstone Serverless E-commerce Platform (Workshop section 5.4).
