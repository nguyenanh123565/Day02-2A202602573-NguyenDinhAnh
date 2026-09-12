# 01 — Individual Problem Scan

> Điền theo Phase 1 + Phase 2 trong `01-worksheet.md`. Tự scan trước, dùng AI sau để phản biện. Không copy ví dụ Weekly Report.

## Thông tin cá nhân

- Họ và tên: Nguyễn Đình
- Mã học viên:  2A202602573
- Vai trò / bối cảnh (VD: sinh viên năm X, intern PM, ...): vừa tốt nghiệp
- Công việc hằng tuần (3-5 gạch đầu dòng để soi problem):
/ -Viết code và debug các lỗi phát sinh (3-5 lần/tuần)

-   Viết tài liệu báo cáo, giải trình thiết kế và tiến độ bài lab/dự án (2-3 lần/tuần)

-    Trả lời, hỗ trợ giải đáp thắc mắc chuyên môn hoặc phân công công việc trong nhóm (moi ngày)

- Review code, họp kiểm thử ranh giới an toàn và merge code lên GitHub (2-3 lần/tuần)


## Phase 1 — Scan 5+ problems (tối thiểu 5, khuyến khích 8-10)

**Cách điền:** mỗi dòng = việc gì + ai chịu + đo bằng gì. Cột `Dấu hiệu thật` bắt buộc có số: mất bao lâu (bấm giờ mấy lần), mấy lần/tuần, bao nhiêu người gặp, log/ticket/quote nào.

| # | Lăng kính (Lặp lại / Tốn thời gian / AI có thể tốt hơn / Pain từ người khác) | Problem quan sát được | Ai chịu ảnh hưởng? | Dấu hiệu thật (số + bằng chứng) |
|---|---|---|---|---|
| 1 | Tốn thời gian|Tự gõ test case thủ công bằng tay để kiểm tra ranh giới System Prompt cho AI Agent. | sinh vien lab chung nhom|mat gan 1 tieng 1/lan va thuc hien 3 lan/ tuan voi 5/5 nguoơ |
| 2 | lap lai|Phải khởi tạo môi trường ảo (.venv), cài requirements.txt và set GEMINI_API_KEY thủ công mỗi khi mở lại Terminal hoặc đổi máy.| Thanh vien trong nhom|maá 10phut cho moi lan va set api KEY |
| 3 |AI lam tot hon |AI hay bi bo lot nhan hoao xuat khong dung dang json| giang vien va | dap an bi sai 2/6 va 6 cau lenh lam AI tra loi sai quy tac|
| 4 | Pain tu nguoi khac|khog biet duoc cau treuc du lieu dau vao do do dat cau hoi sai |ai agents va nguoi su dung  |khien ai phai hoi lai nhieu lan va tieu ton nhieu luot chat  |
| 5 |pain tu nguoi khac |nhom bi xung dot code khi merge |ca ngom |khoang 3 lan /tuan va 1 tieng de fix |
| 6 | | | | |
| 7 | | | | |
| 8 | | | | |
| 9 | | | | |
| 10 | | | | |

> Gợi ý tự soi: tuần trước mất nhiều thời gian nhất vào việc gì? Việc gì hay trì hoãn? Người khác hay hỏi lại câu gì? Workflow nào ai cũng biết là chậm?

**AI đã dùng ở Phase 1 (nếu có):**
- Prompt đã hỏi:
- Ý dùng được:
- Ý bỏ vì không phải pain thật:

**Self-check Phase 1:**
- [ ] Đủ 5+ dòng, mỗi dòng có actor + số đo cụ thể
- [ ] Dùng ít nhất 3/4 lăng kính
- [ ] Không có dòng chung chung kiểu "mất nhiều thời gian"

---

## Phase 2 — Top 3 Problem Cards

### 2.1. Chọn top 3

Giữ bài nào: actor cụ thể, workflow vẽ được 3-7 bước, bottleneck ở 1 bước, impact đo được. Loại bài quá rộng.

| Rank | Problem (copy từ bảng scan) | Vì sao chọn (2-3 ý) | Điều còn chưa chắc |
|---|---|---|---|
 
