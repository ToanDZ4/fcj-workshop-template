---
title: "Worklog Tuần 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu Tuần 2
* Hiểu về quản lý định danh và truy cập (IAM) và mô hình trách nhiệm chung (shared responsibility model).
* Tìm hiểu user, group, role, policy và cách áp dụng nguyên tắc đặc quyền tối thiểu (least privilege).
* Thực hành bảo vệ tài khoản root và tạo các định danh IAM giới hạn quyền cho dự án.

> Lưu ý: 30/04 và 01/05 là ngày nghỉ lễ tại Việt Nam nên phần thực hành trong tuần được sắp xếp quanh hai ngày này.

### Công việc thực hiện trong tuần
| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| Thứ 2 | - Học mô hình trách nhiệm chung <br> - IAM user, group, role, policy | 27/04/2026 | 27/04/2026 | <https://docs.aws.amazon.com/IAM/> |
| Thứ 3 | - Bật MFA cho tài khoản root <br> - Tạo IAM user & group quản trị <br> - Thiết lập password policy | 28/04/2026 | 28/04/2026 | <https://cloudjourney.awsstudygroup.com/> |
| Thứ 4 | - Học cấu trúc policy (Effect, Action, Resource, Condition) <br> - Viết policy JSON tùy chỉnh | 29/04/2026 | 29/04/2026 | <https://docs.aws.amazon.com/IAM/> |
| Thứ 5 | Nghỉ lễ (Giải phóng miền Nam) | 30/04/2026 | 30/04/2026 | |
| Thứ 6 | Nghỉ lễ (Quốc tế Lao động) | 01/05/2026 | 01/05/2026 | |

### Kết quả đạt được trong Tuần 2
* Hiểu mô hình trách nhiệm chung — phần nào AWS bảo vệ, phần nào khách hàng bảo vệ.
* Bảo vệ tài khoản: bật MFA cho root, ngừng dùng root cho công việc hằng ngày, tạo IAM user/group quản trị và password policy mạnh.
* Nắm cấu trúc policy IAM và viết policy JSON theo least-privilege giới hạn theo từng tài nguyên cụ thể.
* Tạo các service role đầu tiên cần dùng cho dự án về sau (ví dụ `ecsTaskExecutionRole` cho ECS task), phân biệt được IAM user và IAM role.
* Thực hành kiểm tra quyền hiệu lực bằng IAM Policy Simulator.
