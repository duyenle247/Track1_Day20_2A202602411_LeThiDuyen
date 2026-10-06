# Metrics Pack — AI Tutor (VLearn)

> **Học viên:** Lê Thị Duyên  
> **Mã học viên:** 2A202602411  
> **Dự án:** AI Tutor — Nền tảng học trực tuyến VLearn  
> **Use case phân tích sâu:** In-Context Prerequisite Diagnosis (Chẩn đoán & gỡ tắc lỗ hổng kiến thức tiên quyết ngay trong luồng bài giảng)

---

## 00 — Dự án, Persona, Core Job (Phase 0)

1. **Dự án:** VLearn AI Tutor — Trợ lý học tập thông minh tích hợp trực tiếp trên nền tảng bài giảng trực tuyến VLearn dành cho các môn công nghệ/kỹ thuật.
2. **Persona:** Minh Thảo — Sinh viên CNTT năm 3 / Người chuyển ngành tự học lập trình và AI trực tuyến vào buổi tối.
3. **Core job:** *"Khi đang nghe bài giảng kỹ thuật phức tạp, tôi bị nghẽn lại vì một khái niệm lạ không hiểu, nhưng tôi không biết mình đang thiếu kiến thức nền tảng nào để tự tra cứu, và tôi mất 1–2 tiếng mò mẫm ngoài Google/ChatGPT rồi nản lòng bỏ dở bài học."*

---

## 01 — Core Action Card (+ Kết quả tự kiểm 5 tiêu chí) (Phase 1)

### 1. Phân biệt bốn khái niệm cốt lõi

| Khái niệm | Câu hỏi | Trả lời cho VLearn AI Tutor |
| :--- | :--- | :--- |
| **Core job** | User đang cố hoàn thành việc gì? | Vượt qua điểm nghẽn kiến thức tiên quyết để hiểu bài và không bỏ dở bài giảng. |
| **Core action** | User làm gì trong sản phẩm để tiến tới giá trị? | Hoàn thành 1 câu chẩn đoán micro-quiz của AI và bấm xác nhận "Đã hiểu, tiếp tục bài học" (*Resolved Diagnostic Interaction*). |
| **Core value** | User nhận được lợi ích gì? | Nhận diện đúng lỗ hổng nền tảng, giải tỏa ngay điểm tắc nhận thức trong $\le 60$s, bảo toàn luồng học liên tục. |
| **Core value event** | Sự kiện nào chứng minh value đã xảy ra? | `diagnostic_session_resolved` (với `resolved_success = true` và thời lượng xem tiếp bài giảng $\ge 5$ phút). |

### 2. Core Action Card

| Thành phần | Câu trả lời của bạn |
| :--- | :--- |
| **Target user** | Học viên trực tuyến đang xem video bài giảng kỹ thuật trên VLearn. |
| **Core job** | Gỡ tắc lỗ hổng kiến thức tiên quyết đang chặn đứng mạch tiếp thu bài giảng. |
| **Core action** | **Hoàn thành chẩn đoán và giải tỏa điểm tắc (Resolved Diagnostic Interaction)**. |
| **Object** | Điểm khó hiểu / khái niệm tiên quyết trên slide bài giảng hiện tại. |
| **Preconditions** | Học viên đang dừng video tại slide phức tạp và mở widget chẩn đoán AI. |
| **Completion rule** | Học viên chọn đáp án micro-quiz $\rightarrow$ đọc phản hồi ngắn $\rightarrow$ bấm nút "Đã hiểu, tiếp tục bài học". |
| **Core value** | Làm chủ kiến thức nền tảng tức thì, chuyển từ bế tắc sang tự tin học tiếp. |
| **Evidence of value** | Học viên tiếp tục bấm Play video và hoàn thành tối thiểu 5 phút bài giảng tiếp theo. |
| **Candidate event** | `diagnostic_session_resolved` |

### 3. Tự kiểm 5 tiêu chí Core Action

