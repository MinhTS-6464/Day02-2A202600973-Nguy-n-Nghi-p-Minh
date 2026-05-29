# Day 02 Lab — Problem Discovery, Workflow Design & AI Reflection

## 1. Thông tin học viên

| Thông tin | Nội dung |
|---|---|
| **Họ và tên** | Nguyễn Nghiệp Minh |
| **Mã học viên** | 2A202600973 |
| **Lớp** | E402 |
| **Chương trình** | Chương trình đào tạo AI — VinUni |
| **Buổi học** | Lab 02 — Problem Discovery, Workflow Design & Reflection |

---

## 2. Nội dung thực hiện trong buổi Lab 02

Trong buổi lab hôm nay, tôi được thực hành quy trình xác định và đánh giá một bài toán phù hợp để ứng dụng AI, bắt đầu từ **pain thực tế** thay vì bắt đầu bằng ý tưởng xây dựng một chatbot hay một sản phẩm AI quá rộng.

Các hoạt động chính tôi đã thực hiện gồm:

- Quan sát và liệt kê các vấn đề thực tế theo bốn lăng kính: **lặp lại**, **tốn thời gian**, **AI có thể làm tốt hơn** và **pain từ người khác**.
- Chọn ra các problem cá nhân có actor rõ, workflow có thể vẽ được, bottleneck cụ thể và impact có thể đo lường.
- Viết **Problem Cards** và mô tả quy trình **Current State / Future State** cho các bài toán ưu tiên.
- Tham gia thảo luận nhóm, phản biện lỗ hổng của đề tài chung và hỗ trợ chuẩn bị trình bày trước hội đồng phản biện.
- So sánh các mức giải pháp **No AI / Rule / Workflow / Agent** để lựa chọn cách tiếp cận vừa đủ, an toàn và phù hợp với phạm vi một buổi lab.
- Viết reflection cá nhân về việc sử dụng AI, vai trò của bản thân trong nhóm và các bài học sau quá trình thực hành.

### Ý tưởng cá nhân: AI hỗ trợ nhóm lựa chọn đồ ăn hằng ngày

Problem cá nhân tôi phát triển xuất phát từ trải nghiệm thực tế sau khi chuyển đến nơi ở mới gần trường: nhóm gồm 5 người phải quyết định món ăn cho cả bữa trưa và bữa tối mỗi ngày. Trước mỗi bữa, một người thường phải hỏi lại cả nhóm muốn ăn gì, ăn ngoài hay tự nấu, mức ngân sách bao nhiêu và nếu ăn ngoài thì quán nào vừa gần vừa phù hợp.

Trong các pain đã scan, tôi ưu tiên bài toán:

> **Khi nhóm chọn ăn ngoài, người chốt phải tự tìm và so sánh nhiều quán quanh VinUni theo món muốn ăn, giá tiền, khoảng cách, đánh giá và giờ mở cửa, khiến việc chốt quán mất thời gian và thường phải làm lại khi một thành viên không đồng ý.**

Hướng giải pháp phù hợp được xác định là **Workflow**, trong đó AI có thể hỗ trợ lọc và tóm tắt shortlist quán ăn dựa trên các ràng buộc của nhóm như món muốn ăn, ngân sách và khoảng cách. Tuy nhiên, người dùng vẫn là người kiểm tra thông tin và đưa ra quyết định cuối cùng.

Phạm vi của ý tưởng được giữ nhỏ và thực tế:

- Không để AI tự đặt món.
- Không để AI tự thanh toán hoặc chia tiền.
- Không để AI tự quyết định thay toàn bộ nhóm.
- Chỉ tập trung vào bước **tìm, lọc và đề xuất các quán phù hợp**.

### Đề tài nhóm: AI Inbox Operator cho Social Commerce

Sau quá trình thảo luận, nhóm không chọn problem cá nhân của tôi mà lựa chọn đề tài **AI Inbox Operator — tối ưu phễu chốt đơn Social Commerce tại Việt Nam**.

