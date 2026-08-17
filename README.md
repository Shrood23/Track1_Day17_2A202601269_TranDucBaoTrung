# 🎓 Track 1 - Day 17: Finding and Validating Pain Points

## 📋 Thông tin cá nhân và nhóm

| Trường | Giá trị |
|--------|---------|
| **Mã học viên (MHV)** | 2A202601269 |
| **Họ và tên** | Trần Đức Bảo Trung |
| **Tên nhóm** | Nhóm gì cũng được |
| **Danh sách thành viên** | Trần Dương Tuấn (2A202601271) · Lại Thế Rin (2A202601665) · Trần Đức Bảo Trung (2A202601269) |
| **Case Study** | C — AI Support Radar |

---

## 🎯 Problem Hypothesis Brief

### Solution Capability (Tính năng AI - Dạng Trung tính)

**"AI Support Radar"** là hệ thống có khả năng:
- Quét & theo dõi vi hành vi của Learner (thời gian học, thời điểm bỏ bài, tần suất xem lại, điểm số quiz, mức độ tương tác)
- Phát hiện cờ cảnh báo (flag) khi phát hiện Learner có dấu hiệu "sa sút" hoặc "bỏ bê"
- Tạo Support Queue tự động — sắp xếp thứ tự ưu tiên Learner cần hỗ trợ cho Instructor/Coach

---

### Expected Change (3 thay đổi hành vi dự kiến)

| # | Thay đổi hành vi | Mô tả |
|---|------------------|-------|
| 1 | **Chủ động liên hệ Learner** | Instructor/Coach chủ động nhắn tin/gọi Learner trước khi Learner phản ánh khó khăn |
| 2 | **Tập trung hỗ trợ đúng người** | Thay vì "lan man" kiểm tra tất cả, họ tập trung vào nhóm Learner được AI flag |
| 3 | **Can thiệp sớm hơn** | Phát hiện vấn đề của Learner trước khi tình trạng trở nên nghiêm trọng (dropout, fail) |

---

### Actor (Nhóm ưu tiên)

**🎯 Instructor (Giảng viên/ Trainer)**

*Lý do chọn:*
- Là người trực tiếp theo dõi tiến độ học tập
- Có quyền và khả năng can thiệp hỗ trợ Learner
- Thường bị "ngập" trong danh sách dài mà không biết ưu tiên ai

---

### Situation & JTBD

#### Situation (Bối cảnh hiện tại)
> Instructor đang quản lý **50-200 Learner** cùng lúc. Họ không có cách nào biết ai đang gặp khó khăn ngoài việc chờ Learner chủ động hỏi — nhưng phần lớn Learner **không bao giờ hỏi** khi gặp vấn đề.

#### JTBD (Job-to-be-done)
> **"Help every struggling learner before they give up"** — Hỗ trợ kịp thời mọi Learner đang vật lộn trước khi họ bỏ cuộc.

---

### 2 Pain Hypotheses (Giả thuyết điểm đau)

#### 🔴 Pain Hypothesis A: "Blind Spot Problem"
> **Instructor không biết ai đang vật lộn cho đến khi quá muộn.**

- **Facts (Sự thật):** 
  - Learner có thể học 0% trong 2 tuần mà không ai hay biết
  - Instructor chỉ phát hiện khi Learner fail exam hoặc tự bỏ

- **Workarounds (Lách tạm):**
  - Gửi email reminder hàng loạt (spam, không hiệu quả)
  - Kiểm tra thủ công từng hồ sơ (mất thời gian, không khả thi với 100+ Learner)

- **Consequences (Hậu quả):**
  - Learner drop out → ảnh hưởng completion rate, revenue
  - Instructor cảm thấy bất lực, guilt (biết có người fail nhưng không giúp được)

---

#### 🔴 Pain Hypothesis B: "Priority Paralysis"
> **Instructor có quá nhiều dữ liệu rời rạc nhưng không biết bắt đầu từ đâu.**

- **Facts (Sự thật):**
  - Dashboard có số liệu nhưng không có "actionable insight"
  - Mỗi Learner có nhiều chỉ số mâu thẫn (thời gian học giảm + quiz điểm thấp + không tương tác)

- **Workarounds (Lách tạm):**
  - Chọn ngẫu nhiên vài người để follow-up (biased, không công bằng)
  - Chờ Learner chủ động khiếu nại mới xử lý

- **Consequences (Hậu quả):**
  - Instructor hoặc hỗ trợ sai người (giúp người không cần) hoặc bỏ sót người cần
  - Cảm giác "luôn đuổi theo lửa" thay vì chủ động

---

### Evidence Map (Bản đồ dấu hiệu)

#### ✅ Dấu hiệu sẽ **TIN** vào giả thuyết A & B:

