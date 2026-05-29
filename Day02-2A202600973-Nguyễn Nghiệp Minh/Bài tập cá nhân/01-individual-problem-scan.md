# 01 — Individual Problem Scan

## Scan rộng

Nhóm gồm 5 học viên chuyển đến chỗ ở mới gần VinUni. Mỗi ngày nhóm phải quyết định bữa trưa và bữa tối: ăn món gì, ăn ngoài hay tự nấu, mức giá phù hợp và chọn quán nào.

| # | Lăng kính | Problem quan sát được | Ai đang đau? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Lặp lại | Trước mỗi bữa trưa/tối, một người phải hỏi lại cả nhóm: ăn gì, ăn ngoài hay tự nấu, ngân sách bao nhiêu, quán nào phù hợp | Người đứng ra chốt món; cả nhóm | Có thể lặp lại 2 lần/ngày; nhiều tin nhắn trước khi chốt |
| 2 | Tốn thời gian | Khi nhóm chọn ăn ngoài, người chốt phải tự tìm và so sánh nhiều quán quanh VinUni theo món, giá, khoảng cách, đánh giá và giờ mở cửa | Người tìm quán; các thành viên đang chờ ăn | Ước lượng mất 15–25 phút/bữa ăn ngoài; cần đo lại trong 5–7 ngày |
| 3 | Lặp lại | Nhóm không nhớ rõ các món đã ăn gần đây, dẫn đến đề xuất trùng món rồi phải đổi lựa chọn | Cả nhóm; người đang đề xuất món | Xuất hiện tình huống “món này mới ăn rồi”; mất thêm thời gian tranh luận |
| 4 | AI có thể tốt hơn | Việc chọn món hiện dựa trên ý kiến rời rạc trong nhóm chat, chưa tổng hợp sở thích, ngân sách và lịch sử món ăn của từng người | Cả nhóm; thành viên thường xuyên phải nhượng bộ | Có người không thích phương án đã chốt hoặc ăn theo số đông |
| 5 | Pain từ người khác | Khi nhóm tự nấu, người phụ trách phải hỏi lại ai ăn và mua bao nhiêu; nếu có người đổi ý muộn thì dễ mua dư hoặc thiếu nguyên liệu | Người đi chợ/người nấu; người góp tiền | Chờ xác nhận trước khi mua; có nguy cơ thừa/thiếu phần ăn |
| 6 | Pain từ người khác | Sau bữa ăn, người trả trước phải tự chia tiền và nhắc những người chưa chuyển khoản, đặc biệt khi từng người gọi món khác nhau | Người ứng tiền; thành viên bị nhắc trả | Phải tính lại hoặc nhắc chuyển khoản sau bữa ăn |

Vì sao phần scan này phù hợp:

- Có actor cụ thể: nhóm 5 học viên sống gần VinUni.
- Có workflow xảy ra trong đời sống hằng ngày, tối đa 2 lần/ngày.
- Các problem không bắt đầu bằng ý tưởng “làm chatbot” hay “xây trợ lý toàn năng”.
- Mỗi problem đều có dấu hiệu có thể quan sát và đo lại trong thời gian ngắn.

## Top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Tìm và so sánh quán ăn khi nhóm chọn ăn ngoài | Actor rõ, workflow dễ vẽ, bottleneck nằm ở bước tìm/lọc/so sánh quán; đo được bằng thời gian chốt quán, số quán bị loại và mức hài lòng; so sánh Rule / Workflow / Agent rõ | Chưa đo chính xác số phút mất cho mỗi lần tìm; thông tin giá và giờ mở cửa của quán có thể không cập nhật |
| 2 | Đề xuất trùng món vì không nhớ lịch sử ăn gần đây | Scope nhỏ, dễ thử trong một buổi lab; bottleneck cụ thể là thiếu lịch sử món; có thể kiểm chứng bằng rule đơn giản trước khi dùng AI | Chưa biết nhóm có thực sự khó chịu với việc ăn lặp món hay vấn đề chỉ xảy ra thỉnh thoảng |
| 3 | Khó xác nhận số người ăn khi nhóm tự nấu | Actor và workflow rõ; impact có thể đo bằng thời gian chờ, đồ mua dư/thiếu và số lần đổi ý muộn; thể hiện tốt hướng Workflow | Chưa chắc nhóm tự nấu đủ thường xuyên để problem có impact lớn |

## Problem Card #1 — Tìm và so sánh quán ăn khi nhóm chọn ăn ngoài

**Problem 1 câu:**  
Khi nhóm 5 người quyết định ăn ngoài, người chốt phải tự tìm và so sánh nhiều quán quanh VinUni theo món muốn ăn, giá tiền, khoảng cách, đánh giá và giờ mở cửa, khiến việc chốt quán mất thời gian và thường phải làm lại khi một thành viên không đồng ý.

