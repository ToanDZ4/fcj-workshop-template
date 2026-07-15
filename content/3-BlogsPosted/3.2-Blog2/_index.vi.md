---
title: "Blog 2"
date: 2026-07-09
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

# Web Search trên Amazon Bedrock AgentCore: AI Agent giờ có thể duyệt web mà dữ liệu không rời khỏi AWS

Chào mọi người, trong lúc tìm hiểu về Agentic AI trên AWS, mình nhận thấy AWS vừa công bố General Availability (GA) cho tính năng Web Search trên Amazon Bedrock AgentCore. Đây là một công cụ tìm kiếm web được quản lý hoàn toàn (fully managed), cho phép các AI agent tra cứu thông tin mới nhất trên Internet trong khi vẫn giữ toàn bộ truy vấn bên trong môi trường AWS của khách hàng. Mình tóm tắt các ý cốt lõi để chia sẻ với cộng đồng.

## 1. Amazon Bedrock AgentCore là gì?

Amazon Bedrock AgentCore là nền tảng của AWS để xây dựng, triển khai và vận hành AI agent ở quy mô production. Thay vì lập trình viên phải tự quản lý hạ tầng (runtime, memory, identity, khả năng quan sát hành vi agent, v.v.), AgentCore cung cấp những thứ này dưới dạng dịch vụ được quản lý. Nó hoạt động với tất cả các framework mã nguồn mở phổ biến như Strands Agents, LangGraph, CrewAI hay LlamaIndex, cùng với bất kỳ foundation model nào.

Một vấn đề cố hữu của AI agent là kiến thức của model bị "đóng băng" tại thời điểm huấn luyện. Một agent tư vấn tài chính không biết tin tức sáng nay; một agent hỗ trợ khách hàng không biết chính sách vừa thay đổi tuần trước. Trước đây, để agent tìm kiếm web, lập trình viên phải tích hợp các search API của bên thứ ba — và đây chính là vấn đề mà tính năng mới này giải quyết.

## 2. Tính năng này có gì mới?

Web Search được cung cấp dưới dạng một connector target dựng sẵn trên AgentCore Gateway, giao tiếp qua chuẩn Model Context Protocol (MCP). Agent chỉ cần gửi truy vấn bằng ngôn ngữ tự nhiên, và Web Search trả về các đoạn (snippet) liên quan nhất kèm URL nguồn, tiêu đề và ngày xuất bản — cung cấp đủ ngữ cảnh để model suy luận và tạo ra câu trả lời có căn cứ kèm trích dẫn.

**Các điểm kỹ thuật nổi bật:**

* **Xây dựng trên hạ tầng tìm kiếm của chính Amazon:** Nó dùng chung nền tảng tìm kiếm đang vận hành Alexa+, Amazon Quick và Kiro, được tối ưu cho truy hồi phục vụ agent — trả về snippet giá trị cao thay vì danh sách link thô, mang lại "nhiều trí tuệ hơn trên mỗi token".
* **Grounding đa nguồn:** Kết hợp chỉ mục web công khai với Amazon Knowledge Graph — dữ liệu thực thể có cấu trúc và thông tin đã xác minh, bao gồm cả dữ liệu thời gian thực như giá cổ phiếu hay tỷ số thể thao.
* **Zero data egress (dữ liệu không rời AWS):** Prompt của người dùng và truy vấn tìm kiếm không được gửi tới nhà cung cấp tìm kiếm bên ngoài AWS — đây là điểm khác biệt lớn nhất so với việc tự tích hợp Google hay Bing API.
* **Chuẩn MCP:** Vì đi qua Gateway bằng một giao thức mở, tính năng này hoạt động với mọi framework agent và không bị khóa vào một SDK cụ thể.

## 3. Ứng dụng thực tế

So với cách làm cũ, giá trị vận hành rất rõ ràng:

* **Loại bỏ phần "đường ống" (plumbing):** Không cần đăng ký một nhà cung cấp tìm kiếm riêng, hay viết logic tùy chỉnh cho điều phối, xác thực, retry và tính phí chỉ để tìm kiếm.
* **Đáp ứng yêu cầu tuân thủ:** Với các ngành như tài chính, y tế và bảo hiểm — nơi việc gửi prompt của người dùng ra dịch vụ bên ngoài là một rào cản pháp lý — kiến trúc zero data egress đơn giản hóa đáng kể việc quản trị.
* **Câu trả lời có trích dẫn:** URL nguồn và ngày xuất bản đi kèm mỗi kết quả giúp giảm hiện tượng "ảo giác" (hallucination) và tăng độ tin cậy khi agent trả lời về sự kiện thời sự.
* **Các tình huống điển hình:** Agent nghiên cứu thị trường cần tin tức mới nhất, chatbot hỗ trợ cần tra cứu thông số sản phẩm vừa ra mắt, hoặc agent sáng tạo nội dung theo dõi các sự kiện đang diễn ra.