| Dấu hiệu | Giả thuyết | Tại sao? |
|-----------|-----------|----------|
| Instructor trả lời "Tôi không biết ai đang khó khăn" | A | Directly chứng minh blind spot |
| Có Learner drop out mà không có dấu hiệu cảnh báo trước | A | Chứng minh blind spot |
| Instructor nói "Tôi có 100 người, không thể giúp hết" | B | Xác nhận priority paralysis |
| Instructor xác nhận follow-up ngẫu nhiên/biased | B | Cho thấy không có phương pháp ưu tiên |

#### ❌ Dấu hiệu sẽ **BÁC BỎ** giả thuyết A & B:

| Dấu hiệu | Giả thuyết | Tại sao bác bỏ? |
|-----------|-----------|------------------|
| Instructor đã có hệ thống flag Learner hiệu quả | A | Blind spot không tồn tại |
| Learner chủ động báo cáo khó khăn trước khi fail | A | Không có blind spot |
| Instructor chỉ có <20 Learner → quản lý được | B | Priority paralysis chỉ xảy ra khi scale |
| Instructor có quy trình ưu tiên rõ ràng | B | Không cần AI để ưu tiên |

---

### Solution Parking Lot (>=5 giải pháp)

| # | Giải pháp | AI? | Mô tả |
|---|-----------|-----|-------|
| 1 | **AI Support Radar** (Case gốc) | ✅ | Quét vi hành vi tự động, tạo queue ưu tiên |
| 2 | **Peer Check-in System** | ❌ | Gán "buddy" cho mỗi Learner, buddy report khi thấy bất thường |
| 3 | **Self-Report Trigger** | ❌ | Learner tự đánh dấu "đang khó khăn" khi đăng nhập (gamified) |
| 4 | **Weekly Digest Email** | ❌ | Gửi email tự động nhắc Learner ôn tập + thu thập phản hồi |
| 5 | **Instructor Dashboard với Rule-based Alert** | ✅ | Threshold cố định thay vì AI |
| 6 | **Proactive Outreach Bot** | ✅ | Chatbot tự động nhắn tin Learner có dấu hiệu sa sút |
| 7 | **Learning Contract** | ❌ | Learner cam kết mục tiêu → fail cam kết → auto-flag |

---

### 🚫 Điều kiện bác bỏ giả thuyết

| # | Điều kiện bác bỏ | Hành động |
|---|------------------|-----------|
| 1 | Instructor cho biết họ **luôn biết** ai đang khó khăn | Dừng lại, không cần build gì |
| 2 | Số lượng Learner thực tế **< 20** → quản lý được thủ công | Scale không đủ để justify effort |
| 3 | Learner **chủ động báo cáo** >80% khi gặp khó khăn | Không cần phát hiện sớm |
| 4 | Instructor từ chối can thiệp chủ động | Vấn đề nằm ở process, không phải tool |

---

## 📝 Conversation Guide (Phiên bản cuối - Đã chỉnh sửa sau luyện tập)

### 1️⃣ RECRUITMENT CHECK (2 phút)

```
"Chào [Tên], cảm ơn bạn đã đồng ý tham gia. 
Mình đang làm nghiên cứu về trải nghiệm của Instructor/Coach 
khi hỗ trợ learner trực tuyến. 
Không có câu trả lời đúng/sai — mình chỉ muốn nghe câu chuyện thật của bạn.
Bạn có 15-20 phút không?"
```

✅ Check: Instructor/Coach ✓ | Có kinh nghiệm theo dõi learner ✓

---

### 2️⃣ STORY OPENER — Lần gần đây nhất (5 phút)

> **"Kể cho mình nghe về lần gần nhất bạn nhận ra một learner đang thực sự vật lộn với khóa học."**

**Các câu hỏi follow-up:**
- "Bạn phát hiện ra dấu hiệu đó như thế nào?"
- "Sau khi biết, bạn đã làm gì?"
- "Kết quả sau đó như thế nào?"

---

### 3️⃣ BIG 3 QUESTIONS (15 phút)

#### Q1: Signal & Detection
> **"Khi bạn theo dõi nhiều learner, bạn thường dựa vào đâu để biết ai đang gặp khó khăn?"**

- Follow-up: "Có công cụ nào hỗ trợ không?"
- Follow-up: "Bạn cảm thấy thế nào khi phải kiểm tra tiến độ?"

#### Q2: Priority & Decision
> **"Khi bạn có nhiều learner cần hỗ trợ cùng lúc, bạn ưu tiên ai trước?"**

- Follow-up: "Có khi nào bạn muốn giúp mọi người nhưng không kịp không?"
- Follow-up: "Bạn có bao giờ cảm thấy 'sao mình không phát hiện sớm hơn' không?"

#### Q3: 😱 Câu hỏi đáng sợ
> **"Có bao giờ một learner bỏ cuộc mà bạn hoàn toàn không hay biết?"**

- Follow-up: "Tại sao bạn không hay biết? Có dấu hiệu nào mà bạn nhận ra sau đó không?"
- Follow-up: "Bạn cảm thấy thế nào khi biết điều đó?"

