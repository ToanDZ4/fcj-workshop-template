---
title: "Worklog Tuần 8"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu Tuần 8
* Học về giám sát, ghi log và caching trên AWS.
* Hiểu Amazon CloudWatch, AWS CloudTrail, AWS X-Ray, Amazon ElastiCache và AWS Systems Manager Parameter Store.

### Công việc thực hiện trong tuần
| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| Thứ 2 | - CloudWatch metric, log, alarm, dashboard | 08/06/2026 | 08/06/2026 | <https://docs.aws.amazon.com/cloudwatch/> |
| Thứ 3 | - CloudTrail để kiểm toán hoạt động API | 09/06/2026 | 09/06/2026 | <https://docs.aws.amazon.com/cloudtrail/> |
| Thứ 4 | - AWS X-Ray tracing cho ứng dụng phân tán | 10/06/2026 | 10/06/2026 | <https://docs.aws.amazon.com/xray/> |
| Thứ 5 | - ElastiCache (Redis) để caching; SSM Parameter Store cho config/secret | 11/06/2026 | 11/06/2026 | <https://docs.aws.amazon.com/elasticache/> |
| Thứ 6 | - **Thực hành:** tạo alarm & dashboard cho ứng dụng mẫu | 12/06/2026 | 12/06/2026 | <https://cloudjourney.awsstudygroup.com/> |

### Kết quả đạt được trong Tuần 8
* Cấu hình CloudWatch metric, log group, alarm và dashboard để theo dõi tình trạng ứng dụng.
* Bật CloudTrail để kiểm toán hoạt động tài khoản và hiểu vai trò của nó trong điều tra bảo mật.
* Gắn X-Ray vào ứng dụng mẫu để trace request qua các dịch vụ và tìm điểm nghẽn.
* Học cách caching bằng ElastiCache (Redis) để giảm tải cơ sở dữ liệu, và lưu config/secret an toàn trong SSM Parameter Store.
* Các thực hành về khả năng quan sát và caching này được áp dụng vào phần giám sát và hiệu năng của dự án.
