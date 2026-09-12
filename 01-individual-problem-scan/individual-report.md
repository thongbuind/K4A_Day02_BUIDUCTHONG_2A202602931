# 01 — Individual Problem Scan

## Thông tin cá nhân

- Họ và tên: Bùi Đức Thông
- Mã học viên: 2A202602931
- Bối cảnh: Sinh viên năm 4; tham gia lab AI và làm project LLM cá nhân.

> Thời lượng là ước lượng cá nhân để ưu tiên khảo sát, không phải số liệu đại diện cho toàn bộ người dùng.

## Phase 1 — Scan problems

| # | Lăng kính | Problem quan sát được | Ai chịu ảnh hưởng? | Dấu hiệu thật |
|---:|---|---|---|---|
| 1 | Tốn thời gian / AI có thể tốt hơn | Khi xe có cảnh báo hoặc vận hành bất thường, chủ xe phải tự tra mã lỗi, manual và mạng trước khi chọn hành động an toàn. | Chủ xe VinFast, CSKH, kỹ thuật viên | Candidate nhóm đã chọn; chưa có baseline người dùng Việt Nam. |
| 2 | Lặp lại / Pain từ người khác | Nhiều cư dân phản ánh cùng một sự cố bằng các ticket riêng lẻ, làm ban quản lý khó thấy lịch sử vấn đề. | Cư dân, ban quản lý | Quan sát trong bối cảnh cư dân; chưa có ticket mẫu hay số lượng để xác nhận. |
| 3 | Pain từ người khác | Khách không rõ tiện ích nào tính phí hoặc cách dùng thiết bị trong phòng. | Khách lưu trú, lễ tân | Trải nghiệm cá nhân: từng không rõ cà phê/mì có tính phí và cách dùng vòi nước. |
| 4 | Tốn thời gian | Bắt đầu thử nghiệm LLM phải đọc README, paper và issue để xác định đúng dữ liệu, model, metric. | Sinh viên làm project LLM | Ước lượng 45–60 phút/lần, 1–2 lần/tuần ở giai đoạn thử nghiệm. |
| 5 | Lặp lại | Dữ liệu từ nhiều nguồn có schema, encoding và nhãn khác nhau; kiểm tra/làm sạch lặp lại trước khi train. | Người làm project LLM | Ước lượng 30–45 phút/bộ dữ liệu. |
| 6 | Tốn thời gian | Kết quả model nằm ở notebook, terminal và log rời rạc, khó biết run tốt nhất. | Nhóm lab | Ước lượng 15–20 phút/lần đối chiếu. |
| 7 | AI có thể tốt hơn | Tài liệu kỹ thuật dài khiến tìm đúng điều kiện áp dụng và cách tái lập phương pháp chậm. | Sinh viên nghiên cứu AI | Ước lượng 30–60 phút/tài liệu dài. |
| 8 | Lặp lại | Quyết định kỹ thuật nằm ở nhiều tin nhắn/tài liệu, nên phải tìm lại context trước khi tiếp tục task. | Thành viên nhóm lab | Ước lượng 10–15 phút/lần, thường khi handoff. |

**AI đã dùng ở Phase 1**

- Prompt: hỏi AI gợi ý problem từ phản ánh cư dân Vinhomes theo bốn lăng kính.
- Ý dùng được: workflow tiếp nhận → chuẩn hóa → nối sự cố tương tự → tổng hợp cho ban quản lý.
- Ý bỏ: gợi ý cần ticket/dữ liệu nội bộ mà chưa có quyền truy cập hoặc evidence.

## Phase 2 — Top 3 Problem Cards

| Rank | Problem | Vì sao chọn | Điều chưa chắc |
|---:|---|---|---|
| 1 | Hỗ trợ chủ xe VinFast khi có cảnh báo/lỗi | Actor và trigger rõ; có thể so sánh Rule/Workflow/Agent. | Pain, baseline và khoảng trống so với app hiện tại cần phỏng vấn 2–3 chủ xe. |
| 2 | Nối ticket sự cố lặp lại trong khu đô thị | Có thể đo triage và thấy pattern thay vì xử lý từng ticket. | Chưa có ticket mẫu hay baseline. |
| 3 | Giải đáp tiện ích trong phòng khách sạn | Bối cảnh và thời điểm cần thông tin cụ thể; dễ pilot. | FAQ/nhãn rõ có thể đã đủ, chưa cần AI. |

