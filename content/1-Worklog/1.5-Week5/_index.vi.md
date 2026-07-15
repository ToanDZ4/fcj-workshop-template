---
title: "Worklog Tuần 5"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu Tuần 5
* Hiểu sâu hơn về compute trên AWS: Amazon EC2, Elastic Load Balancing và Auto Scaling.
* Học về container: Docker, Amazon ECR, Amazon ECS và AWS Fargate.

### Công việc thực hiện trong tuần
| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| Thứ 2 | - EC2 chuyên sâu: họ instance, mô hình giá (On-Demand, Spot, Savings Plans) | 18/05/2026 | 18/05/2026 | <https://docs.aws.amazon.com/ec2/> |
| Thứ 3 | - Application Load Balancer & target group <br> - Health check | 19/05/2026 | 19/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| Thứ 4 | - Auto Scaling group, launch template, scaling policy | 20/05/2026 | 20/05/2026 | <https://docs.aws.amazon.com/autoscaling/> |
| Thứ 5 | - Kiến thức nền Docker, build image, push lên Amazon ECR | 21/05/2026 | 21/05/2026 | <https://docs.aws.amazon.com/ecr/> |
| Thứ 6 | - Amazon ECS & AWS Fargate <br> - **Thực hành:** chạy một container task trên Fargate | 22/05/2026 | 22/05/2026 | <https://docs.aws.amazon.com/ecs/> |

### Kết quả đạt được trong Tuần 5
* Học cách chọn họ instance EC2 và mô hình giá để cân bằng hiệu năng và chi phí.
* Cấu hình Application Load Balancer với target group và health check, cùng Auto Scaling group dùng launch template và scaling policy.
* Build image Docker cục bộ, push lên Amazon ECR, hiểu image tag và lifecycle policy của repository.
* Chạy một container task trên AWS Fargate mà không cần quản lý server, hiểu task definition, service của ECS và `ecsTaskExecutionRole`.
* Xác nhận ECS trên Fargate phía sau ALB là lựa chọn compute phù hợp cho backend của dự án.
