---
title: "Worklog Tuần 11"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.11. </b> "
---

### Mục tiêu Tuần 11
* Tiếp tục xây dựng dự án (phần 2).
* Triển khai backend ECS/Fargate phía sau ALB, thêm Route 53 + ACM và Cognito, các hàm serverless, và một CloudFront distribution.

### Công việc thực hiện trong tuần
| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| Thứ 2 | - Build image backend, push lên ECR, triển khai ECS service trên Fargate phía sau ALB | 29/06/2026 | 29/06/2026 | [Workshop 5.4](../../5-Workshop/5.4-backend-ecs/) |
| Thứ 3 | - Cấu hình tên miền Route 53 + chứng chỉ ACM; thêm Cognito để xác thực | 30/06/2026 | 30/06/2026 | [Workshop 5.4](../../5-Workshop/5.4-backend-ecs/) |
| Thứ 4 | - Thêm các hàm serverless (Lambda) để xử lý đơn hàng | 01/07/2026 | 01/07/2026 | [Workshop 5.5](../../5-Workshop/5.5-serverless/) |
| Thứ 5 | - Tạo CloudFront distribution phía trước frontend + API | 02/07/2026 | 02/07/2026 | [Workshop 5.7](../../5-Workshop/5.7-cloudfront/) |
| Thứ 6 | - Kiểm thử end-to-end toàn bộ luồng | 03/07/2026 | 03/07/2026 | |

### Kết quả đạt được trong Tuần 11
* Triển khai backend container trên ECS/Fargate phía sau Application Load Balancer có health check.
* Gắn tên miền riêng qua Route 53 và bật HTTPS bằng chứng chỉ ACM; tích hợp Cognito cho đăng ký/đăng nhập.
* Thêm các hàm Lambda để xử lý đơn hàng và kết nối chúng vào luồng.
* Đặt CloudFront phía trước frontend và API để giảm độ trễ và phục vụ mọi thứ qua HTTPS.
* Hoàn tất kiểm thử end-to-end toàn luồng; tài liệu trở thành các mục 5.4, 5.5 và 5.7 của Workshop.