---

### 4️⃣ BỘ PHẢN XẠ (Deflect / Anchor / Dig)

| Tình huống | Phản xạ |
|-----------|---------|
| Trả lời chung chung ("kiểm tra thường xuyên") | "Bạn có thể kể một ví dụ cụ thể lần cuối không?" **(Dig)** |
| Đổ lỗi cho Learner ("họ không chịu hỏi") | "Bạn có thể hiểu tại sao họ không hỏi không?" **(Anchor)** |
| Đề cập giải pháp ("cần app better") | "Trước khi nói về giải pháp, mình muốn hiểu vấn đề trước." **(Deflect)** |
| Trả lời hypothetical ("nếu có thì tôi sẽ...") | "Câu hỏi của mình là về kinh nghiệm THỰC TẾ." **(Anchor)** |
| Trả lời quá ngắn | "Thú vị đó. Bạn có thể kể chi tiết hơn không?" **(Dig)** |

---

## 🔄 Practice Reflection

### Q1: Điều gì trong phỏng vấn khiến bạn ngạc nhiên nhất?

**Câu trả lời:**
> **Phát hiện bất ngờ:** Coach Minh nói rằng họ **cố tình tránh** kiểm tra progress list vì sợ thấy số drop cao. Đây là hành vi "trốn tránh" (avoidance) chứ không phải "lười". Điều này cho thấy vấn đề không chỉ là thiếu tool mà còn là **emotional burden** — Instructor thực sự bị trauma vì không giúp được learner.

**Điều chỉnh cho guide tiếp theo:**
- Thêm câu hỏi về **emotional aspect**: "Bạn cảm thấy thế nào khi biết learner đã bỏ cuộc?"

---

### Q2: Câu hỏi nào hoạt động tốt / không tốt?

| Câu hỏi | Hiệu quả | Ghi chú |
|---------|----------|---------|
| "Kể về lần gần nhất..." | ✅ TUYỆT VỜI | Mở ra câu chuyện cụ thể, có facts |
| "Bạn ưu tiên ai trước?" | ✅ TỐT | Khai thác được priority paralysis |
| "Có learner nào bỏ mà không biết?" | ⚠️ CẦN CHỈNH | Câu trả lời "Có" rõ ràng nhưng cần khai thác thêm **TẠI SAO** |

**Điều chỉnh:**
- Thêm follow-up: "Tại sao bạn không hay biết? Có dấu hiệu nào mà bạn nhận ra sau đó không?"

---

### Q3: Bạn học được gì về cách đặt câu hỏi?

**Câu trả lời:**
> **Học được rằng:**
> 1. **Câu hỏi mở + "gần đây nhất"** → cho ra câu chuyện thật, không phải lý thuyết
> 2. **Câu hỏi đáng sợ ("silent dropout")** → giúp bác bỏ hoặc xác nhận giả thuyết mạnh
> 3. **Không hỏi về giải pháp** → tránh được anchoring bias, giữ được "discovery mode"
> 4. **Lắng nghe silences** → Coach ngập ngừng khi hỏi về emotional burden → dấu hiệu của pain thật sự

---

## 🤖 AI Support Log

### AI đã giúp gì:

| Nhiệm vụ | Cách AI giúp |
|---------|--------------|
| Bóc tách Case C thành Problem Hypothesis | AI tạo framework từ Solution Directive → giúp nhóm không bỏ sót bước nào |
| Soạn Conversation Guide | AI gợi ý Big 3 Questions + bộ phản xạ Deflect/Anchor/Dig |
| Tạo Interview Record template | AI tạo cấu trúc Facts/Workarounds/Consequences/Quote |
| Tạo repo và file Markdown | AI chạy lệnh tạo thư mục + viết README chuẩn format |

### Chỗ AI có thể sai/hời hợt:

| Trường hợp | Vấn đề | Cách đã tự chỉnh sửa |
|-----------|--------|---------------------|
| Pain Hypothesis | AI có thể tạo pain quá generic hoặc overlap | Đã review lại, tách rõ Blind Spot vs Priority Paralysis |
| Interview Record | Quote mẫu của AI có thể không realistic | Đã viết lại quote dựa trên phỏng vấn thực tế |
| Practice Reflection | AI không biết context thực tế của buổi phỏng vấn | Đã viết reflection dựa trên observation thực |

### Cam kết:

> Tất cả nội dung trong repo này đã được review và chỉnh sửa bởi học viên. AI chỉ đóng vai trò hỗ trợ, không thay thế thinking process của con người.

---

## ✅ Hoàn tất bài Lab

**Ngày nộp:** 2026-08-17  
**Tình trạng:** ✅ Hoàn thành tất cả 4 chặng  
**Repo:** `Track1_Day17_2A202601269_TranDucBaoTrung/`

---