### Problem Card #1 — Hỗ trợ chủ xe VinFast khi có cảnh báo/lỗi

**Problem 1 câu:** Khi xe xuất hiện cảnh báo hoặc vận hành bất thường, chủ xe VinFast khó hiểu mức độ nghiêm trọng, thu thập đủ thông tin và chọn hành động an toàn mà không phải tự tra nhiều nguồn hoặc mô tả lại cho kỹ thuật viên.

- **Actor:** Chủ xe; CSKH/kỹ thuật viên nhận handoff.
- **Bối cảnh:** Ngay khi HMI/app hiện cảnh báo hoặc xe có biểu hiện bất thường.
- **Current workflow:** (1) Nhận cảnh báo/bất thường → (2) xem HMI/app → (3) tra mã lỗi, manual, web → (4) chọn tự xử lý/đặt dịch vụ/cứu hộ → (5) mô tả lại → (6) kỹ thuật viên hỏi thêm và chẩn đoán.
- **Bottleneck:** Bước 3 — người dùng phải nối mã lỗi, triệu chứng, manual và dịch vụ thành hành động an toàn.
- **Impact:** Người dùng lo lắng, mô tả thiếu bối cảnh và kỹ thuật viên phải hỏi lại.
- **Success metric:** Sau khi có baseline pilot, giảm ≥50% thời gian từ cảnh báo đến hành động phù hợp và ≥50% lượt hỏi bổ sung; phân luồng ≥95%, không hạ mức bất kỳ case safety-critical nào.
- **Non-AI alternative:** Cải thiện nội dung cảnh báo, decision tree cố định theo mã lỗi và FAQ/manual theo model.
- **AI hypothesis:** Sau rule an toàn, AI chỉ truy xuất manual đúng model/version, giải thích, hỏi dữ kiện không nguy hiểm và tạo handoff có cấu trúc.
- **Quick gut:** Workflow.

```text
CURRENT — chưa có time-log
[Cảnh báo] → [Xem HMI/app] → [Tra manual/web] ← bottleneck
→ [Chọn hành động] → [Mô tả lại] → [Kỹ thuật viên chẩn đoán]

FUTURE — mục tiêu giảm ≥50% sau pilot
[Đọc mã lỗi, read-only] → [Rule an toàn] → [Truy xuất manual đúng phiên bản]
→ [AI giải thích + hỏi thêm] → [Chủ xe xác nhận] ← human boundary → [Handoff có cấu trúc]

Fallback: thiếu dữ liệu, confidence thấp, nguồn mâu thuẫn hoặc cảnh báo an toàn
→ chuyển CSKH/kỹ thuật viên/cứu hộ ngay; không hướng dẫn tự xử lý.
```

### Problem Card #2 — Nối ticket sự cố lặp lại trong khu đô thị

**Problem 1 câu:** Khi nhiều cư dân phản ánh cùng một sự cố bằng cách diễn đạt khác nhau, ban quản lý khó nhận ra pattern và ưu tiên xử lý đúng mức.

- **Actor:** Cư dân; nhân viên ban quản lý triage và điều phối.
- **Bối cảnh:** Tiếp nhận ticket mới qua app, hotline hoặc chat.
- **Current workflow:** (1) Cư dân gửi mô tả tự do → (2) nhân viên đọc → (3) tạo/phân loại ticket → (4) điều phối riêng lẻ → (5) quản lý xem báo cáo thủ công.
- **Bottleneck:** Ticket mới không được nối với lịch sử cùng vị trí/chủ đề.
- **Impact:** Sự cố lặp lại có thể bị ưu tiên thấp; cư dân phải phản ánh lại.
- **Success metric:** Pilot ticket ẩn danh: ≥90% gắn đúng nhóm sự cố, giảm 30% thời gian triage; 100% gộp ticket do nhân viên duyệt.
- **Non-AI alternative:** Form bắt buộc vị trí/loại sự cố, taxonomy và dashboard theo khu vực.
- **AI hypothesis:** Chuẩn hóa mô tả tự do, đề xuất ticket tương tự và tóm tắt lịch sử để nhân viên duyệt.
- **Quick gut:** Workflow.