Một khách hàng thực tế được AWS nhắc đến là Gen Digital (công ty mẹ của Norton): họ dùng Web Search cho sản phẩm Norton Revamp để gợi ý nội dung xây dựng thương hiệu cá nhân dựa trên những gì đang diễn ra, và họ đánh giá cao việc truy vấn không bao giờ rời khỏi môi trường AWS tin cậy của mình.

## 4. Hạn chế và lưu ý khi triển khai

* **Giới hạn khu vực:** Tại thời điểm GA, Web Search chỉ có ở region US East (N. Virginia). Với những ai ở Việt Nam đang dùng `ap-southeast-1`, chúng ta cần theo dõi lộ trình mở rộng region hoặc chấp nhận độ trễ cao hơn với các lệnh gọi cross-region.
* **Không thay thế Knowledge Bases:** Web Search giải quyết bài toán kiến thức công khai và thời sự; với dữ liệu nội bộ doanh nghiệp, bạn vẫn cần kết hợp với Bedrock Knowledge Bases (RAG) — hai phần này bổ sung cho nhau chứ không loại trừ.
* **Chi phí trả theo mức dùng:** Mô hình giá không yêu cầu cam kết trước, nhưng agent có thể quyết định tìm kiếm nhiều lần trong một phiên. Bạn cần giới hạn vòng lặp tool-use và giám sát chi phí như bất kỳ workload agentic nào.
* **Vẫn cần đánh giá chất lượng:** Kết quả có trích dẫn giúp dễ kiểm chứng hơn, nhưng khi agent dùng nguồn web công khai, việc lọc các nguồn kém chất lượng vẫn là trách nhiệm thiết kế của bạn (có thể kết hợp với AgentCore Evaluations và Guardrails).

## 5. Đánh giá cá nhân

Theo mình, đây là mảnh ghép còn thiếu mà bất kỳ ai từng xây dựng agent "tìm kiếm web" đều sẽ thấy giá trị ngay. Phần khó của tính năng này chưa bao giờ là gọi một search API — mà là công việc nền tẻ nhạt: quản lý key, phân tích kết quả, xếp hạng lại, và đau đầu nhất là giải thích với bộ phận bảo mật rằng dữ liệu người dùng đang đi đâu. Việc AWS gói mọi thứ vào một connector target chuẩn MCP, chạy trên hạ tầng tìm kiếm của chính Amazon, là cách làm "đúng đắn" cho môi trường doanh nghiệp.

Những điểm mình sẽ tiếp tục theo dõi là chất lượng kết quả tìm kiếm so với các search API chuyên dụng, và tốc độ mở rộng region — vì với ứng dụng chat thời gian thực, một vòng tìm kiếm vòng qua bán cầu kia có thể ảnh hưởng rõ đến trải nghiệm người dùng.

## Kết luận

Web Search trên Amazon Bedrock AgentCore là một bước tiến đáng kể giúp AI agent thoát khỏi giới hạn kiến thức tại thời điểm huấn luyện mà không đánh đổi an toàn dữ liệu. Với tích hợp qua chuẩn MCP, grounding đa nguồn kèm trích dẫn, và kiến trúc zero data egress, đây sẽ là lựa chọn mặc định xứng đáng cho bất kỳ ai đưa agent từ demo lên production trên AWS. Mình tin rằng trong tương lai gần, "agent có khả năng tìm kiếm web an toàn" sẽ trở thành tiêu chuẩn chứ không còn là tính năng bổ sung.

Hy vọng bản tóm tắt này giúp mọi người có cái nhìn nhanh về hướng đi của AWS trong lĩnh vực Agentic AI!

---

## Tài liệu tham khảo

* <https://aws.amazon.com/blogs/aws/announcing-web-search-on-amazon-bedrock-agentcore-ground-your-ai-agents-in-current-accurate-web-knowledge/>
* <https://aws.amazon.com/blogs/machine-learning/new-in-amazon-bedrock-agentcore-build-agents-with-broader-knowledge-and-continuous-learning/>
