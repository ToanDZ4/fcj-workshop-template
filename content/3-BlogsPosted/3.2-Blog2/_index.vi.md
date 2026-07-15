---
title: "Blog 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

# Xây dựng REST API serverless với API Gateway, Lambda và DynamoDB

Trong bài lab này, tôi xây dựng một **REST API hoàn toàn serverless**. Không có server nào phải quản lý: Amazon API Gateway nhận request HTTP, AWS Lambda chạy logic nghiệp vụ, và Amazon DynamoDB lưu dữ liệu. Bạn chỉ trả phí theo từng request.

## Kiến trúc

```
Client → API Gateway → các hàm Lambda → bảng DynamoDB
```

- **Amazon API Gateway** expose các endpoint REST (ví dụ `GET /items`, `POST /items`).
- **AWS Lambda** có một hàm cho mỗi thao tác (list, get, create, delete).
- **Amazon DynamoDB** là kho dữ liệu NoSQL với partition key `id`.

## Các bước chính

1. **Tạo bảng DynamoDB** (`items`) với partition key `id`.
2. **Viết các hàm Lambda** cho từng thao tác và cấp cho mỗi hàm một **execution role** least-privilege chỉ truy cập đúng bảng đó.
3. **Tạo REST API trên API Gateway** và kết nối mỗi route/method tới Lambda tương ứng bằng proxy integration.
4. **Deploy API** lên một stage (ví dụ `prod`) để lấy URL invoke.
5. **Kiểm thử** bằng `curl` / Postman:
   ```bash
   curl -X POST https://<api-id>.execute-api.<region>.amazonaws.com/prod/items \
     -H "Content-Type: application/json" \
     -d '{"id":"1","name":"Sample"}'
   ```
6. (Tùy chọn) **Bảo vệ API** bằng Cognito authorizer để chỉ người dùng đã đăng nhập mới gọi được.

## Bài học rút ra

- Serverless loại bỏ việc quản lý server và tự động co giãn theo lưu lượng.
- Execution role theo least-privilege rất quan trọng — mỗi hàm chỉ nên chạm vào tài nguyên nó cần.
- Lưu ý **cold start của Lambda** ở request đầu tiên; giữ hàm nhỏ gọn và ít phụ thuộc.

> Tôi tái sử dụng mô hình API Gateway + Lambda + DynamoDB này cho các API đơn hàng và sản phẩm của dự án.