| --- | --- | --- | --- |
| 1 | **AI Dispatcher bị lọt lưới khi gặp câu lệnh lách luật (Jailbreak) | Đánh đúng mục tiêu cốt lõi của bài Lab về an toàn vận hành; có metric tỷ lệ lỗi rõ ràng (2/5 test case). | Làm sao bao phủ hết các kịch bản tấn công mới do người dùng cố tình nghĩ ra. |
| 2 | Tự gõ test case thủ công để kiểm tra System Prompt | Tốn nhiều thời gian nhất (45-60 phút/lần); dễ giải quyết triệt để bằng viết script tự động hóa. | Khó đánh giá liệu độ bao phủ (coverage) của script tự động đã đủ 100% chưa. |
| 3 | Người dùng gửi câu hỏi thiếu thông tin (thiếu % pin, vị trí)| Trực tiếp ảnh hưởng đến trải nghiệm (chiếm 40% lượt chat); buộc AI phải xử lý dữ liệu mập mờ. | Thiết kế prompt thu thập thông tin (slot-filling) sao cho không làm cuộc trò chuyện bị dài dòng. |






### 2.2. Problem Cards chi tiết (lặp lại cho cả 3 cards)

---

#### Problem Card #1 — AI Dispatcher bị lọt lưới khi gặp câu lệnh lách luật (Jailbreak)

```text
Problem 1 câu:

Actor:

Thời điểm / bối cảnh:

Current workflow 3-7 bước:
1.
2.
3.
4.
5.

Bottleneck:

Impact:

Success metric:

Non-AI alternative:

AI hypothesis:

Quick gut:
[ ] No AI / process fix
[ ] Rule
[ ] Workflow
[ ] Agent
[ ] Chưa biết
```
Problem 1 câu:
AI Dispatcher bị lọt lưới (bỏ nhãn [DRAFT_ONLY] hoặc không xuất JSON cứu hộ khi pin < 5%) khi nhận các câu lệnh tấn công lách luật từ người dùng.

Actor:
Lập trình viên AI / Sinh viên phát triển Agent.

Thời điểm / bối cảnh:
Trong quá trình kiểm thử ranh giới an toàn (Guardrails & System Prompt) trước khi nộp bài hoặc đưa Agent vào vận hành.

Current workflow 3-7 bước:
1. Sửa đổi System Prompt trong code.
2. Chạy ứng dụng Agent trên Terminal.
3. Gõ thủ công câu lệnh tấn công lách luật (Jailbreak prompt).
4. Quan sát kết quả đầu ra của AI.
5. Đọc log và đánh giá xem AI có tuân thủ quy tắc an toàn không.

Bottleneck:
Bước 4 — AI không tuân thủ quy tắc an toàn (tỷ lệ lỗi 2/5 test case), mất nhiều thời gian tinh chỉnh Prompt mà vẫn bị lọt lưới.

Impact:
Tốn 60-90 phút/buổi tinh chỉnh Prompt; rủi ro cao bị trừ điểm bài Lab hoặc gây nguy hiểm vận hành thực tế nếu AI tự ý thực thi lệnh khẩn cấp sai định dạng.

Success metric:
Giảm tỷ lệ lọt lưới quy tắc từ 40% (2/5 case) xuống 0% trên tập test case tấn công tiêu chuẩn.

Non-AI alternative:
Viết code Python cứng (Hardcode If/Else) để kiểm tra và chặn chuỗi đầu ra (Output Validation).

AI hypothesis:
Sử dụng mô hình bảo vệ 3 lớp (Input Filter + Few-shot System Prompt + Output Guardrails Code) để ép AI tuân thủ ranh giới tuyệt đối.

Quick gut:
[ ] No AI / process fix
[ ] Rule
[x] Workflow
[ ] Agent
[ ] Chưa biết

**Draft workflow Card #1*(ASCII / Mermaid / ảnh đính kèm):

```text
CURRENT STATE — ___ phút

[1 ...: __'] → [2 ...: __'] → [3 ...: __'] → [4 ...: __']  <-- bottleneck

FUTURE STATE — ___ phút

[1 ...: __'] → [2 ...: __'] → [3 ... review: __']  <-- human boundary

Fallback: nếu AI sai thì ...
``

File đính kèm (nếu vẽ riêng): `01-individual-problem-scan-workflow-card-1.png`
CURRENT STATE — 45 phút
//
[1 Sửa Prompt: 5'] → [2 Chạy Agent: 2'] → [3 Gõ test case thủ công: 10'] → [4 AI lọt lưới/Đọc kết quả: 25'] <-- bottleneck → [5 Chỉnh lại Prompt: 3']

FUTURE STATE — 10 phút

[1 Nhập System Prompt: 2'] → [2 Chạy script kiểm thử tự động 3 lớp: 1'] → [3 Developer review log vi phạm: 5'] <-- human boundary → [4 Fix Prompt/Code: 2']

Fallback: nếu AI vẫn lọt lưới → Code Python chốt chặn (Output Validation) sẽ tự động ghi đè (override) chèn nhãn [DRAFT_ONLY] hoặc trả JSON chuẩn.


#### Problem Card #2 — Tự gõ test case thủ công để kiểm tra System Prompt

```text
Problem 1 câu:

