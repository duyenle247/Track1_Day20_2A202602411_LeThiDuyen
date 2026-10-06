# AI Support Log — Nhật ký Sử dụng AI & Kiểm chứng Cá nhân

- **Họ và tên:** Lê Thị Duyên
- **Mã học viên:** 2A202602411
- **Bài tập:** Track 1 — Day 20 (Metrics Pack & Tracking Architecture)

---

## 1. Tuyên bố tuân thủ nguyên tắc sử dụng AI

Tôi cam kết tuân thủ nghiêm ngặt các quy tắc học thuật và đạo đức nghề nghiệp:
- **Phạm vi sử dụng:** Sử dụng AI như một công cụ hỗ trợ tư duy phản biện (sounding board), gợi ý các góc nhìn về cấu trúc chỉ số, rà soát tính khả thi của Tracking Schema và đối chiếu các tiêu chí kỹ thuật.
- **Phạm vi KHÔNG sử dụng:** Không phó mặc cho AI tự quyết định các chỉ số đo lường cốt lõi. Toàn bộ các quyết định về Core Action, việc chọn chu kỳ đo lường (Cadence), công thức North Star Metric và ngưỡng kiểm soát rủi ro (Counter-metric) đều do tôi tự phân tích dựa trên đặc thù bài toán người học và dữ liệu phỏng vấn người dùng thực tế từ các ngày trước.
- **Tự chịu trách nhiệm:** Mọi nội dung, công thức tính toán và tiêu chí nghiệm thu trong Metrics Pack đều được tôi kiểm chứng và phản biện lại các gợi ý thiên kiến của AI.

---

## 2. Bảng phân định công việc & Đánh giá chất lượng hỗ trợ của AI

