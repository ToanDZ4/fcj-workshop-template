---
title: "Blog 1"
date: 2026-06-04
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# Bảo mật đám mây với Amazon VPC Encryption Controls

Trong các hệ thống doanh nghiệp hiện đại, mã hóa dữ liệu khi truyền (in transit) là một yêu cầu thiết yếu để đáp ứng các tiêu chuẩn bảo mật như **HIPAA**, **PCI DSS**, **FedRAMP** và **SOC 2**. Tuy nhiên, khi hạ tầng AWS mở rộng tới hàng trăm hoặc hàng nghìn tài nguyên, việc xác định lưu lượng nào đã được mã hóa và tài nguyên nào vẫn đang truyền dữ liệu dạng plaintext trở nên rất khó khăn.

Để giải quyết thách thức này, AWS đã giới thiệu **Amazon VPC Encryption Controls** — một tính năng bảo mật mới giúp các tổ chức giám sát, kiểm soát và bắt buộc mã hóa khi truyền giữa các tài nguyên AWS trong cùng một VPC hoặc giữa nhiều VPC trong một Region.

---

## Amazon VPC Encryption Controls là gì?

Amazon VPC Encryption Controls là một tính năng bảo mật cho phép bạn:

* Giám sát trạng thái mã hóa của lưu lượng mạng trong một VPC.
* Xác định các tài nguyên vẫn cho phép truyền dữ liệu không mã hóa.
* Bắt buộc một chính sách yêu cầu mã hóa dữ liệu trên toàn bộ môi trường AWS.
* Đơn giản hóa quá trình kiểm toán và đáp ứng yêu cầu tuân thủ.

Tính năng này tận dụng hai cơ chế mã hóa chính:

* **Mã hóa ở tầng ứng dụng** như TLS.
* **Mã hóa dựa trên phần cứng bởi AWS Nitro System**, được tích hợp trong các thế hệ instance hiện đại.

Ngoài Amazon EC2, AWS đã mở rộng khả năng mã hóa của Nitro sang nhiều dịch vụ khác, bao gồm:

* Application Load Balancer (ALB)
* Network Load Balancer (NLB)
* AWS Fargate
* Amazon EKS
* Amazon ECS
* Amazon RDS
* Amazon OpenSearch Service
* Amazon MSK
* AWS Transit Gateway

Nhờ đó, các tổ chức có thể triển khai mã hóa một cách nhất quán ở quy mô lớn mà không cần xây dựng một hệ thống PKI phức tạp hay phụ thuộc vào nhiều giải pháp bảo mật của bên thứ ba.

---

## Hai chế độ hoạt động chính

### 1. Monitor Mode – Quan sát trước khi bắt buộc

AWS khuyến nghị mọi VPC hiện có nên bắt đầu với **Monitor Mode**.

Ở chế độ này, VPC Encryption Controls **không chặn lưu lượng**, mà chỉ ghi nhận và đánh giá trạng thái mã hóa của các kết nối.

Một trường dữ liệu mới tên là **encryption-status** được thêm vào **VPC Flow Logs** với các giá trị sau:

| Giá trị | Ý nghĩa |
| --- | --- |
| 0 | Không mã hóa |
| 1 | Được mã hóa bởi AWS Nitro |
| 2 | Mã hóa tầng ứng dụng (TLS) |
| 3 | Nitro + TLS |
| Không có giá trị | Không xác định |

Thông qua Flow Logs, quản trị viên có thể nhanh chóng xác định:

* Luồng dữ liệu nào đã được bảo vệ.
* Dịch vụ nào vẫn cho phép truyền dạng plaintext.
* Tài nguyên nào cần nâng cấp trước khi bắt buộc chính sách mã hóa.

Ngoài ra, AWS cung cấp API sau:

```
GetVpcResourcesBlockingEncryptionEnforcement
```

API này giúp liệt kê các tài nguyên chưa đáp ứng yêu cầu mã hóa trước khi chuyển sang Enforce Mode.

---

## Chuyển sang môi trường mã hóa hoàn toàn

Sau khi đánh giá hệ thống bằng Monitor Mode, tổ chức có thể tiến hành chuyển đổi hạ tầng.

### Các dịch vụ được AWS tự động nâng cấp

AWS tự động chuyển hạ tầng bên dưới sang AWS Nitro cho các dịch vụ sau:

* Application Load Balancer
* Network Load Balancer
* AWS Fargate
* Amazon EKS Control Plane

Quá trình này diễn ra với:

* Không có thời gian gián đoạn (zero downtime).
* Không cần thay đổi cấu hình.
* Không cần can thiệp thủ công.

### Các dịch vụ cần nâng cấp thủ công

Một số tài nguyên vẫn yêu cầu khách hàng chủ động chuyển đổi, bao gồm:

* Các instance EC2 thế hệ cũ
* Auto Scaling Groups
* Amazon RDS
* Amazon ElastiCache
* Amazon Redshift
* Amazon ECS chạy trên EC2
* Amazon OpenSearch Service
* Amazon EMR

Nếu các tài nguyên này đang dùng instance không hỗ trợ Nitro, tổ chức cần:

* Chuyển sang các loại EC2 hiện đại có hỗ trợ AWS Nitro System.
* Hoặc triển khai TLS ở tầng ứng dụng.

---

## Enforce Mode – Bắt buộc chính sách mã hóa

Khi quá trình đánh giá và chuyển đổi hoàn tất, tổ chức có thể kích hoạt **Enforce Mode**.

Đây là giai đoạn AWS chủ động thực thi chính sách bảo mật.

Khi bật Enforce Mode:

* Bạn không thể khởi chạy các instance EC2 thế hệ cũ không hỗ trợ AWS Nitro.
* Bạn không thể triển khai các tài nguyên cho phép lưu lượng không mã hóa.
* Chỉ các kết nối đã mã hóa mới được phép hoạt động trong VPC.

Nhờ đó, toàn bộ lưu lượng nội bộ được bảo vệ nhất quán mà không hoàn toàn phụ thuộc vào việc người dùng cấu hình TLS đúng cách.

---

## Các ngoại lệ được hỗ trợ (Exclusions)

Trong thực tế, một số tài nguyên cần giao tiếp ra ngoài hạ tầng AWS và không thể được quản lý hoàn toàn bởi VPC Encryption Controls.

AWS cho phép bạn cấu hình **Exclusions** cho các tài nguyên như:

* Internet Gateway
* NAT Gateway
* Egress-only Internet Gateway
* Virtual Private Gateway
* VPC Peering
* AWS Lambda trong VPC
* VPC Lattice
* Amazon EFS

Các ngoại lệ này được ghi lại đầy đủ trong quá trình kiểm toán, giúp tổ chức chứng minh mức độ tuân thủ khi được audit.

---

## Lợi ích cho tổ chức

### Tăng cường bảo mật

* Đảm bảo toàn bộ lưu lượng nội bộ được mã hóa.
* Giảm thiểu nguy cơ rò rỉ dữ liệu trong quá trình truyền.

### Đơn giản hóa vận hành

Tổ chức không còn phải:

* Xây dựng hệ thống PKI riêng.
* Quản lý số lượng lớn chứng chỉ số.
* Triển khai nhiều giải pháp bảo mật rời rạc.

### Hỗ trợ kiểm toán và tuân thủ

VPC Encryption Controls cung cấp:

* Báo cáo trạng thái mã hóa.
* VPC Flow Logs phục vụ kiểm toán.
* Bằng chứng đáp ứng các tiêu chuẩn như HIPAA, PCI DSS và FedRAMP.

### Tận dụng AWS Nitro

Vì việc mã hóa được xử lý ở mức phần cứng, gần như không có tác động đến hiệu năng của ứng dụng.

---

## Kết luận

Amazon VPC Encryption Controls là một bước tiến đáng kể trong việc đơn giản hóa bảo mật mạng trên AWS. Thay vì phải xây dựng các hệ thống giám sát và kiểm soát mã hóa phức tạp, tổ chức có thể tận dụng giải pháp tích hợp sẵn này để:

* Giám sát trạng thái mã hóa của toàn bộ lưu lượng mạng.
* Phát hiện các điểm mù về bảo mật.
* Bắt buộc chính sách mã hóa một cách tập trung.
* Đáp ứng các yêu cầu tuân thủ nghiêm ngặt.

Nếu tổ chức của bạn đang hướng tới các chứng nhận như **HIPAA**, **PCI DSS** hay **FedRAMP**, triển khai **Monitor Mode** là bước đầu tiên lý tưởng để đánh giá mức độ bảo mật của hạ tầng trước khi chuyển sang **Enforce Mode**.

---

## Tài liệu tham khảo

* <https://docs.aws.amazon.com/vpc/latest/userguide/vpc-encryption-controls.html>
* <https://aws.amazon.com/blogs/aws/introducing-vpc-encryption-controls-enforce-encryption-in-transit-within-and-across-vpcs-in-a-region/>