**Actor:**  
Người đứng ra hỏi ý kiến và chốt quán cho nhóm; 4 thành viên còn lại đang chờ quyết định để đi ăn hoặc đặt đồ.

**Thời điểm / bối cảnh:**  
Trước bữa trưa hoặc bữa tối, sau khi nhóm đã quyết định ăn ngoài nhưng chưa biết chọn quán nào.

**Current workflow:**

```text
1. Người chốt hỏi nhóm muốn ăn món gì và ngân sách khoảng bao nhiêu
2. Các thành viên phản hồi rời rạc trong nhóm chat
3. Người chốt mở Google Maps hoặc ứng dụng giao đồ ăn để tìm quán
4. Người chốt xem từng quán: món, giá, khoảng cách, đánh giá, giờ mở cửa
5. Người chốt gửi 1–3 lựa chọn vào nhóm
6. Thành viên phản hồi: xa, đắt, không thích hoặc quán không phù hợp
7. Người chốt tìm lại hoặc nhóm thống nhất quán cuối cùng
```

**Bottleneck:**  
Bước 3–6 — tìm, lọc, so sánh và đề xuất lại quán phù hợp với nhiều yêu cầu của nhóm. Ước lượng ban đầu mất khoảng 10–15 phút/lần ăn ngoài, chưa tính thời gian chờ phản hồi.

**Impact:**  
Nếu nhóm ăn ngoài khoảng 8 bữa/tuần và mỗi lần việc tìm/chốt quán mất trung bình 15 phút, người chốt có thể mất khoảng 120 phút/tuần cho thao tác lặp lại này. Việc chốt muộn còn có thể ảnh hưởng thời gian nghỉ trưa hoặc lịch học.

**Success metric:**  
Giảm thời gian từ lúc nhóm thống nhất ăn ngoài đến lúc chốt quán từ mức cần đo ban đầu xuống dưới 8 phút/bữa; giảm ít nhất 50% số lần phải tìm lại quán sau khi gửi đề xuất; mức hài lòng sau bữa đạt trung bình từ 4/5 trở lên.

**Non-AI alternative:**  
Tạo Google Sheet/Notion lưu danh sách quán quen quanh trường gồm món, mức giá, khoảng cách, giờ mở cửa và đánh giá của nhóm; người chốt lọc thủ công thay vì tìm lại từ đầu.

**AI hypothesis:**  
AI hỗ trợ workflow lọc và tóm tắt shortlist quán từ các ràng buộc như món muốn ăn, ngân sách và khoảng cách. Người chốt vẫn kiểm tra thông tin quan trọng và gửi lựa chọn để nhóm quyết định cuối.

**Quick gut:**  
Workflow.

### Draft current workflow

```text
CURRENT STATE — ƯỚC LƯỢNG 15–25 PHÚT/BỮA ĂN NGOÀI

[1 Hỏi món + ngân sách: 3']
→ [2 Chờ phản hồi nhóm: 4']
→ [3 Tìm quán trên Maps/app: 6']
→ [4 So sánh giá/khoảng cách/review: 5']  <-- bottleneck
→ [5 Gửi lựa chọn: 1']
→ [6 Nhận phản đối + tìm lại: 3–6']
→ [7 Chốt quán: 1']
```

### Draft future workflow

```text
FUTURE STATE — MỤC TIÊU DƯỚI 8 PHÚT/BỮA

[1 Nhóm nhập món + ngân sách + khoảng cách: 2']
→ [2 Workflow lọc danh sách quán phù hợp: <1']
→ [3 AI tóm tắt top 3 lựa chọn và lý do: <1']
→ [4 Người chốt kiểm tra + gửi nhóm: 2']  <-- human boundary
→ [5 Nhóm vote/chốt quán: 2']

Fallback: Dữ liệu quán thiếu, sai giá hoặc quán đóng cửa
→ người chốt kiểm tra lại trên Maps/app trước khi đi.
```

## Problem Card #2 — Đề xuất trùng món vì không nhớ lịch sử ăn gần đây

**Problem 1 câu:**  
Nhóm không có cách xem nhanh những món đã ăn gần đây, nên trước mỗi bữa có thể đề xuất lại món vừa ăn, khiến cả nhóm phải loại món, tranh luận và nghĩ phương án mới.

**Actor:**  
Cả 5 thành viên tham gia chọn món; người đề xuất món và người không muốn ăn lặp lại chịu pain trực tiếp nhất.