| STT | Tiêu chí đánh giá | Kết quả | Giải trình chi tiết |
| :---: | :--- | :---: | :--- |
| **1** | **Gần core value** | **ĐẠT** | Hành vi kết thúc bằng việc giải tỏa điểm nghẽn nhận thức, chứng minh học viên đã nhận trọn vẹn giá trị sư phạm. |
| **2** | **Có thể lặp lại** | **ĐẠT** | Xuất hiện lặp lại tự nhiên mỗi khi học viên gặp khái niệm khó mới trong bài (1–3 lần/buổi học). |
| **3** | **Có thể quan sát** | **ĐẠT** | Hệ thống ghi nhận chính xác thời điểm hoàn tất qua event `diagnostic_session_resolved`. |
| **4** | **Có ý nghĩa** | **ĐẠT** | Tần suất gỡ tắc thành công tăng đồng nghĩa với tỷ lệ hoàn thành bài học tăng và tỷ lệ bỏ học giảm. |
| **5** | **Có thể tác động** | **ĐẠT** | Team có thể tối ưu thuật toán chẩn đoán, chất lượng câu hỏi micro-quiz và giảm độ trễ phản hồi của AI. |

> **GATE 1 — Phản biện Core Action đứng vững:**  
> Core Action được chọn không phải là *"mở app"* hay *"hỏi AI"* (đó chỉ là thao tác giao diện hoặc input đầu vào thụ động). Core action ở đây đòi hỏi nỗ lực nhận thức (cognitive effort) của học viên qua câu micro-quiz và khép lại bằng hành động xác nhận đã thông suốt để học tiếp.

---

## 02 — Action Nature Card + Kết luận Cadence (Phase 2)

### 1. Action Nature Card

| Thành phần | Câu trả lời phân tích thực tế |
| :--- | :--- |
| **Actor** | Individual Learner (Tài khoản học viên cá nhân). |
| **Intent** | Giải tỏa ngay sự bối rối khi không hiểu một công thức/khái niệm để tiếp tục mạch học. |
| **Trigger** | Học viên chủ động kích hoạt khi nhận thấy mình bị nghẽn nhận thức trên slide. |
| **Effort** | Trung bình: Dừng video 45–60 giây, đọc câu hỏi và suy nghĩ chọn 1 đáp án trắc nghiệm. |
| **Value timing** | Giá trị xuất hiện tức thì (Immediate value) ngay sau khi đọc lời giải thích 2 dòng của AI. |
| **State** | Lỗ hổng kiến thức đã chẩn đoán được lưu vào "Sổ điểm nghẽn cá nhân" để phục vụ ôn tập. |
| **Dependency** | Phụ thuộc vào nội dung bài giảng hiện tại (phải có khái niệm kỹ thuật gây tắc nghẽn). |
| **Repeat condition** | Xuất hiện lại khi gặp slide phức tạp tiếp theo hoặc ở bài giảng tuần kế tiếp. |

### 2. Kết luận Cadence

- **Dạng hành vi đã chọn:** **Tiến trình tích lũy & Phản ứng theo sự kiện trong buổi học** (*Session-based Event-Response & Cumulative Progress*).
- **Kết luận theo template chuẩn:**
  > *"Đối với **học viên tự học công nghệ trực tuyến (Minh Thảo)**, core action **Resolved Diagnostic Interaction** thường xuất hiện **2–4 lần mỗi tuần (trung bình 1–2 lần mỗi buổi học)** vì **người học chỉ học bài giảng chuyên sâu vào 2–3 buổi tối/cuối tuần theo tiến độ khóa học**. Do đó, nhịp đo phù hợp là **Weekly Cadence (Chu kỳ tuần)** ở cấp **Learner Cohort**."*

- **Cân nhắc chiều sâu (Quality vs. Frequency):**  
  Với sản phẩm AI Tutor, frequency cao hơn không đồng nghĩa với value cao hơn. Nếu học viên phải gọi chẩn đoán 15 lần trong 1 video 30 phút, đó là dấu hiệu bài giảng quá tệ hoặc AI giải thích không rõ. Value cao nhất là: **Xong việc gỡ tắc nhanh nhất ($\le 60$s) để học viên quay lại trạng thái tập trung cao độ (Flow state).**

> **GATE 2 — Cadence từ Nature:** Nhịp Weekly khớp chuẩn xác với nhịp sinh hoạt học tập tự nhiên; không ép Daily máy móc theo thói quen của các dashboard mạng xã hội.

---

## 03 — Metric System (Activation / Engagement / NSM / Leading / Counter) (Phase 3)

