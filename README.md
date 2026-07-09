# 🛒 Amaze Advanced Product Search Engine — Project Overview

Tài liệu này tổng hợp quy trình làm việc toàn diện khi triển khai tính năng **Tìm kiếm Sản phẩm Thông minh (Smart Product Search)** cho nền tảng thương mại điện tử đa quốc gia. Tài liệu hướng tới việc làm rõ yêu cầu nghiệp vụ nhanh chóng và cộng tác hiệu quả theo mô hình phát triển **Agile**.

---

## 🎯 Quy Trình Làm Việc & Các Tài Liệu Bàn Giao (Project Outline & Workflow)

Để hiện thực hóa tính năng này, quy trình từ đầu đến cuối được tổ chức thành **4 bước cốt lõi** dưới đây. Sếp có thể truy cập nhanh vào từng tài liệu đính kèm tương ứng:

### 1️⃣ Phân tích & Đặt câu hỏi làm rõ (Analysis & Clarifying)
* **Quy trình:** Nghiên cứu yêu cầu ban đầu của khách hàng, phân tích các điểm mù (blind spots) và trường hợp biên (edge cases). Từ đó, lập danh sách câu hỏi phản biện chi tiết để thống nhất nghiệp vụ.
* **Tài liệu bàn giao:** 📝 **[Open Questions & Clarifications](open_questions.md)** *(Danh sách câu hỏi mở rộng làm rõ yêu cầu để gửi khách hàng).*

### 2️⃣ Phân tách tính năng & Thống nhất giải pháp trực quan (Client Alignment)
* **Quy trình:** Sơ đồ hóa kiến trúc hệ thống và luồng dữ liệu (data flow) thành các sơ đồ tương tác trực quan (mockup/dashboard) để khách hàng và sếp dễ hình dung giải pháp mà không cần đọc văn bản khô khan.
* **Trình diễn trực quan (Tải file chạy trực tiếp trên trình duyệt):** 
  * 📈 **[Business Value Presentation](search_business_presentation.html)** *(Bản đồ giá trị kinh doanh và các luồng nghiệp vụ tương tác).*
  * 🛠️ **[System Architecture Map](search_architecture_presentation.html)** *(Sơ đồ thiết kế kiến trúc hệ thống tìm kiếm).*

### 3️⃣ Đặc tả tài liệu PRD & Chia phase MVP (PRD & MVP Planning)
* **Quy trình:** Viết tài liệu đặc tả yêu cầu nghiệp vụ (BRD/PRD) chi tiết dưới dạng các **User Stories** đi kèm tiêu chí nghiệm thu **Acceptance Criteria (Gherkin format Given-When-Then)**, đồng thời phân chia các giai đoạn triển khai (MVP vs. Future Phases) cho dự án Agile.
* **Tài liệu đặc tả chi tiết:** 📄 **[Business Requirements Document (BRD)](product_search_requirements.md)** *(Tài liệu đặc tả nghiệp vụ chính thức).*

---

## 🤖 Kỹ Năng Sử Dụng AI Trong Dự Án (AI Copilot Integration)

Dự án này ứng dụng AI làm trợ lý đồng hành xuyên suốt quá trình thiết kế tài liệu và xây dựng mockup.

### 1. Các AI Skills được sử dụng để tối ưu hiệu suất:
* **`effective-html`** (`npx skills add plannotator/effective-html`):
  * *Hiệu quả:* Tạo nhanh các trang slide/sơ đồ HTML tương tác cao, giúp khách hàng nước ngoài và sếp hiểu nhanh kiến trúc hệ thống mà không cần đọc tài liệu kỹ thuật khô khan.
  * *Output:* Trang HTML tương tác [search_business_presentation.html](search_business_presentation.html).
* **`grill-me`** (`npx skills@latest add mattpocock/skills --skill grill-me`):
  * *Hiệu quả:* Thực hiện phỏng vấn phản biện sâu với AI để phát hiện các lỗ hổng nghiệp vụ và hoàn thiện đặc tả.
  * *Output:* Tài liệu câu hỏi mở rộng [open_questions.md](open_questions.md).

### 2. Quy trình cộng tác với AI khi làm tài liệu nghiệp vụ (BRD):
Quy trình làm việc với AI được thiết kế chặt chẽ qua các bước:
1. **Đưa ra yêu cầu rõ ràng (Clear Requirements):** Cung cấp ngữ cảnh, mục tiêu kinh doanh và mô hình Agile cho AI.
2. **AI tạo bản phác thảo đầu tiên (Initial Draft):** Nhận bản thảo khung BRD cơ bản.
3. **Đọc, review và đánh giá (Review & Evaluate):** Đánh giá tính thực tế của các stories và tiêu chí nghiệm thu.
4. **Prompt điều chỉnh & cập nhật (Feedback Loop):** Yêu cầu AI sửa lỗi, dịch thuật sang tiếng Anh thân thuộc và cập nhật luật xếp hạng.
5. **Minh chứng lịch sử tương tác (Evidence Logs):** 🤖 **[AI Collaboration & Prompt Log](ai_collaboration_log.md)** *(Nhấp vào để xem chi tiết các câu lệnh prompt và phản hồi từ AI).*
