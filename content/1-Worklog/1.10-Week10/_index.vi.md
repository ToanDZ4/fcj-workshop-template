---
title: "Worklog Tuần 10"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---

### Mục tiêu Tuần 10
* Bắt đầu xây dựng dự án — Nền tảng Thương mại điện tử Serverless (phần 1).
* Thiết lập IAM role, frontend tĩnh trên S3 và tầng dữ liệu DynamoDB.

### Công việc thực hiện trong tuần
| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| Thứ 2 | - Tạo IAM role cho dự án (ecsTaskExecutionRole, role cho Lambda) theo least privilege | 22/06/2026 | 22/06/2026 | [Workshop 5.2](../../5-Workshop/5.2-IAM/) |
| Thứ 3 | - Build và triển khai frontend lên S3 static hosting | 23/06/2026 | 23/06/2026 | [Workshop 5.3](../../5-Workshop/5.3-database-storage/) |
| Thứ 4 | - Tạo bảng DynamoDB cho sản phẩm/đơn hàng; nạp dữ liệu mẫu | 24/06/2026 | 24/06/2026 | [Workshop 5.3](../../5-Workshop/5.3-database-storage/) |
| Thứ 5 | - Kết nối luồng upload/list của frontend với tầng lưu trữ | 25/06/2026 | 25/06/2026 | |
| Thứ 6 | - Rà soát, sửa lỗi và ghi lại tiến độ | 26/06/2026 | 26/06/2026 | |

### Kết quả đạt được trong Tuần 10
* Tạo các IAM role least-privilege cho ECS task và các hàm Lambda dùng trong dự án.
* Triển khai frontend tĩnh lên bucket S3 và xác minh trang tải đúng.
* Tạo và nạp dữ liệu cho các bảng DynamoDB (sản phẩm và đơn hàng), kết nối luồng list/upload của frontend với tầng lưu trữ.
* Ghi lại từng bước kèm ảnh chụp màn hình, về sau trở thành mục 5.2 và 5.3 của Workshop.