Actor:

Thời điểm / bối cảnh:

Current workflow 3-7 bước:
1.
2.
3.
4.
5.

Bottleneck:

Impact:

Success metric:

Non-AI alternative:

AI hypothesis:

Quick gut:
[ ] No AI / process fix
[ ] Rule
[ ] Workflow
[ ] Agent
[ ] Chưa biết
```
//
Problem 1 câu:
Lập trình viên mất 45-60 phút mỗi lần thử nghiệm vì phải gõ tay từng kịch bản test để kiểm tra tính chặt chẽ của System Prompt.

Actor:
Lập trình viên AI / Thành viên nhóm phát triển bài Lab.

Thời điểm / bối cảnh:
Mỗi khi cập nhật logic System Prompt mới trong file prompt_prototype.py (3 lần/tuần).

Current workflow 3-7 bước:
1. Mở file prompt_prototype.py và chỉnh sửa System Prompt.
2. Chạy script python trong Terminal.
3. Nhập câu hỏi test 1 (kiểm tra nhãn [DRAFT_ONLY]).
4. Nhập câu hỏi test 2 (kiểm tra quy tắc Pin < 5%).
5. Nhập câu hỏi test 3 (kiểm tra kịch bản lách luật).
6. Tự đối chiếu kết quả trả về với yêu cầu đề bài.

Bottleneck:
Bước 3, 4, 5 — Nhập liệu và kiểm thử từng câu hỏi thủ công tốn thời gian, dễ bỏ sót case và thiếu tính nhất quán.

Impact:
Lãng phí 45-60 phút/lần x 3 lần/tuần = 135-180 phút/tuần cho mỗi lập trình viên; trễ tiến độ hoàn thiện bài lab.

Success metric:
Giảm tổng thời gian kiểm thử Prompt từ 45 phút xuống dưới 3 phút/lần chạy.

Non-AI alternative:
Tạo file script Python đọc danh sách câu hỏi từ file JSON/Text và tự động chạy vòng lặp kiểm tra.

AI hypothesis:
Dùng AI sinh tự động bộ test case đa dạng (bao gồm cả edge case) và tự đánh giá độ tuân thủ (LLM-as-a-Judge).

Quick gut:
[ ] No AI / process fix
[ ] Rule
[x] Workflow
[ ] Agent
[ ] Chưa biết
//
**Draft workflow Card #2:**

```text
CURRENT STATE — ___ phút

[1 ...] → [2 ...] → [3 ...]  <-- bottleneck

FUTURE STATE — ___ phút

[1 ...] → [2 ...] → [3 ... review]  <-- human boundary

Fallback: ...
```

File đính kèm: `01-individual-problem-scan-workflow-card-2.png`

-//
CURRENT STATE — 45 phút

[1 Sửa Prompt: 5'] → [2 Mở Terminal: 2'] → [3,4,5 Gõ test case 1,2,3 thủ công: 25'] <-- bottleneck → [6 Tự đối chiếu kết quả: 13']

FUTURE STATE — 5 phút

[1 Sửa Prompt: 2'] → [2 Chạy Script Auto-test: 1'] → [3 Dev review bảng tổng hợp Pass/Fail: 2'] <-- human boundary

Fallback: nếu Script Auto-test gặp lỗi → Dev chạy lại 1-2 test case nghi vấn bằng tay trong Terminal.

#### Problem Card #3 — 

```text
Problem 1 câu:

Actor:

Thời điểm / bối cảnh:

Current workflow 3-7 bước:
1.
2.
3.
4.
5.

Bottleneck:

Impact:

Success metric:

Non-AI alternative:

AI hypothesis:

