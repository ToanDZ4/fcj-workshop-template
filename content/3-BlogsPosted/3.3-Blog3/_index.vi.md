---
title: "Blog 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---

# Chạy container trên Amazon ECS với AWS Fargate

Trong bài lab này, tôi triển khai một ứng dụng web dạng container trên **Amazon ECS** dùng **AWS Fargate**, phía sau một **Application Load Balancer (ALB)**. Fargate là serverless cho container — bạn không phải quản lý host EC2 nào.

## Kiến trúc

```
Người dùng → ALB → ECS Service (Fargate task) → (DynamoDB / RDS)
                        ↑ image được kéo từ Amazon ECR
```

- **Amazon ECR** lưu Docker image.
- **Amazon ECS** với launch type **Fargate** chạy container dưới dạng task.
- **Application Load Balancer** phân phối lưu lượng tới các task và chạy health check.

## Các bước chính

1. **Build Docker image** cục bộ và **push lên Amazon ECR**:
   ```bash
   aws ecr get-login-password | docker login --username AWS --password-stdin <acct>.dkr.ecr.<region>.amazonaws.com
   docker build -t myapp .
   docker tag myapp:latest <acct>.dkr.ecr.<region>.amazonaws.com/myapp:latest
   docker push <acct>.dkr.ecr.<region>.amazonaws.com/myapp:latest
   ```
2. **Tạo ECS cluster** (Fargate).
3. **Tạo task definition** tham chiếu image ECR, CPU/memory, port mapping và **`ecsTaskExecutionRole`**.
4. **Tạo ECS service** với số lượng task mong muốn, đặt trong các subnet private.
5. **Thêm ALB** với target group và health check trỏ tới port của container.
6. **Kiểm thử** bằng tên DNS của ALB trên trình duyệt.

## Bài học rút ra

- Fargate loại bỏ việc vá lỗi hay co giãn host EC2; bạn chỉ cần định nghĩa CPU/memory cho mỗi task.
- **`ecsTaskExecutionRole`** là bắt buộc để ECS kéo image từ ECR và ghi log vào CloudWatch.
- Chạy task trong **subnet private** phía sau ALB là bố cục an toàn, gần với môi trường production.

> Đây chính là thiết kế backend của dự án Nền tảng Thương mại điện tử Serverless (Workshop mục 5.4).
