---
title: "Worklog Tuần 4"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu Tuần 4
* Tìm hiểu các dịch vụ lưu trữ và cơ sở dữ liệu của AWS.
* Hiểu Amazon S3 (bucket, storage class, static website hosting, bucket policy).
* Hiểu Amazon DynamoDB (bảng, partition/sort key) và tổng quan về Amazon RDS.

### Công việc thực hiện trong tuần
| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| Thứ 2 | - S3 bucket, object, storage class <br> - Versioning & lifecycle rule | 11/05/2026 | 11/05/2026 | <https://docs.aws.amazon.com/s3/> |
| Thứ 3 | - S3 static website hosting <br> - Bucket policy & block public access <br> - **Thực hành:** host một trang tĩnh trên S3 | 12/05/2026 | 12/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| Thứ 4 | - Bảng DynamoDB, partition key & sort key <br> - Read/write capacity, chế độ on-demand | 13/05/2026 | 13/05/2026 | <https://docs.aws.amazon.com/dynamodb/> |
| Thứ 5 | - **Thực hành:** tạo bảng DynamoDB và thao tác CRUD qua CLI/SDK | 14/05/2026 | 14/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| Thứ 6 | - Tổng quan Amazon RDS (engine, Multi-AZ, read replica) <br> - Khi nào chọn SQL vs NoSQL | 15/05/2026 | 15/05/2026 | <https://docs.aws.amazon.com/rds/> |

### Kết quả đạt được trong Tuần 4
* Tạo bucket S3, áp dụng versioning và lifecycle rule, hiểu các storage class và đánh đổi về chi phí.
* Host một website tĩnh trên S3 và viết bucket policy cấp quyền đọc trong khi vẫn nắm rõ cơ chế "block public access".
* Tạo bảng DynamoDB với partition/sort key hợp lý và thao tác CRUD qua AWS CLI và SDK.
* So sánh SQL (RDS) vs NoSQL (DynamoDB), học cách chọn theo access pattern; quyết định dùng DynamoDB cho dữ liệu sản phẩm/giỏ hàng của dự án.
* Các kỹ năng lưu trữ và cơ sở dữ liệu này phục vụ trực tiếp cho frontend (S3) và tầng dữ liệu (DynamoDB) của dự án.