Quick gut:
[ ] No AI / process fix
[ ] Rule
[ ] Workflow
[ ] Agent
[ ] Chưa biết
```
//
Problem 1 câu:
Người dùng/Tester gửi yêu cầu điều vận mập mờ, thiếu dữ liệu đầu vào (% pin, vị trí) làm AI trả lời sai ngữ cảnh hoặc phải hỏi lại nhiều lần.

Actor:
Tài xế/Người vận hành (User) và AI Dispatcher.

Thời điểm / bối cảnh:
Khi tài xế gặp sự cố trên đường và gửi tin nhắn báo cứu hộ vào hệ thống.

Current workflow 3-7 bước:
1. Tài xế gửi tin nhắn sự cố ("Xe tôi sắp hết điện rồi").
2. AI tiếp nhận tin nhắn.
3. AI kiểm tra không thấy % pin và vị trí.
4. AI phản hồi hỏi lại % pin.
5. Tài xế trả lời % pin.
6. AI phản hồi hỏi lại vị trí hiện tại.
7. AI mới đưa ra phương án xử lý cuối cùng.

Bottleneck:
Bước 4, 5, 6 — Vòng lặp hỏi đáp kéo dài do thiếu thông tin ban đầu, chiếm 40% tổng số lượt chat.

Impact:
Làm chậm thời gian xử lý cứu hộ khẩn cấp (tăng 3-4 lượt chat/phiên); gây ức chế cho tài xế đang gặp sự cố.

Success metric:
Giảm số lượt hỏi đáp từ 3-4 lượt xuống tối đa 1 lượt để thu thập đủ thông tin.

Non-AI alternative:
Tạo biểu mẫu (Form) bắt buộc nhập đủ trường: [Biển số xe, % Pin, Vị trí] trước khi bấm gửi.

AI hypothesis:
Thiết kế Prompt dạng Slot-Filling giúp AI nhận diện trường thông tin còn thiếu và gom hỏi đúng 1 câu duy nhất.

Quick gut:
[ ] No AI / process fix
[ ] Rule
[ ] Workflow
[x] Agent
[ ] Chưa biết//



**Draft workflow Card #3:**

```text
CURRENT STATE — ___ phút

[1 ...] → [2 ...] → [3 ...]  <-- bottleneck

FUTURE STATE — ___ phút

[1 ...] → [2 ...] → [3 ... review]  <-- human boundary

Fallback: ...
```

File đính kèm: `01-individual-problem-scan-workflow-card-3.png`

//
CURRENT STATE — 4 lượt chat (3 phút)

[1 User gửi tin mập mờ: 10s] → [2,3,4 AI hỏi lại % pin: 30s] <-- bottleneck → [5 User trả lời: 30s] → [6 AI hỏi lại vị trí: 30s] → [7 AI xử lý: 10s]

FUTURE STATE — 1 lượt chat (45 giây)

[1 User gửi tin mập mờ: 10s] → [2 AI phân tích slot thiếu & hỏi gom 1 câu chuẩn: 10s] → [3 User bổ sung đủ thông tin: 15s] → [4 Dev/Operator review đề xuất AI: 10s] <-- human boundary

Fallback: nếu User vẫn cung cấp thiếu → AI tự động chuyển cuộc gọi/tin nhắn sang nhân viên tổng đài hỗ trợ trực tiếp.---
//
### 2.3. Card muốn pitch nhất (chuẩn bị 2 phút)

**Card tôi muốn pitch nhất:**

```text

Problem Card #1 — AI Dispatcher bị lọt lưới khi gặp câu lệnh lách luật (Jailbreak)




**Vì sao (2-3 câu: workflow gì, số đo gì, impact gì):**

```text

Card này giải quyết trực tiếp quy trình kiểm thử ranh giới an toàn (Guardrails & System Prompt) cho AI Dispatcher — lõi vận hành cốt lõi của bài lab. Việc chốt chặn lỗi Jailbreak giúp giảm tỷ lệ lọt lưới từ 40% (2/5 test case) xuống 0%, đảm bảo AI luôn trả về bản nháp [DRAFT_ONLY] và đúng format JSON. Impact quan trọng nhất là loại bỏ rủi ro hệ thống tự động kích hoạt lệnh cứu hộ sai gây nguy hiểm thực tế, đồng thời tiết kiệm 60-90 phút tinh chỉnh prompt thủ công mỗi buổi dev.

**Câu hỏi tôi muốn nhóm challenge (1-2 câu hỏi đúng chỗ yếu):**

```text
1. Nếu người dùng dùng kịch bản Jailbreak hoàn toàn mới chưa từng có trong Few-shot ví dụ, liệu lớp Code Python (Output Validation) có thực sự chốt chặn thành công 100% định dạng đầu ra không?
2. Việc dùng Code Python để ép/chèn lại nhãn [DRAFT_ONLY] khi AI trả lời sai có làm biến dạng nội dung ngữ cảnh mà AI vừa phân tích không?
```

**AI phản biện Card (nếu có):**
- Điểm yếu AI chỉ ra:
- Tôi sửa gì:

### Self-check nộp phần 01
- [ ] Có 5+ problems + top 3 Cards đủ field
- [ ] Mỗi Card có workflow trước/sau + bottleneck + metric + fallback
- [ ] Đã chọn 1 card pitch + câu hỏi challenge
