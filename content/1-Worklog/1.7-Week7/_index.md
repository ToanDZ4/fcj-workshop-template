---
title: "Week 7 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives
* Learn DNS, content delivery and authentication on AWS.
* Understand Amazon Route 53, AWS Certificate Manager (ACM), Amazon CloudFront and Amazon Cognito.

### Tasks carried out this week
| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| Mon | - Route 53 hosted zones, record types (A, CNAME, Alias) | 01/06/2026 | 01/06/2026 | <https://docs.aws.amazon.com/route53/> |
| Tue | - ACM: request and validate a public TLS certificate | 02/06/2026 | 02/06/2026 | <https://docs.aws.amazon.com/acm/> |
| Wed | - CloudFront distributions, origins, cache behaviors | 03/06/2026 | 03/06/2026 | <https://docs.aws.amazon.com/cloudfront/> |
| Thu | - **Practice:** serve an S3 site over CloudFront with HTTPS | 04/06/2026 | 04/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| Fri | - Amazon Cognito user pools, sign-up/sign-in, JWT tokens | 05/06/2026 | 05/06/2026 | <https://docs.aws.amazon.com/cognito/> |

### Week 7 Achievements
* Created a Route 53 hosted zone and understood record types and routing policies.
* Requested and validated a TLS certificate with ACM and attached it to CloudFront/ALB for HTTPS.
* Configured a CloudFront distribution in front of an S3 origin, set cache behaviors, and served content over HTTPS with lower latency.
* Set up an Amazon Cognito user pool for sign-up/sign-in and understood how JWT tokens authorize API requests.
* These services provide the capstone's custom domain, HTTPS, CDN, and user authentication.