```text
CURRENT: [Cư dân gửi tự do] → [Đọc] → [Tạo ticket mới] → [Điều phối riêng] → [Báo cáo thủ công] ← bottleneck
FUTURE: [Form có field] → [Rule kiểm tra] → [AI đề xuất tương tự] → [Nhân viên duyệt/gộp] ← human boundary → [Dashboard]
Fallback: không đủ tin cậy → tạo ticket mới; không tự gộp hoặc đóng ticket.
```

### Problem Card #3 — Giải đáp tiện ích trong phòng khách sạn

**Problem 1 câu:** Khách không biết vật dụng nào tính phí hoặc cách dùng thiết bị trong phòng đúng lúc cần, nên phải tự đoán, tìm thông tin hoặc gọi lễ tân.

- **Actor:** Khách lưu trú và lễ tân.
- **Bối cảnh:** Lần đầu vào phòng hoặc khi dùng minibar, phòng tắm, điều khiển thiết bị.
- **Current workflow:** (1) Khách có câu hỏi → (2) tìm bảng giá/booklet/QR → (3) tự đoán hoặc gọi lễ tân → (4) lễ tân tra và trả lời.
- **Bottleneck:** Thông tin không nổi bật theo ngữ cảnh và khác nhau theo phòng/thiết bị.
- **Impact:** Trải nghiệm khách bị gián đoạn; câu hỏi FAQ lặp lại cho lễ tân.
- **Success metric:** 10 câu hỏi phổ biến được trả lời đúng trong dưới 1 phút; nếu có log, giảm ≥30% cuộc gọi FAQ.
- **Non-AI alternative:** QR đúng vị trí, nhãn/bảng giá song ngữ và FAQ tìm kiếm.
- **AI hypothesis:** Chỉ cân nhắc hỏi đáp đa ngôn ngữ trên knowledge base đã duyệt sau khi thử nhãn/FAQ.
- **Quick gut:** No AI / Rule.

```text
CURRENT: [Khách có câu hỏi] → [Tìm booklet/nhãn] ← bottleneck → [Gọi lễ tân] → [Trả lời]
FUTURE: [Nhãn/QR đúng vị trí] → [FAQ theo phòng/thiết bị] → [Lễ tân xử lý ngoại lệ] ← human boundary
Fallback: thông tin phí/hướng dẫn không chắc → lễ tân xác nhận, không trả lời đoán.
```

### Card muốn pitch nhất

**Card:** Hỗ trợ chủ xe VinFast khi có cảnh báo/lỗi.

**Pitch:** Chủ xe không cần “AI technician” tự quyết. Điều cần kiểm chứng là họ có mất thời gian hiểu cảnh báo, chọn hành động an toàn và mô tả lại sự cố không. Nếu có khoảng trống, giải pháp phù hợp là workflow: rule an toàn phân nhánh trước; AI chỉ giải thích/truy xuất tài liệu đúng phiên bản và tạo handoff; kỹ thuật viên vẫn quyết định.

**Câu hỏi challenge:** App VinFast hiện đã có cảnh báo và đặt dịch vụ. Bằng chứng nào cho thấy lớp giải thích/handoff còn giảm được thời gian hoặc lượt hỏi lại? Nếu không đạt safety gate và baseline, có nên dừng ở rule/UX thay vì dùng AI?

### Self-check

- [x] Có 5+ problems và 3 Cards đủ field
- [x] Mỗi Card có workflow trước/sau, bottleneck, metric, fallback
- [x] Có card pitch và câu hỏi challenge