**Thời điểm / bối cảnh:**  
Trước bữa trưa hoặc bữa tối, khi nhóm đang nghĩ món ăn nhưng chưa chốt lựa chọn.

**Current workflow:**

```text
1. Một thành viên đề xuất một món
2. Thành viên khác phản hồi rằng món đó vừa ăn hôm qua hoặc vài ngày trước
3. Cả nhóm cố nhớ lại hoặc kéo tin nhắn cũ để kiểm tra
4. Món vừa đề xuất bị loại
5. Một hoặc nhiều thành viên đề xuất món khác
6. Nhóm tiếp tục trao đổi cho đến khi chọn được món
```

**Bottleneck:**  
Bước 2–5 — nhóm chỉ phát hiện món trùng sau khi đã đề xuất và bắt đầu tranh luận, vì không có lịch sử món ăn dễ xem. Ước lượng ban đầu mất thêm khoảng 5–10 phút/lần có trùng món.

**Impact:**  
Nếu tình huống này xảy ra 5 lần/tuần và mỗi lần làm mất thêm khoảng 7 phút, cả nhóm mất khoảng 35 phút/tuần chỉ để loại các món vừa ăn gần đây. Việc ăn lặp món cũng có thể làm giảm mức hài lòng của thành viên.

**Success metric:**  
Giảm ít nhất 70% số lần món bị phản đối vì “mới ăn rồi”; giảm thời gian tranh luận do trùng món xuống dưới 3 phút/lần; tỷ lệ lặp cùng món trong vòng 3 ngày dưới 10%.

**Non-AI alternative:**  
Lưu lịch sử bữa ăn trong một bảng đơn giản gồm ngày, bữa trưa/tối, món và quán; áp dụng rule không đề xuất lại món đã ăn trong 3 ngày gần nhất.

**AI hypothesis:**  
AI có thể đọc lịch sử món ăn và gợi ý danh sách món chưa ăn gần đây. Tuy nhiên, nếu pain chính chỉ là tránh lặp món thì rule đơn giản có thể đã đủ hiệu quả và nên được thử trước.

**Quick gut:**  
Rule.

### Draft current workflow

```text
CURRENT STATE — ƯỚC LƯỢNG 8–15 PHÚT KHI XẢY RA TRÙNG MÓN

[1 Một người đề xuất món: 1']
→ [2 Thành viên phản hồi "mới ăn rồi": 2']
→ [3 Cả nhóm nhớ lại / kéo tin nhắn cũ: 3']  <-- bottleneck
→ [4 Loại món cũ: 1']
→ [5 Đề xuất món mới: 3']
→ [6 Chốt món: 2–5']
```

### Draft future workflow

```text
FUTURE STATE — MỤC TIÊU DƯỚI 3 PHÚT CHO VIỆC TRÁNH TRÙNG MÓN

[1 Mở lịch sử 3 ngày gần nhất: <1']
→ [2 Rule tự loại món vừa ăn: <1']
→ [3 Hiển thị danh sách món còn hợp lệ: <1']
→ [4 Nhóm chọn món: 1–2']  <-- human boundary

Fallback: Nếu cả nhóm vẫn muốn ăn lại món vừa ăn
→ cho phép override rule và ghi nhận lựa chọn.
```

## Problem Card #3 — Khó xác nhận số người ăn khi nhóm tự nấu

**Problem 1 câu:**  
Khi nhóm quyết định tự nấu, người phụ trách phải chờ từng thành viên xác nhận có ăn hay không trước khi mua nguyên liệu; nếu một người trả lời muộn hoặc đổi ý sau khi mua đồ, nhóm dễ bị dư hoặc thiếu thức ăn và khó chia chi phí.

**Actor:**  
Người đi chợ hoặc người trực tiếp nấu; các thành viên xác nhận ăn và góp tiền nguyên liệu.

**Thời điểm / bối cảnh:**  
Vào các bữa nhóm cân nhắc tự nấu tại chỗ ở mới, trước khi một người đi mua nguyên liệu hoặc bắt đầu chuẩn bị đồ ăn.

**Current workflow:**

```text
1. Một thành viên đề xuất tự nấu một món cho bữa trưa hoặc bữa tối
2. Người phụ trách hỏi trong nhóm chat ai sẽ ăn
3. Các thành viên trả lời không cùng lúc; có người chưa xác nhận
4. Người phụ trách ước lượng số phần ăn và số tiền cần góp
5. Người phụ trách đi mua nguyên liệu
6. Có thành viên đổi ý, báo không ăn hoặc muốn ăn thêm sau khi đã mua đồ
7. Người nấu phải điều chỉnh lượng thức ăn hoặc nhóm xử lý phần tiền/nguyên liệu dư thiếu
```

