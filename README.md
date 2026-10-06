# Track 1 — Day 20: Product Metrics Pack & Tracking Architecture

## 1. Thông tin Cá nhân & Dự án
- **Họ và tên:** Lê Thị Duyên
- **Mã học viên:** 2A202602411
- **Dự án chọn làm:** **AI Tutor — Nền tảng học trực tuyến VLearn**
- **Trọng tâm sản phẩm:** Trợ lý học tập chẩn đoán & bù đắp lỗ hổng kiến thức tiên quyết theo ngữ cảnh bài giảng (*In-Context Diagnostic & Socratic Review*)

---

## 2. Link Tệp Metrics Pack (Đã cấp quyền xem)

- 📄 **Tệp Metrics Pack (Bản chi tiết trong Repo):** [👉 Xem Tệp Metrics Pack Đầy Đủ](./metrics-pack.md)
- 🔗 **Link Google Docs / Drive (Đã cấp quyền xem):** [Link Google Docs Metrics Pack — Le Thi Duyen](https://docs.google.com/document/d/1_PLACEHOLDER_LINK_METRICS_PACK_VLEARN/edit?usp=sharing)
*(Lưu ý: Toàn bộ nội dung chuẩn hóa của Metrics Pack đã được lưu trữ và đồng bộ nguyên vẹn trong tệp [`metrics-pack.md`](./metrics-pack.md)).*

---

## 3. Cấu trúc Tệp Metrics Pack

Tệp Metrics Pack được xây dựng theo chuẩn 7 phần:
- **00 — Dự án, persona, core job:** Chân dung học viên trực tuyến Minh Thảo và JTBD gỡ tắc kiến thức tiên quyết trong dưới 2 phút.
- **01 — Core Action Card (+ kết quả tự kiểm 5 tiêu chí):** Định nghĩa hành vi *Resolved Diagnostic Interaction* kèm bảng tự kiểm 5 tiêu chí.
- **02 — Action Nature Card + kết luận cadence:** Phân tích bản chất học tập theo phiên và chốt nhịp độ tự nhiên **Weekly Cadence**.
- **03 — Metric System (activation / engagement / NSM / leading / counter):** Hệ thống chỉ số toàn diện với NSM là *Weekly Resolved Learning Hours (WRLH)* và counter-metric kiểm soát đứt gãy luồng học.
- **04 — Retention Definition (6 thành phần):** Chuẩn hóa định nghĩa giữ chân người học theo 6 thành tố chuẩn quốc tế.
- **05 — Product Loop (2 chu kỳ + metric hypothesis):** Vòng lặp giải tỏa tức thì trong buổi học (*In-Session Micro Loop*) và Vòng lặp củng cố tự nhiên giữa các buổi (*Cross-Session Mastery Loop*), tuân thủ nguyên tắc Nurture chỉ khuếch đại Nature.
- **06 — Tracking nhanh (4–8 events + 2 acceptance criteria):** Bảng schema 6 sự kiện theo dõi then chốt và 2 tiêu chí nghiệm thu kỹ thuật (Acceptance Criteria) cho tracking QA.
- **07 — Bảng Tự Kiểm 9 Lỗi Kinh Điển (Phase 5 Gate Check):** Tự đối chiếu và xác nhận vượt qua 9 cạm bẫy thiết kế chỉ số sản phẩm.

---

## 4. Điều Tôi Mang Về Áp Dụng Cho Dự Án Thật

Qua bài toán xây dựng Metrics Pack cho sản phẩm số, 4 bài học lớn tôi đúc kết để áp dụng trực tiếp vào công việc Product Management thực tế:

1. **Phân biệt rạch ròi giữa Vanity Metrics và Core Action có giá trị:**
   - Trong các sản phẩm AI hoặc EdTech, số lượt bấm mở chatbot (Chat sessions / Queries submitted) rất dễ trở thành chỉ số ảo (vanity metric) vì người dùng có thể mở ra rồi thất vọng tắt đi.
   - Khi áp dụng vào dự án thật, tôi sẽ luôn neo vào **Core Action phản ánh giá trị giải quyết trọn vẹn (Resolved Action)**: Không chỉ đo lường số lần hỏi AI, mà phải đo lường việc người dùng hấp thụ câu trả lời và hoàn thành tiếp công việc dang dở.

2. **Tầm quan trọng sống còn của Counter-Metric (Chỉ số kìm hãm / đối trọng):**
   - Nếu chỉ tối ưu hóa NSM hoặc số lượt tương tác AI, đội ngũ sản phẩm rất dễ lạm dụng pop-up, notification hoặc can thiệp quá sâu làm đứt gãy mạch trải nghiệm chính của người dùng.
   - Việc thiết lập **Counter-Metric (như tỷ lệ bỏ học do gián đoạn luồng $\le 8\%$)** là chiếc "phanh an toàn" bắt buộc phải có trong mọi dashboard đo lường tính năng AI.

3. **Thiết kế Product Loop thay vì chỉ xây phễu tuyến tính (Funnel):**
   - Phễu chuyển đổi thông thường chỉ đưa người dùng đi một chiều rồi kết thúc. Để sản phẩm duy trì được retention bền vững, mọi hành vi người dùng bỏ công sức thực hiện (như làm quiz, giải quyết điểm tắc) đều phải trở thành "vốn liếng" tích lũy dữ liệu để kích hoạt vòng lặp kế tiếp (Cross-session loop / Habit loop).

4. **Kỷ luật dữ liệu ngay từ khâu Tracking Schema & Acceptance Criteria:**
   - Tracking không phải là việc "sau khi dev xong rồi tính". Một PM chuyên nghiệp phải định nghĩa cấu trúc event, property và acceptance criteria về độ trễ, chống trùng lặp (debounce) ngay trong giai đoạn thiết kế tính năng, đảm bảo dữ liệu thu về sạch, có thể ghép nối phiên (session stitching) và sẵn sàng cho việc phân tích funnel/retention.
