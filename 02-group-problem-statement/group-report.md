# 02 — Group Problem Statement (bản nộp nhóm)

> Nhóm 3-4 người làm chung 1 bản, rồi mỗi bạn copy bản cuối vào repo cá nhân.
> Nhóm chỉ chọn 1 candidate problem để đào sâu, chưa viết Statement ngay từ đầu.
> Xem ví dụ đầy đủ ở `02-deliverable-example.md` phần 02.

## Thành viên nhóm

| STT | Họ và tên | Mã học viên | Vai trò trong nhóm (ví dụ vẽ workflow, research, viết Statement) |
|-----|-----------|-------------|----|
| 1   |           |             |    |
| 2   |           |             |    |
| 3   |           |             |    |
| 4   |           |             |    |

## 1. Nhật ký hội tụ (từ 9-12 candidates về 1)

Mỗi người mang top 3 tới pitch, nhóm gom bài na ná thành cụm rồi shortlist và chấm điểm. Không vote ngay từ đầu vì vote sớm dễ chọn bài nghe hay chứ không phải bài làm được.

### 3.1 Ai pitch bài gì (mỗi người 3 bài, mỗi bài 1-2 phút)

| # | Người đưa ra | Candidate problem | Người gặp vấn đề | Điểm nghẽn ở bước nào | Cảm nhận nhanh của nhóm |
|---|---|---|---|---|---|
| VD | Minh | Weekly Report | Minh, EM/CEO | Bước viết narrative 25' | Workflow rõ, có số đo |
| 1 | | | | | |
| 2 | | | | | |
| 3 | | | | | |
| 4 | | | | | |
| 5 | | | | | |
| 6 | | | | | |
| 7 | | | | | |
| 8 | | | | | |
| 9 | | | | | |

### 3.2 Cluster (gom bài na ná thành 3-4 cụm để thấy pattern)

| Cluster | Candidates trong cụm | Pattern chung (điểm giống nhau) |
|---|---|---|
| VD Báo cáo/tổng hợp | Weekly Report, meeting recap | Gom nhiều nguồn rồi viết lại cho người khác đọc |
| A | | |
| B | | |
| C | | |

### 3.3 Shortlist (giữ 2-3 bài trả lời được 7 câu hỏi: ai hiểu workflow thật, actor cụ thể, bottleneck 1 bước, đo được, vẽ được before/after, so được R/W/A, kịp trong lab)

| Candidate | Vì sao vào shortlist (2-3 ý) | Rủi ro / điều chưa rõ |
|---|---|---|
| VD Weekly Report | Đã bấm giờ 3 tuần, workflow 7 bước rõ | Baseline mới là số của 1 người, cần hỏi thêm |
| | | |
| | | |

### 3.4 Score 1-5 (chấm để ép nói lý do, không cần tuyệt đối. Bài nào điểm thấp ở cột làm kịp trong lab thì nên loại dù tổng cao)

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm kịp trong lab | So được R/W/A | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| VD Weekly Report | 5 | 5 | 4 | 5 | 5 | 5 | 5 | 34 |
| | | | | | | | | |
| | | | | | | | | |

- Candidate nhóm chọn (ghi 1 bài duy nhất):
- Vì sao chọn (4-5 câu: workflow gì, số đo gì, hỏi được ai, research được gì, vẽ before/after ra sao):
- Vì sao không chọn các bài còn lại (mỗi bài 2-3 câu: vướng gì, scope to quá ở đâu):
- Disagreement trong nhóm và cách chốt (ai lo gì, nhóm xử lý ra sao):

## 2. Kiểm chứng nhanh + research

### Validation (hỏi ít nhất 2-3 người, ghi quote nguyên văn đừng chỉ ghi đa số đồng ý)

| Nguồn | Số người | Tín hiệu xác nhận (kèm quote) | Tín hiệu phản bác | Nhóm sửa problem thế nào |
|---|---:|---|---|---|
| VD Interview 3 PM | 3 | 2/3 vẫn viết tay, đau ở đoạn viết. Quote: "lấy số 10 phút xong, viết cho sếp hiểu mới mất cả buổi" | 1 bạn chỉ cần dashboard là đủ | Thu hẹp từ "tự động report" về "draft narrative từ data có sẵn" |
| Interview | | | | |
| Survey/poll/log | | | | |

Insight sau validation (2-3 câu: pain thật nằm ở bước nào, bài nào chỉ cần template khỏi cần AI):

```text

```

### Research tool có sẵn (ít nhất 2-3 tool kèm link docs chính thức, không dùng số liệu không verify được)

| Tool/case | Link | Họ giải bước nào trong workflow? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| | | | | | |
| | | | | | |
| | | | | | |

Takeaway (1 đoạn: có nên build mới không, hay đi theo Workflow nào, pattern chung học được là gì):

```text

```

## 3. Workflow trước/sau

File đính kèm (ảnh, Mermaid, Excalidraw đều được, miễn đọc được thời gian từng bước):

```text
VD: 02-group-problem-statement-workflow.png
```

