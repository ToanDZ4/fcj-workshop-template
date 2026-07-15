---
title: "Blog 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# Host website tĩnh trên Amazon S3 và Amazon CloudFront

Trong bài lab này, tôi host một website tĩnh (HTML/CSS/JS) trên Amazon S3 và phân phối toàn cầu qua HTTPS bằng Amazon CloudFront. Đây là mô hình rất phổ biến, chi phí thấp cho landing page, trang tài liệu và ứng dụng single-page.

## Kiến trúc

```
Người dùng → CloudFront (HTTPS, cache tại edge) → S3 bucket (private, file tĩnh)
```

- **Amazon S3** lưu các file website. Bucket luôn ở trạng thái **private**; người dùng không truy cập trực tiếp.
- **Amazon CloudFront** là CDN đặt phía trước S3. Nó xử lý HTTPS, cache nội dung tại các edge location gần người dùng, và đọc từ S3 thông qua **Origin Access Control (OAC)**.

## Các bước chính

1. **Tạo bucket S3** và upload các file website (`index.html`, asset). Vẫn bật *Block Public Access*.
2. **Tạo CloudFront distribution** với origin là bucket S3.
3. **Bật Origin Access Control (OAC)** để chỉ CloudFront được đọc bucket, sau đó cập nhật **bucket policy** cho phép service principal của CloudFront.
4. **Thiết lập default root object** là `index.html`.
5. (Tùy chọn) **Thêm tên miền riêng** với Amazon Route 53 và **chứng chỉ ACM** để dùng HTTPS trên domain của bạn.
6. **Kiểm thử** URL CloudFront và xác nhận trang tải qua HTTPS.

## Bài học rút ra

- Giữ bucket S3 private và chỉ phục vụ qua CloudFront + OAC an toàn hơn việc để bucket public.
- Cache của CloudFront giảm rõ rệt độ trễ cho người dùng ở xa region của bucket.
- Sau khi cập nhật file trên S3, có thể cần **cache invalidation** (hoặc đặt tên file có version) để thấy thay đổi ngay.

> Đây chính là mô hình tôi dùng cho frontend của dự án Nền tảng Thương mại điện tử Serverless.