| Hạng mục công việc (Day 20) | AI làm hay bạn làm? | AI đã giúp gì? | AI làm sai / hời hợt / thiên kiến ở đâu? | Bạn đã kiểm chứng, điều chỉnh và quyết định lại thế nào? |
| :--- | :--- | :--- | :--- | :--- |
| **Chặng 1: Xác định Core Action & Tự kiểm 5 tiêu chí** | **Bạn làm chính, AI phản biện** | Hỗ trợ cung cấp khung kiểm tra 5 tiêu chí chuẩn mực cho Core Action. | AI gợi ý Core Action là *"Học viên gửi câu hỏi cho AI Tutor"* hoặc *"Học viên mở popup AI"*. Đây là các hành vi bề nổi mang tính vanity metric, không đo lường được việc người học có thực sự giải tỏa được điểm nghẽn kiến thức hay không. | Tôi đã bác bỏ và định nghĩa lại Core Action chuẩn xác: **"Resolved Diagnostic Interaction"** — bắt buộc phải gồm cả chuỗi: chẩn đoán $\rightarrow$ trả lời câu hỏi $\rightarrow$ bấm "Đã hiểu, tiếp tục bài học" để đảm bảo gắn chặt với giá trị cốt lõi. |
| **Chặng 2: Action Nature & Xác định Cadence** | **Bạn làm 100%** | Phân tích các mô hình chu kỳ sử dụng sản phẩm thông thường (Daily, Weekly, Monthly). | AI ban đầu đề xuất tính toán theo nhịp **Daily (DAU / Daily Active)** theo thói quen của các ứng dụng mạng xã hội hoặc game ngôn ngữ (như Duolingo). | Tôi nhận diện đây là sai lầm nghiêm trọng đối với nền tảng học chuyên sâu (như VLearn). Người học không thể học hàng ngày mà học theo lịch 2–3 buổi/tuần. Tôi đã chốt lại là **Weekly Cadence** để phản ánh đúng nhịp độ tiến độ khóa học. |
| **Chặng 3: Thiết lập Metric System (NSM, Leading, Counter)** | **Cả hai cùng làm** (Bạn chủ trì) | Gợi ý các cách kết hợp giữa chỉ số số lượng (Volume) và chất lượng (Quality) trong công thức NSM. | AI đề xuất North Star Metric là *"Tổng số câu hỏi AI được tạo ra mỗi tuần"*. Nếu dùng chỉ số này, đội ngũ sẽ bị khuyến khích spam câu hỏi vô bổ, làm loãng trải nghiệm học. | Tôi điều chỉnh NSM thành **"Weekly Resolved Learning Hours"** (kết hợp thời lượng học hoàn thành với tỷ lệ gỡ tắc thành công), đồng thời bổ sung **Counter-Metric: Flow Disruption Drop-off Rate $\le 8\%$** để bảo vệ trải nghiệm luồng học không bị đứt gãy. |
| **Chặng 4: Định nghĩa Retention 6 thành phần** | **Bạn làm chính, AI hỗ trợ format** | Cung cấp cấu trúc 6 thành phần tiêu chuẩn quốc tế: Who, Core Event, Cadence, Bracket, Calculation, Target. | AI để trống phần Target Baseline hoặc đưa ra con số phi thực tế như *"Retention 70% sau 8 tuần"* mà không có căn cứ cho ngành EdTech khóa học chuyên sâu. | Tôi đã căn chỉnh mục tiêu đường cong giữ chân người học phẳng dần ở mức **$\ge 30\%$ ở Tuần 4** — mức chuẩn mực lành mạnh cho sản phẩm EdTech có trả phí/kỹ thuật cao. |
| **Chặng 5: Thiết kế 2 Product Loops & Giả thuyết số liệu** | **Bạn thiết kế, AI định dạng** | Hỗ trợ mô hình hóa trực quan dòng chảy sự kiện trong 2 chu kỳ: In-session và Cross-session loop. | AI viết câu giả thuyết số liệu rất mơ hồ: *"Giúp người học tiến bộ hơn và yêu thích sản phẩm hơn"*. | Tôi đã viết lại giả thuyết đo lường theo đúng cấu trúc định lượng chuẩn: *Nếu [rút ngắn thời gian chẩn đoán $<45$s với độ chính xác $\ge 85\%$] $\rightarrow$ thì [Lecture Completion Rate tăng từ 42% lên 65%]*. |
| **Chặng 6: Tracking Schema & Acceptance Criteria** | **Bạn thiết kế, AI rà soát cú pháp** | Rà soát tên biến (`snake_case`), cấu trúc properties đính kèm cho từng event. | AI bỏ quên các trường dữ liệu quan trọng như `session_id`, `is_correct`, và không lường trước trường hợp spam click hay event mồ côi (orphaned events). | Tôi đã bổ sung 2 tiêu chí nghiệm thu kỹ thuật (Acceptance Criteria) khắt khe: **AC1** (Độ trễ $<1.5$s kèm cơ chế Debounce) và **AC2** (Ràng buộc toàn vẹn session stitching với tỷ lệ mồ côi $<0.5\%$). |

---

## 3. Bài học cá nhân về việc cộng tác với AI trong Product Analytics

1. **AI rất thích các chỉ số "đẹp mã" (Vanity Metrics):**  
   Khi được hỏi về chỉ số, các mô hình ngôn ngữ lớn luôn có xu hướng đưa ra các chỉ số dễ đo lường nhất như Pageviews, Clicks, Message Counts. Một PM có tư duy vững phải luôn đặt câu hỏi ngược lại: *"Chỉ số này tăng thì doanh nghiệp và người dùng có thực sự nhận thêm giá trị không?"*
   
2. **AI không có trực giác về ngữ cảnh người dùng thật (Context Blindness):**  
   AI dễ áp đặt công thức của sản phẩm giải trí/mạng xã hội (đo lường DAU hàng ngày) vào sản phẩm giáo dục chuyên sâu. Nếu PM thiếu kinh nghiệm và nghe theo AI, sản phẩm sẽ thiết kế các tính năng push notification quấy rầy người học sai thời điểm.

3. **Giá trị lớn nhất của AI là người phản biện kỹ thuật (QA / Sounding Board):**  
   AI phát huy hiệu quả tốt nhất khi được giao vai trò rà soát góc khuất: tìm kiếm các rủi ro kỹ thuật trong tracking, kiểm tra xem các event property có bị thiếu sót ngữ cảnh không, và giúp chuẩn hóa văn phong báo cáo theo các thông lệ quốc tế.