```text
CURRENT STATE — ... bước, ... phút, ai làm toàn bộ
VD: [1 Export Jira 10' - Minh] → [2 Lấy Sheets 10'] → [3 Đọc Slack 15'] → [4 Tổng hợp 15'] → [5 Viết narrative 25' - bottleneck] → [6 Review 10'] → [7 Gửi 5']

FUTURE STATE — ... bước, ... phút (ghi rõ bước nào máy làm bằng Rule, bước nào AI làm, bước nào người giữ, fallback nếu AI sai ở đâu)
VD: [1 Auto-pull 2' - máy] → [2 AI cấu trúc 1'] → [3 AI draft 1'] → [4 Minh review 15' - boundary] → [5 Minh gửi 2']. Fallback: draft bịa số hoặc nhạt quá thì bỏ, viết tay như cũ.
```

| Metric | Trước | Sau kỳ vọng | Cách đo |
|---|---:|---:|---|
| Số bước | | | |
| Tổng thời gian | | | |
| Số bước thủ công | | | |
| Bottleneck chính | | | |
| Risk mới (AI sai kiểu gì) | | | |

## 4. Problem Statement v0 rồi v1

### v0 (viết sau validate và workflow, trước khi chốt R/W/A. Mỗi field 2-3 câu)

| Field | Nội dung | Gợi ý viết |
|---|---|---|
| **Actor** | | Ai làm, ai nhận, deadline nào |
| **Workflow** | | 5-7 bước kèm thời gian |
| **Bottleneck** | | 1 bước duy nhất và vì sao kẹt |
| **Impact** | | Số phút/tuần và hậu quả trễ |
| **Success Metric** | | Số trước, số sau, đếm bằng gì |
| **Boundary** | | Liệt kê làm và không làm |

### So sánh Rule / Workflow / Agent (so trên cùng bài này, đừng so chung chung)

| Mức | Phương án cụ thể cho bài nhóm | Khi nào đủ | Rủi ro | Chọn? |
|---|---|---|---|---|
| **Rule** | | | | |
| **Workflow** | | | | |
| **Agent** | | | | |

- Mức chọn (ghi 1 mức):
- Vì sao chọn (3-4 câu: bước nào Rule đủ, bước nào cần AI, ai review nên rủi ro kiểm soát được):
- Vì sao không chọn mức đơn giản hơn (2-3 câu: Rule giải được tới đâu, sao chưa đủ):

### v1 (lấy v0 sửa lại cho chặt hơn + 3 field mới)

| Field | Nội dung | Gợi ý viết |
|---|---|---|
| **Actor** | | |
| **Workflow** | | |
| **Bottleneck** | | |
| **Impact** | | |
| **Success Metric** | | |
| **Boundary** | | Làm và không làm thành 2 vế |
| **AI intervention point** | | Vào sau bước nào, trước bước nào |
| **Mức chọn** | | 1 mức và 1 câu vì sao |
| **Rủi ro & người thật kiểm tra** | | Rủi ro lớn nhất, ai kiểm tra bằng cách nào |

## 5. Quyết định cuối

Tick 6 câu này trước khi chốt. Câu nào trả lời không được thì quyết định phải là Not Yet, đừng cố Go.

| Câu hỏi | Yes / Not Yet / No | Ghi chú (viết câu đầy đủ) |
|---|---|---|
| Actor và workflow đã rõ chưa? | | VD: Rõ, workflow 7 bước đã bấm giờ |
| Baseline và metric đã đo được chưa? | | VD: Rồi, 90' xuống 30', đếm câu hỏi lại |
| Có đủ data không? | | VD: Đủ 3 nguồn Jira/Sheets/Slack |
| AI sai thì hậu quả có chịu được không? | | VD: Được vì Minh review trước khi gửi |
| Có người review không? | | VD: Có, Minh chịu trách nhiệm gửi |
| Có cách non-AI đơn giản hơn không? | | VD: Có template cho report đơn giản, AI chỉ cho report cần narrative |

- Decision: [ ] Go / [ ] Not Yet / [ ] No-Go
- Lý do (3-4 câu dựa trên bằng chứng, đừng ghi vì AI hay):
- Nếu Go thì pilot nhỏ nhất (data tuần nào, chạy bán thủ công ra sao, mỗi tuần đo 3 số nào):
- Nếu Not Yet thì cần validate gì thêm (hỏi ai, bao nhiêu người, để chắc số nào):
- Nếu No-Go thì làm gì thay AI (template, dashboard hay process fix):
- Exit/rollback nếu fail (ngưỡng nào thì dừng, ví dụ viết lại hơn 70% draft 2 tuần liên tiếp):

## Tự kiểm trước khi nộp

- [ ] [15đ] Workflow trước/sau có thời gian từng bước, bottleneck, boundary và fallback.
- [ ] [20đ] Problem Statement v0/v1 đủ 6 field + 3 field mới, metric có số trước/sau/cách đếm, boundary liệt kê làm/không làm.
- [ ] [15đ] So đủ No AI/Rule/Workflow/Agent trên cùng bài, ghi ai kiểm tra nếu AI sai.
- [ ] [10đ] Quyết định Go/Not Yet/No-Go có lý do bằng chứng và pilot hoặc rollback cụ thể.
