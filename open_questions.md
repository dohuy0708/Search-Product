# ❓ Open Questions for Product Search Engine (Agile Alignment)

Dưới đây là danh sách toàn bộ các câu hỏi mở được rút gọn súc tích và phân nhóm rõ ràng để làm việc, thảo luận và thống nhất yêu cầu (Requirements Sign-off) với khách hàng và các bên liên quan:

---

## 1. 🔍 Gợi Ý Tìm Kiếm (Smart Autocomplete)
* **Q1.1 (Lịch sử tìm kiếm cá nhân):** Hệ thống có ưu tiên hiển thị Lịch sử tìm kiếm gần đây (Search History) của chính người dùng lên đầu hộp gợi ý trước khi hiển thị từ khóa phổ biến không?
* **Q1.2 (Giới hạn & Tính năng xóa):** Số lượng từ khóa lịch sử tối đa được lưu là bao nhiêu? Có cần tính năng xóa lịch sử (cho phép xóa từng từ hoặc xóa tất cả lịch sử) không?
* **Q1.3 (Điều kiện kích hoạt):** Điều kiện kích hoạt để gọi API Autocomplete là người dùng phải nhập tối thiểu bao nhiêu ký tự (ví dụ: tối thiểu từ 2 hay 3 ký tự)?
* **Q1.4 (Tham số Debounce):** Thời gian hoãn gọi API khi người dùng tạm dừng gõ (Debounce time) là bao nhiêu mili-giây? *(Khuyến nghị: 200ms - 300ms để tối ưu số lượng request và đảm bảo tốc độ phản hồi thực tế thay vì 1-2 giây).*

---

## 2. ⚡ Hiệu Năng & Khả Năng Chịu Tải (Performance & Scalability)
* **Q2.1 (Chỉ số CCU vs RPS):** Con số "500 lượt truy cập đồng thời" trong tài liệu được định nghĩa là số lượng người dùng online cùng lúc (CCU) hay số lượng request hệ thống phải xử lý trong 1 giây (RPS)?
* **Q2.2 (Dự phóng tải đỉnh):** Dự kiến tải đỉnh (Peak load) trong các dịp chiến dịch Flash Sale đa quốc gia sẽ tăng gấp bao nhiêu lần con số 500 này để đội ngũ chuẩn bị thiết kế hạ tầng phù hợp?

---

## 3. 🌐 Đa Ngôn Ngữ & Dịch Thuật (Multilingual & Translation)
* **Q3.1 (Cơ chế dịch thuật tối ưu):** Hệ thống sẽ chốt phương án dịch thuật ở thời điểm nào?
  * **Ingestion-time translation:** Dịch và lưu trữ sẵn khi người bán đăng sản phẩm (Ưu tiên: tốc độ tìm kiếm của người mua cực nhanh vì index có sẵn).
  * **Query-time translation:** Dịch trực tiếp khi người dùng gõ tìm kiếm (Ưu tiên: tiết kiệm dung lượng lưu trữ chỉ mục của database).

---

## 4. 📊 Thuật Toán Xếp Hạng & Đấu Thầu (Relevance & Ranking)
* **Q4.1 (Trọng số chi tiết):** Công thức và tỷ lệ trọng số (%) cụ thể giữa các yếu tố xếp hạng (Tiêu đề, Mô tả, Sản phẩm quảng cáo, Tồn kho) là bao nhiêu?
* **Q4.2 (Ưu tiên hiển thị Sponsored):** Sản phẩm tài trợ/quảng cáo của Seller được ưu tiên hiển thị cố định lên top đầu trang kết quả (ví dụ: cố định 3 vị trí đầu) hay chỉ được cộng thêm điểm ưu tiên (boost score) vào thuật toán xếp hạng chung?

---

## 5. 🤖 Vòng Lặp Tự Học AI (Self-Learning Loop)
* **Q5.1 (Ngưỡng nhận diện từ khóa lạ):** Tiêu chí định lượng để hệ thống ghi nhận một cụm từ là "từ khóa lạ" để phân tích là gì? *(Ví dụ: tần suất xuất hiện tối thiểu bao nhiêu lần trong tuần từ những tìm kiếm trả về 0 kết quả).*
* **Q5.2 (Tần suất quét log):** Tiến trình chạy ngầm (cron job/worker) quét và phân tích từ khóa lạ sẽ chạy định kỳ bao lâu một lần? *(Mỗi giờ, mỗi ngày, hay gom lại quét vào nửa đêm khi tải hệ thống thấp)?*

---

## ⚙️ 6. Kênh Quản Trị & Phân Quyền (Admin UI & Access Control)
* **Q6.1 (Tác vụ quản lý từ khóa):** Các tính năng tác vụ cụ thể trên màn hình Admin UI để xử lý các đề xuất từ khóa gồm những gì? *(Ví dụ: Phê duyệt - Approve, Từ chối - Reject, Sửa - Edit, Gộp nhóm từ đồng nghĩa - Merge).*
* **Q6.2 (Phân quyền bảo mật):** Luồng duyệt từ khóa trên Admin UI có cần phân quyền theo cấp bậc nhân sự không? *(Ví dụ: Nhân viên vận hành chỉ được phép sửa/gộp nhóm, cấp Quản lý/Admin mới được bấm phê duyệt áp dụng luật thực tế).*