### 1. Activation Metric
- **Start event:** `lecture_started` (Học viên bắt đầu bài giảng đầu tiên trong khóa học).
- **Activation event:** `diagnostic_session_resolved` (Lần đầu tiên hoàn thành gỡ tắc thành công và tiếp tục xem video $\ge 5$ phút).
- **Time window:** Trong vòng **7 ngày** kể từ start event (Tuần học đầu tiên).
- *Tên metric:* **First Breakthrough Rate** = $\frac{\text{Số học viên đạt Activation event}}{\text{Số học viên có Start event}} \times 100\%$ (Mục tiêu: $\ge 45\%$).

### 2. Engagement Metric (Chọn 2 góc đo: Frequency & Depth)
- **Frequency:** Số phiên gỡ tắc thành công trung bình trên mỗi Active Learner mỗi tuần (*Weekly Resolved Actions / WAU*). Benchmark: 2–4 lần/tuần.
- **Depth:** Tỷ lệ học viên tiếp tục xem hết bài giảng sau khi gỡ tắc (*Post-Resolution Lecture Completion Rate*). Benchmark: $\ge 70\%$.

### 3. North Star Metric (NSM)
* **Tên chỉ số:** **Weekly Resolved Learning Hours (WRLH)**
* **Công thức chuẩn 3 thành phần:**
  $$\text{NSM} = [\text{Video Learning Hours completed}] \times [\text{Diagnostic Resolution Success Rate}] \times [\text{Weekly Frequency}]$$
  - *Unit of value:* Số giờ học tập hiệu quả hoàn thành.
  - *Quality threshold:* Các phiên học có tỷ lệ gỡ tắc thành công đạt $\ge 80\%$.
  - *Frequency:* Nhịp tuần (Weekly).

### 4. Leading Indicators (Tối đa 3 chỉ số)
1. **In-Lecture Diagnostic Acceptance Rate:** Tỷ lệ học viên bấm chấp nhận làm micro-quiz khi dừng video tại slide khó $\ge 30$s.  
   *Vì sao tin nó dự báo core action lặp lại:* Phản ánh mức độ tin tưởng ban đầu của học viên vào khả năng giải quyết vấn đề của AI Tutor.
2. **First-Try Quiz Accuracy:** Tỷ lệ học viên trả lời đúng câu hỏi chẩn đoán ngay lần đầu.  
   *Vì sao tin nó dự báo core action lặp lại:* Chứng minh AI bắt trúng điểm hổng nền tảng; giải quyết đúng bệnh thì học viên sẽ tiếp tục dùng lại khi gặp khó khăn sau này.
3. **Weekly Practice Warm-up Completion Rate:** Tỷ lệ hoàn thành bài warm-up ôn lại điểm nghẽn trước buổi học mới.  
   *Vì sao tin nó dự báo core action lặp lại:* Tạo đà tâm lý thoải mái và củng cố thói quen học tập có chủ đích.

### 5. Counter-Metric (Kiểm soát rủi ro)
* **Tên chỉ số:** **Flow Disruption Drop-off Rate** (Tỷ lệ bỏ học do đứt gãy luồng học).
* **Định nghĩa:** Tỷ lệ học viên thoát khỏi bài học ngay trong lúc tương tác với AI hoặc trong vòng 60 giây sau khi mở popup chẩn đoán.
* **Ngưỡng kiểm soát:** Bắt buộc **$\le 8\%$** (Nếu vượt quá $15\%$, báo động đỏ: AI đang làm phiền hoặc làm gián đoạn trải nghiệm học tập của học viên).

---

## 04 — Retention Definition (6 Thành phần) (Phase 3)

| Thành phần | Câu trả lời chuẩn xác cho VLearn AI Tutor |
| :--- | :--- |
| **Unit** | **Individual Learner ID** (Tài khoản học viên duy nhất). |
| **Cohort entry** | Học viên đạt mốc Activation (`diagnostic_session_resolved` lần đầu) trong tuần quan sát. |
| **Return event** | Thực hiện ít nhất 1 lần Core Action (`diagnostic_session_resolved`) trong tuần đánh giá. |
| **Window** | **Weekly Window** (Tuần W1, W2, W3, ..., W8) khớp chuẩn với chu kỳ tự nhiên của khóa học. |
| **Threshold** | $\ge 1$ lần hoàn thành Core Action VÀ tích lũy $\ge 30$ phút học tập trong tuần. |
| **Segment** | Học viên theo học các môn kỹ thuật có độ khó cao (Toán ứng dụng, Lập trình, AI/Data). |