**Bottleneck:**  
Bước 2–4 — chờ đủ xác nhận số người ăn trước khi quyết định lượng nguyên liệu và đi mua đồ. Ước lượng ban đầu mất khoảng 10–20 phút/bữa tự nấu.

**Impact:**  
Người đi chợ/người nấu mất thời gian nhắc từng người xác nhận. Nếu mua dư, nhóm tốn tiền hoặc phải xử lý đồ thừa; nếu mua thiếu, người nấu phải chia lại khẩu phần hoặc mua bổ sung. Pain chỉ đủ lớn nếu nhóm tự nấu tương đối thường xuyên.

**Success metric:**  
Giảm thời gian từ lúc đề xuất nấu đến khi đủ xác nhận xuống dưới 5 phút; giảm ít nhất 50% số bữa có người đổi ý sau khi đã chốt; giảm ít nhất 50% giá trị nguyên liệu dư hoặc đồ phải mua bổ sung.

**Non-AI alternative:**  
Dùng poll trong nhóm chat kèm deadline rõ ràng, ví dụ: “Ai ăn tối nay xác nhận trước 17:30; sau thời điểm này mặc định không tính phần”, kết hợp bảng định lượng nguyên liệu theo số người.

**AI hypothesis:**  
Một workflow có AI hỗ trợ có thể tổng hợp xác nhận, đếm số phần, áp dụng định lượng đã định sẵn và tạo danh sách mua đồ. Người phụ trách vẫn kiểm tra và quyết định mua cuối cùng.

**Quick gut:**  
Workflow.

### Draft current workflow

```text
CURRENT STATE — ƯỚC LƯỢNG 20–35 PHÚT TRƯỚC KHI BẮT ĐẦU ĐI CHỢ

[1 Đề xuất món tự nấu: 2']
→ [2 Hỏi ai ăn: 1']
→ [3 Chờ từng người xác nhận: 10–20']  <-- bottleneck
→ [4 Ước lượng nguyên liệu + chi phí: 5']
→ [5 Đi mua đồ]
→ [6 Có người đổi ý sau khi mua]
→ [7 Điều chỉnh phần ăn / chia lại tiền]
```

### Draft future workflow

```text
FUTURE STATE — MỤC TIÊU DƯỚI 8 PHÚT TRƯỚC KHI ĐI CHỢ

[1 Gửi poll món + deadline xác nhận: 1']
→ [2 Thành viên chọn có ăn/không ăn: 3–5']
→ [3 Workflow chốt số phần khi hết deadline: <1']
→ [4 AI hoặc bảng định lượng tạo danh sách mua đồ: <1']
→ [5 Người đi chợ kiểm tra và mua: 1']  <-- human boundary

Fallback: Nếu có người đổi ý sau deadline
→ người phụ trách quyết định có bổ sung phần ăn hay không.
```

## Quyết định cá nhân

Chọn làm sâu hơn: **Problem Card #1 — Tìm và so sánh quán ăn khi nhóm chọn ăn ngoài.**

Vì sao chọn:

- Xảy ra trực tiếp trong bữa trưa và bữa tối, không phụ thuộc vào việc nhóm có thường xuyên tự nấu hay không.
- Actor rõ: người chốt quán và các thành viên đang chờ ăn.
- Workflow hiện tại dễ quan sát và vẽ được.
- Bottleneck cụ thể: tìm, lọc, so sánh và đề xuất lại quán.
- Có thể đo bằng thời gian chốt quán, số phương án bị loại và mức hài lòng sau bữa.
- Có thể so sánh rõ No AI / Rule / Workflow / Agent mà không mở rộng thành hệ thống quá lớn.

Phạm vi giữ lại cho bài lab:

```text
Chỉ giải quyết bước tìm, lọc và đề xuất shortlist quán ăn phù hợp
cho nhóm khi đã quyết định ăn ngoài.

Không mở rộng sang:
- Tự đặt món
- Tự thanh toán hoặc chia tiền
- Tự ra quyết định thay cả nhóm
- Quản lý toàn bộ bữa ăn hằng ngày
```

Dữ liệu cần thu thập để kiểm chứng trong 5–7 ngày:

| Dữ liệu cần ghi | Mục đích |
|---|---|
| Thời gian bắt đầu hỏi và thời gian chốt quán | Đo baseline thời gian |
| Số quán đã đề xuất trước khi chốt | Đo effort tìm kiếm |
| Lý do quán bị loại: xa, đắt, không thích, đóng cửa, khác | Xác định rule lọc quan trọng |
| Mức hài lòng sau bữa ăn của từng người từ 1–5 | Kiểm tra việc chốt nhanh có làm giảm chất lượng lựa chọn không |
