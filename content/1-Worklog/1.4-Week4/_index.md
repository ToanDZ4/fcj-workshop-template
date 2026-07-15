---
title: "Week 4 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives
* Learn AWS storage and database services.
* Understand Amazon S3 (buckets, storage classes, static website hosting, bucket policies).
* Understand Amazon DynamoDB (tables, partition/sort keys) and get an overview of Amazon RDS.

### Tasks carried out this week
| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| Mon | - S3 buckets, objects, storage classes <br> - Versioning & lifecycle rules | 11/05/2026 | 11/05/2026 | <https://docs.aws.amazon.com/s3/> |
| Tue | - S3 static website hosting <br> - Bucket policies & block public access <br> - **Practice:** host a static page on S3 | 12/05/2026 | 12/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| Wed | - DynamoDB tables, partition key & sort key <br> - Read/write capacity, on-demand mode | 13/05/2026 | 13/05/2026 | <https://docs.aws.amazon.com/dynamodb/> |
| Thu | - **Practice:** create a DynamoDB table and run CRUD operations from the CLI/SDK | 14/05/2026 | 14/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| Fri | - Amazon RDS overview (engines, Multi-AZ, read replicas) <br> - When to choose SQL vs NoSQL | 15/05/2026 | 15/05/2026 | <https://docs.aws.amazon.com/rds/> |

### Week 4 Achievements
* Created S3 buckets, applied versioning and lifecycle rules, and understood the storage classes and their cost trade-offs.
* Hosted a static website on S3 and wrote a bucket policy that grants read access while keeping "block public access" controls understood.
* Created a DynamoDB table with a well-chosen partition/sort key and performed CRUD operations from the AWS CLI and SDK.
* Compared SQL (RDS) vs NoSQL (DynamoDB) and learned to choose based on access patterns; decided DynamoDB fits the capstone's product/cart data.
* These storage and database skills feed directly into the capstone's frontend (S3) and data layer (DynamoDB).