> **Retention Target Curve:** Đường cong duy trì phẳng dần (Flattening curve) từ Tuần 4 ở mức **$\ge 30\%$** đối với khóa học kỹ thuật.  
> **So sánh 3 mốc (S34):** Khớp nhịp tự nhiên (Natural Cycle = 7 ngày); Cohort đúng phân khúc (Technical Enrolled Learners); Đạt chuẩn Benchmark ngành EdTech chuyên sâu ($25-35\%$).

> **GATE 3 — Metric tính được, Retention đủ nghĩa:** Activation có đủ 3 yếu tố; Retention đủ 6 thành phần khớp Weekly Cadence; NSM chuẩn công thức 3 thành phần và có counter-metric bảo vệ UX.

---

## 05 — Product Loop (2 Chu kỳ + Metric Hypothesis) (Phase 4)

- **Loại loop chính:** **Progress Loop kết hợp Habit Loop** (*Tiến trình hoàn thành môn học & Củng cố ngắt quãng*).

### Vẽ nhanh Loop tối thiểu hai chu kỳ:

```
[Natural Trigger 1: Gặp slide khó / nghẽn hiểu bài]
           │
           ▼
[Core Action 1: Làm micro-quiz chẩn đoán 1 câu của AI]
           │
           ▼
[Immediate Value: Ngộ ra căn nguyên (Aha!) & tự tin xem tiếp video]
           │
           ▼
[Saved State / Investment: Lỗ hổng được tự động lưu vào Sổ điểm nghẽn cá nhân]
           │
           ▼
[Next Natural Trigger: Nhu cầu tự thân chuẩn bị kiến thức cho bài mới & bài tập tuần]
           │
           ▼
[Core Action tiếp theo: Làm 3 phút Warm-up Quiz giải quyết dứt điểm điểm nghẽn cũ]
           │
           ▼
[Repeat Value: Tiếp thu trọn vẹn bài mới ──> Tạo đà tiến độ học tập tuần tiếp theo]
```

- **Phân tích Reason to return ngoài Notification:**  
  Nếu gỡ bỏ hoàn toàn notification, học viên vẫn quay lại vì **áp lực hạn nộp bài tập tuần (Weekly Assignment Milestone)** và **nhu cầu tự thân muốn hiểu trọn vẹn kiến thức trước khi bước vào kỳ thi/bài kiểm tra**. Notification chỉ là Nurture đóng vai trò nhắc giờ trước 15 phút, không phải lý do quay lại.
- **Metric Hypothesis (Chuẩn template đề bài):**
  > *"Nếu loop này hoạt động, metric **Weekly Assignment Submission Rate** sẽ thay đổi theo hướng **tăng từ 35% lên 58%** trong **4 tuần đầu của khóa học**, vì **học viên không còn bị hổng kiến thức nền tảng tích lũy, giúp họ tự tin làm bài tập tuần thay vì bỏ dở**."*

---

## 06 — Tracking Nhanh (4–8 Events + 2 Acceptance Criteria) (Phase 4)

### 1. Bảng Core Events (4 trường chuẩn hóa)

| Tên event (`object_action`) | Ý nghĩa (Điều đã xảy ra) | Thời điểm ghi nhận chính xác | Metric sử dụng ở Phase 3 |
| :--- | :--- | :--- | :--- |
| `lecture_started` | Học viên bắt đầu bấm xem bài giảng video | Khi video phát được 5 giây đầu tiên | Start event (Activation Metric) |
| `diagnostic_prompt_accepted` | Học viên chấp nhận làm micro-quiz chẩn đoán | Khi học viên click nút "Bắt đầu chẩn đoán" | Leading Indicator 1 (Acceptance Rate) |
| `diagnostic_quiz_submitted` | Học viên nộp câu trả lời cho câu hỏi chẩn đoán | Khi học viên click chọn đáp án trên modal | Leading Indicator 2 (Quiz Accuracy) |
| `diagnostic_session_resolved` | Học viên hoàn tất phiên chẩn đoán thành công | Khi học viên bấm nút "Đã hiểu, tiếp tục bài học" | **Core Action, NSM, Activation, Return Event** |
| `flow_disrupted_exit` | Học viên thoát bài học trong khi đang mở chẩn đoán | Khi đóng tab/bấm back trong modal hoặc $\le 60$s sau đó | **Counter-Metric (Flow Disruption Rate)** |
| `warmup_quiz_completed` | Học viên hoàn thành bài ôn tập điểm nghẽn đầu buổi | Khi nộp bài kiểm tra warm-up 3 phút | Leading Indicator 3 & Loop Hypothesis |

