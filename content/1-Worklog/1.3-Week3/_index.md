---
title: "Week 3 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives
* Understand networking on AWS with Amazon VPC.
* Learn subnets (public/private), Internet Gateway, NAT Gateway, route tables, security groups and network ACLs.
* Build an isolated network that will host the capstone project.

### Tasks carried out this week
| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| Mon | - VPC concepts, CIDR blocks, subnets <br> - Public vs private subnets | 04/05/2026 | 04/05/2026 | <https://docs.aws.amazon.com/vpc/> |
| Tue | - Internet Gateway & route tables <br> - **Practice:** create a VPC with public/private subnets | 05/05/2026 | 05/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| Wed | - NAT Gateway for private subnet outbound access <br> - Elastic IP for NAT | 06/05/2026 | 06/05/2026 | <https://docs.aws.amazon.com/vpc/> |
| Thu | - Security groups vs network ACLs (stateful vs stateless) | 07/05/2026 | 07/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| Fri | - VPC endpoints (Gateway & Interface) <br> - **Practice:** test connectivity between subnets | 08/05/2026 | 08/05/2026 | <https://docs.aws.amazon.com/vpc/> |

### Week 3 Achievements
* Built a VPC with public and private subnets across two Availability Zones for high availability.
* Configured an Internet Gateway and route tables so public subnets reach the internet, and a NAT Gateway so private subnets can pull updates while staying private.
* Understood the difference between security groups (stateful, instance level) and network ACLs (stateless, subnet level), and wrote least-privilege inbound/outbound rules.
* Learned about VPC endpoints and why they keep traffic to AWS services (like S3) inside the AWS network.
* This network design became the foundation for the capstone's ECS backend and database tier.
