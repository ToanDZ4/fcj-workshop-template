---
title: "Worklog Tuần 7"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu Tuần 7
* Học về DNS, phân phối nội dung và xác thực trên AWS.
* Hiểu Amazon Route 53, AWS Certificate Manager (ACM), Amazon CloudFront và Amazon Cognito.

### Công việc thực hiện trong tuần
| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| Thứ 2 | - Route 53 hosted zone, loại record (A, CNAME, Alias) | 01/06/2026 | 01/06/2026 | <https://docs.aws.amazon.com/route53/> |
| Thứ 3 | - ACM: yêu cầu và xác thực chứng chỉ TLS công khai | 02/06/2026 | 02/06/2026 | <https://docs.aws.amazon.com/acm/> |
| Thứ 4 | - CloudFront distribution, origin, cache behavior | 03/06/2026 | 03/06/2026 | <https://docs.aws.amazon.com/cloudfront/> |
| Thứ 5 | - **Thực hành:** phục vụ website S3 qua CloudFront với HTTPS | 04/06/2026 | 04/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| Thứ 6 | - Amazon Cognito user pool, đăng ký/đăng nhập, JWT token | 05/06/2026 | 05/06/2026 | <https://docs.aws.amazon.com/cognito/> |

### Kết quả đạt được trong Tuần 7
* Tạo hosted zone Route 53 và hiểu các loại record cùng routing policy.
* Yêu cầu và xác thực chứng chỉ TLS bằng ACM rồi gắn vào CloudFront/ALB để dùng HTTPS.
* Cấu hình CloudFront distribution phía trước origin S3, thiết lập cache behavior, phục vụ nội dung qua HTTPS với độ trễ thấp hơn.
* Thiết lập user pool Amazon Cognito cho đăng ký/đăng nhập và hiểu cách JWT token cấp quyền cho request API.
* Các dịch vụ này cung cấp tên miền riêng, HTTPS, CDN và xác thực người dùng cho dự án.
