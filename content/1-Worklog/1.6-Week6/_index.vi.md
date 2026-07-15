---
title: "Worklog Tuần 6"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu Tuần 6
* Hiểu kiến trúc serverless trên AWS.
* Học AWS Lambda, Amazon API Gateway, Amazon SQS, Amazon SNS và Amazon EventBridge.
* Xây dựng một REST API serverless nhỏ hoàn chỉnh.

### Công việc thực hiện trong tuần
| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| Thứ 2 | - Khái niệm Lambda: function, trigger, execution role, cold start | 25/05/2026 | 25/05/2026 | <https://docs.aws.amazon.com/lambda/> |
| Thứ 3 | - API Gateway (REST/HTTP API), integration, stage | 26/05/2026 | 26/05/2026 | <https://docs.aws.amazon.com/apigateway/> |
| Thứ 4 | - **Thực hành:** REST API với API Gateway + Lambda + DynamoDB | 27/05/2026 | 27/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| Thứ 5 | - Tách rời hệ thống với SQS (queue) và SNS (pub/sub) | 28/05/2026 | 28/05/2026 | <https://docs.aws.amazon.com/sqs/> |
| Thứ 6 | - EventBridge rule & mô hình hướng sự kiện | 29/05/2026 | 29/05/2026 | <https://docs.aws.amazon.com/eventbridge/> |

### Kết quả đạt được trong Tuần 6
* Viết các hàm AWS Lambda với execution role theo least-privilege, hiểu đánh đổi về chi phí và cold start.
* Xây dựng REST API hoạt động qua API Gateway → Lambda → DynamoDB, kiểm thử bằng `curl` và Postman.
* Dùng SQS để tách rời producer và consumer, dùng SNS cho thông báo fan-out, hiểu khi nào dùng cái nào.
* Học thiết kế hướng sự kiện với EventBridge rule để định tuyến sự kiện giữa các dịch vụ.
* Các mô hình này được tái sử dụng cho các hàm serverless của dự án (ví dụ xử lý đơn hàng và gửi thông báo).
