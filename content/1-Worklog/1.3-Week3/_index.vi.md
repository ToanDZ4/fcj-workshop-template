---
title: "Worklog Tuần 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu Tuần 3
* Hiểu về mạng trên AWS với Amazon VPC.
* Tìm hiểu subnet (public/private), Internet Gateway, NAT Gateway, route table, security group và network ACL.
* Xây dựng một mạng cô lập để triển khai dự án về sau.

### Công việc thực hiện trong tuần
| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| Thứ 2 | - Khái niệm VPC, dải CIDR, subnet <br> - Subnet public vs private | 04/05/2026 | 04/05/2026 | <https://docs.aws.amazon.com/vpc/> |
| Thứ 3 | - Internet Gateway & route table <br> - **Thực hành:** tạo VPC với subnet public/private | 05/05/2026 | 05/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| Thứ 4 | - NAT Gateway cho subnet private truy cập internet chiều ra <br> - Elastic IP cho NAT | 06/05/2026 | 06/05/2026 | <https://docs.aws.amazon.com/vpc/> |
| Thứ 5 | - Security group vs network ACL (stateful vs stateless) | 07/05/2026 | 07/05/2026 | <https://cloudjourney.awsstudygroup.com/> |
| Thứ 6 | - VPC endpoint (Gateway & Interface) <br> - **Thực hành:** kiểm tra kết nối giữa các subnet | 08/05/2026 | 08/05/2026 | <https://docs.aws.amazon.com/vpc/> |

### Kết quả đạt được trong Tuần 3
* Xây dựng VPC với subnet public và private trải trên hai Availability Zone để đảm bảo tính sẵn sàng cao.
* Cấu hình Internet Gateway và route table để subnet public ra được internet, và NAT Gateway để subnet private tải cập nhật mà vẫn giữ tính riêng tư.
* Hiểu sự khác nhau giữa security group (stateful, cấp instance) và network ACL (stateless, cấp subnet), viết rule vào/ra theo least-privilege.
* Tìm hiểu VPC endpoint và lý do nó giữ lưu lượng tới các dịch vụ AWS (như S3) bên trong mạng AWS.
* Thiết kế mạng này trở thành nền tảng cho tầng backend ECS và cơ sở dữ liệu của dự án.
