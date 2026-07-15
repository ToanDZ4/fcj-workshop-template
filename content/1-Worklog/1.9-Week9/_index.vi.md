---
title: "Worklog Tuần 9"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.9. </b> "
---

### Mục tiêu Tuần 9
* Học về Hạ tầng dưới dạng mã (IaC) và kiến thức cơ bản về CI/CD.
* Thiết kế kiến trúc cho dự án tổng kết — Nền tảng Thương mại điện tử Serverless.

### Công việc thực hiện trong tuần
| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| Thứ 2 | - Khái niệm IaC; template và stack AWS CloudFormation | 15/06/2026 | 15/06/2026 | <https://docs.aws.amazon.com/cloudformation/> |
| Thứ 3 | - **Thực hành:** triển khai một stack nhỏ từ template CloudFormation | 16/06/2026 | 16/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| Thứ 4 | - Tổng quan CI/CD: CodeBuild, CodePipeline, GitHub Actions | 17/06/2026 | 17/06/2026 | <https://docs.aws.amazon.com/codepipeline/> |
| Thứ 5 | - Vẽ sơ đồ kiến trúc dự án; liệt kê các dịch vụ cần dùng | 18/06/2026 | 18/06/2026 | |
| Thứ 6 | - Xác định phạm vi, ước tính chi phí và kế hoạch xây dựng dự án | 19/06/2026 | 19/06/2026 | |

### Kết quả đạt được trong Tuần 9
* Hiểu Hạ tầng dưới dạng mã và triển khai một stack nhỏ bằng CloudFormation, nắm được stack, parameter và output.
* Có cái nhìn tổng quan về pipeline CI/CD và cách các bước source → build → deploy hoạt động.
* Thiết kế kiến trúc dự án hoàn chỉnh: frontend S3 + CloudFront, xác thực Cognito, backend ALB + ECS/Fargate, dữ liệu DynamoDB, Lambda cho tác vụ serverless, Route 53 + ACM cho tên miền/HTTPS, và CloudWatch để giám sát.
* Hoàn thành sơ đồ kiến trúc, ước tính chi phí sơ bộ và kế hoạch xây dựng hai tuần (Tuần 10–11), kiểm thử và dọn dẹp ở Tuần 12.