### 2. Hai Tiêu chí Nghiệm thu Kỹ thuật (Acceptance Criteria)

- **AC 1 (Hành vi hoàn tất thật sự & Debounce chống trùng lặp):**  
  *Với mỗi cặp `user_id` và `session_id`, event `diagnostic_session_resolved` CHỈ ĐƯỢC GHI NHẬN DUY NHẤT 1 LẦN khi học viên bấm nút "Đã hiểu, tiếp tục bài học" và thời lượng tương tác thực tế $\ge 5$ giây. Bấm nhiều lần liên tiếp (spam click) hoặc reload trang không được tạo thêm event mới.*

- **AC 2 (Toàn vẹn luồng dữ liệu & Session Stitching):**  
  *Mọi event `diagnostic_quiz_submitted` và `diagnostic_session_resolved` đều phải mang thuộc tính `session_id` khớp với `session_id` được sinh ra từ lúc mở modal chẩn đoán. Tỷ lệ event mồ côi (orphaned events) không gắn được vào phiên chẩn đoán ban đầu phải đạt mức $< 0.5\%$ trên toàn hệ thống.*

> **GATE 4 — Loop nối metric, Event nối loop:** Loop 2 chu kỳ có metric hypothesis trỏ thẳng vào metric Phase 3; toàn bộ 6 event đều map trực tiếp vào công thức tính các chỉ số.

---

## 07 — Tự Soi Lỗi & Revision Log (Phase 5)

### 1. Bảng Tự Kiểm 7 Câu Hỏi Sống Còn (Gate 5 Check)

| STT | Câu hỏi tự soi lỗi | Trạng thái | Giải trình minh chứng trong bài |
| :---: | :--- | :---: | :--- |
| **1** | Core action không phải thao tác giao diện hay output hệ thống? | **ĐẠT** | Chọn `Resolved Diagnostic Interaction` (hành động người học trả lời quiz và giải tỏa nhận thức), không chọn "mở modal" hay "AI trả lời". |
| **2** | Activation không phải "xem hết hướng dẫn" hay "đăng nhập"? | **ĐẠT** | Định nghĩa là `First Breakthrough Rate` (lần đầu tự mình gỡ tắc thành công và học tiếp $\ge 5$ phút). |
| **3** | Frequency không cao hơn nhu cầu thật? | **ĐẠT** | Chọn **Weekly Cadence** dựa trên lịch học thực tế 2–3 buổi/tuần, kiên quyết từ chối ép DAU. |
| **4** | Loop có reason to return ngoài notification? | **ĐẠT** | Reason to return xuất phát từ nhu cầu tự thân: chuẩn bị kiến thức cho bài mới và hạn nộp bài tập tuần. |
| **5** | Retention không dùng chung một window cho mọi cadence? | **ĐẠT** | Sử dụng **Weekly Bracket Window (W1 $\rightarrow$ W8)** khớp 100% với nhịp học tự nhiên. |
| **6** | Mọi event đều map về một metric? | **ĐẠT** | Toàn bộ 6/6 events đều ánh xạ trực tiếp về Activation, NSM, Leading, Counter-metric hoặc Loop hypothesis. |
| **7** | Metric nào cũng có event để tính nó? | **ĐẠT** | Đầy đủ event, trigger moment, thuộc tính định danh để tính toán từng chỉ số trong hệ thống. |

### 2. Revision Log (Ghi nhận điều chỉnh tư duy)
- **Điều chỉnh 1:** Ban đầu AI gợi ý Core Action là *"Hỏi AI Tutor"*. Tôi đã bác bỏ vì đây chỉ là input giao diện, không đảm bảo user nhận được value. Quyết định đổi thành *"Resolved Diagnostic Interaction"* (kèm completion rule xác nhận đã hiểu).
- **Điều chỉnh 2:** Ban đầu định dùng Daily Active Learner (DAL) theo thói quen app thông thường. Sau khi soi chiếu bản chất học tập kỹ thuật theo phiên, tôi đã chuyển toàn bộ hệ thống sang **Weekly Cadence** để không bóp méo hành vi người dùng thật.

> **GATE 5 — Bài sạch lỗi kinh điển:** Đã đối chiếu hoàn tất 7 câu hỏi, bài làm không mắc bất kỳ lỗi tư duy nào theo cảnh báo của giảng viên.