Đề tài tập trung vào nhân viên trực chat tại các shop Social Commerce quy mô SMB, nơi lượng tin nhắn lớn khiến việc tra cứu giá, tồn kho và soạn phản hồi chốt đơn trở nên chậm và dễ sai sót. Nhóm lựa chọn mức giải pháp **Workflow**: AI hỗ trợ tra cứu và soạn bản nháp phản hồi, còn nhân viên là người kiểm duyệt và bấm gửi cuối cùng.

Trong phần làm việc nhóm, tôi đóng góp ở vai trò:

- Tìm các câu hỏi phản biện và lỗ hổng của sản phẩm.
- Đặt vấn đề về cách đánh giá đâu là khách hàng thực sự có nhu cầu mua hàng hoặc là khách hàng tiềm năng để AI ưu tiên đúng hội thoại.
- Tham gia trình bày và bảo vệ đề tài trước hội đồng phản biện.

---

## 3. Cấu trúc các file nộp bài

Tất cả nội dung phân tích chi tiết được tổ chức dưới dạng các file Markdown đồng cấp để thuận tiện cho việc theo dõi, review và chấm bài:

### `01-individual-problem-scan.md`

Bản phân tích problem cá nhân về bài toán **AI hỗ trợ nhóm học viên lựa chọn món ăn/quán ăn hằng ngày**. File bao gồm:

- Scan rộng các pain thực tế phát sinh khi nhóm 5 người quyết định bữa trưa và bữa tối.
- Top 3 problem ưu tiên.
- Ba Problem Cards chi tiết.
- Workflow trước/sau cho từng problem.
- Quyết định cá nhân chọn làm sâu bài toán tìm và so sánh quán ăn khi nhóm quyết định ăn ngoài.

### `02-group-problem-statement.md`

Báo cáo kết quả làm việc nhóm đối với đề tài **AI Inbox Operator — tối ưu phễu chốt đơn Social Commerce tại Việt Nam**. File trình bày:

- Quá trình hội tụ và lựa chọn đề tài nhóm.
- Shortlist, scoring và lý do chọn AI Inbox Operator.
- Quick validation và research các hướng giải pháp liên quan.
- Workflow trước/sau khi áp dụng giải pháp.
- Problem Statement phiên bản hoàn thiện.
- So sánh Rule / Workflow / Agent và quyết định lựa chọn **Workflow** có human-in-the-loop.

### `03-individual-reflection.md`

Bài phản tư học tập cá nhân sau Lab 02. File trình bày:

- Vai trò và đóng góp của tôi trong quá trình làm việc nhóm.
- Việc problem cá nhân không được chọn và cách tôi chuyển sang đóng góp ở vai trò phản biện.
- Cách tôi sử dụng AI trong từng giai đoạn: scan problem, chọn top 3, viết workflow, phản biện nhóm và hoàn thiện bài nộp.
- Những điểm AI hỗ trợ tốt và những điểm AI còn đưa ra gợi ý quá chung chung.
- Bài học về tư duy **problem-first**, lựa chọn mức giải pháp AI phù hợp và vai trò của human boundary.

---

## Bài học chính sau buổi lab

Sau Lab 02, tôi rút ra ba bài học quan trọng:

1. Một sản phẩm AI tốt phải bắt đầu từ **problem thật**, actor thật, workflow thật và bottleneck đo được; không nên bắt đầu bằng mong muốn xây một chatbot hoặc agent tổng quát.
2. Không phải bài toán nào cũng cần Agent. Cần cân nhắc chi phí, rủi ro và phạm vi để lựa chọn đúng giữa **Rule**, **Workflow** và **Agent**.
3. AI rất hữu ích trong việc mở rộng góc nhìn và cấu trúc hóa ý tưởng, nhưng con người vẫn phải kiểm chứng pain thực tế, thu hẹp scope và phản biện các rủi ro trước khi đưa ra quyết định.

---

## Danh sách file

```text
.
├── README.md
├── 01-individual-problem-scan.md
├── 02-group-problem-statement.md
└── 03-individual-reflection.md
```
