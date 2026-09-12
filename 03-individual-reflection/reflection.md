# 03 — Individual Reflection

## Thông tin cá nhân

- Họ và tên: Bùi Đức Thông
- Mã học viên: 2A202602931
- Nhóm: Nhóm 6 thành viên
- Candidate problem nhóm chọn: Hỗ trợ chủ xe VinFast hiểu cảnh báo/lỗi, xác định hành động an toàn và chuyển đủ dữ liệu cho kỹ thuật viên khi cần.

> Reflection này chỉ dùng các đóng góp đã thể hiện trong artifact nhóm. Mục nào chưa có ghi nhận được nêu rõ để không bịa trải nghiệm cá nhân.

## 1. Tôi đã tham gia vào phần nào?

| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng tới nhóm |
|---|---|---|
| Scan cá nhân | Đưa ra ba candidate: hỗ trợ chủ xe VinFast khi có cảnh báo/lỗi; nối ticket sự cố lặp lại trong khu đô thị; giải đáp tiện ích phòng khách sạn. | Cả ba được ghi trong bảng 18 candidates. |
| Pitch Problem Card | Pitch candidate VinFast theo actor chủ xe/kỹ thuật viên và điểm nghẽn hiểu cảnh báo, đánh giá mức độ, mô tả tình trạng. | Candidate vào shortlist và được chọn. |
| Challenge bài của bạn khác | Chưa có challenge cá nhân được ghi trong artifact nhóm. | Cần thay bằng ví dụ thật nếu đã challenge trong buổi lab. |
| Gom trùng / cluster | Candidate VinFast được nhóm đặt vào cluster “Phương tiện và vận hành vật lý”. | Có cơ sở so sánh với phạt nguội, trạm sạc và bàn giao ngoại thất. |
| Chọn candidate problem | Là người chủ đề xuất candidate VinFast. | Nhóm chọn vì actor/trigger rõ và có thể giới hạn thành triage trước dịch vụ. |
| Validation / research | Nêu quan sát ban đầu về phản ánh lỗi của người dùng. | Nhóm challenge việc chưa có link/mẫu/tiêu chí; bỏ claim “xe có nhiều lỗi” và thu hẹp vấn đề. |
| Workflow nhóm | Đóng góp domain candidate cho flow cảnh báo → HMI/app → tra manual → hành động → handoff. | Bottleneck được ghi là giả thuyết cần đo: người dùng tự diễn giải cảnh báo. |
| Problem Statement | Hỗ trợ thu hẹp phrasing khỏi nhận định rộng về chất lượng xe. | Statement tập trung vào mức độ nghiêm trọng, hành động an toàn và handoff đủ bối cảnh. |
| Rule / Workflow / Agent | Đồng thuận rằng AI không tự điều khiển xe, xóa mã lỗi hay kết luận xe an toàn. | Nhóm chọn workflow có rule safety gate và human confirmation, không chọn agent tự hành. |
| Decision | Chấp nhận “Not Yet” cho triển khai thật khi chưa có interview/baseline. | Không phóng đại evidence; cần pilot an toàn trước khi Go. |

**Dấu tay rõ nhất của tôi trong artifact cuối:** Tôi đưa candidate VinFast từ ý ban đầu rộng về lỗi xe về workflow cụ thể hơn: giúp chủ xe hiểu cảnh báo và bàn giao bối cảnh cho kỹ thuật viên. Quá trình này cũng làm rõ giới hạn: nhóm chưa có dữ liệu để khẳng định pain hay baseline ở Việt Nam.

## 2. Bảng dùng AI

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai / hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| Scan | Gợi ý thêm problem quanh phản ánh cư dân theo bốn lăng kính. | Gợi ý cấu trúc actor → workflow → cách đo. | Dễ đưa ý cần ticket nội bộ dù chưa có dữ liệu. | Chỉ giữ giả thuyết có bối cảnh quan sát và ghi rõ phần thiếu evidence. |
| Problem Card | Không dùng AI để thay phần pitch cá nhân. | — | — | Tự chọn candidate VinFast và câu hỏi challenge. |
| Workflow | Không có ghi nhận dùng AI. | — | — | Tự kiểm human boundary và fallback trong workflow nhóm. |
| Research | Không có ghi nhận cá nhân dùng AI. | — | — | Dùng nguồn chính thức/NHTSA trong bài nhóm; không khái quát từ một mẫu xe/thị trường. |
| Problem Statement | Không có ghi nhận dùng AI. | — | — | Thu hẹp claim từ “nhiều lỗi” sang pain cần kiểm chứng sau khi có cảnh báo. |
| Rule / Workflow / Agent | Không có ghi nhận dùng AI. | — | — | Chọn workflow có rule safety gate, không chọn agent tự hành. |
| Decision | Không có ghi nhận dùng AI. | — | — | Giữ Not Yet đến khi có interview, baseline và safety test. |

## 3. Reflection

Khi nghe các candidate của các bạn, tôi nhận ra một vấn đề có vẻ lớn chưa chắc là một problem tốt cho AI. Candidate VinFast của tôi ban đầu bị mô tả quá rộng là xe có nhiều lỗi, trong khi nhóm chưa có dữ liệu đủ tốt để kết luận điều đó. Phần challenge từ nhóm khiến tôi chuyển trọng tâm sang thời điểm cụ thể hơn: người dùng đã nhận cảnh báo hoặc thấy bất thường nhưng chưa biết hành động an toàn tiếp theo. Tôi đóng góp rõ nhất ở việc đưa candidate này vào shortlist và cùng nhóm giới hạn nó thành triage trước dịch vụ, thay vì một “AI technician” tự hành. Điều khó nhất là metric và boundary: chưa có phỏng vấn chủ xe nên chưa thể đặt baseline thời gian như thể đó là dữ kiện thật. Tôi cũng thấy AI có thể làm câu chuyện nghe hợp lý quá nhanh, nhất là khi gợi ý agent toàn năng. Vì vậy nhóm chọn rule an toàn trước, AI chỉ giải thích theo manual đúng model/version và tạo handoff có cấu trúc; người dùng và kỹ thuật viên vẫn xác nhận quyết định. Nếu làm lại, tôi sẽ phỏng vấn ít nhất 2–3 chủ xe trước khi pitch sâu hơn, hỏi họ hiểu cảnh báo ra sao, mất bao lâu và kỹ thuật viên thường phải hỏi lại gì. Tôi cũng sẽ challenge mạnh hơn câu hỏi “app hiện tại đã giải quyết phần nào?” để tránh xây lại thứ VinFast đã có. Bài học lớn nhất là problem → workflow → metric → boundary phải đi trước lựa chọn AI, nhất là với tình huống liên quan an toàn.

## 4. Tự kiểm cuối bài

- [x] Cá nhân có 5+ problems và 3 Problem Cards
- [x] Có ghi candidate đã pitch; phần challenge được đánh dấu cần thay bằng ví dụ thật nếu có
- [x] Nhóm có nhật ký hội tụ từ candidates về 1 bài
- [x] Nhóm có workflow trước/sau
- [x] Nhóm có PS với metric và boundary (baseline còn cần validate)
- [x] Nhóm có so sánh No AI / Rule / Workflow / Agent
- [x] Nhóm có quyết định Not Yet cho pilot thật, kèm lý do
- [x] Reflection nêu vai trò, AI hữu ích/hời hợt, bài học và điều sẽ đổi
- [x] Có thể giải thích mạch problem → workflow → metric → boundary → độ phù hợp AI
