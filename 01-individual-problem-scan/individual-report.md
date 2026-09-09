# 01 — Individual Problem Scan

> Bài cá nhân. Viết từ trải nghiệm thật của bạn, đừng bịa problem cho hay.
> Lăng kính chỉ là góc nhìn để soi việc: việc nào lặp lại, việc nào tốn công, việc nào AI đỡ được, việc nào người khác đang kêu. Một problem ghi 2 lăng kính là bình thường.
> Xem ví dụ đầy đủ ở `02-deliverable-example.md` phần 01.

## Thông tin

- Họ và tên:
- Mã học viên:
- Vai trò/bối cảnh của tôi (ví dụ PM thực tập, sinh viên năm 2):

## Bảng scan 5+ problems

Mỗi dòng ghi theo mạch: việc gì, ai chịu, đo bằng gì. Cột dấu hiệu thật bắt buộc có số: mất bao lâu, mấy lần/tuần, có log hay quote nào. Muốn bonus +3 thì scan 8-10 bài, cứ thêm dòng vào bảng.

| # | Lăng kính (góc nhìn) | Problem quan sát được (việc gì, khi nào) | Ai chịu ảnh hưởng? | Dấu hiệu thật (mất bao lâu, mấy lần/tuần, có log/quote nào) |
|---|---|---|---|---|
| VD | Lặp lại + Tốn thời gian | Mỗi sáng thứ Hai mở Jira, Sheets và Slack để gom số viết Weekly Report | Mình (người viết), EM/CEO (nhận trễ thì họp thiếu số) | Bấm giờ 3 tuần đều 80-90'/tuần, 2/4 tuần gửi trễ sau 10h |
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |
| 6 | | | | |

## Top 3 để pitch với nhóm

Lọc 3 bài actor rõ, workflow vẽ được, bottleneck ở 1 bước, đo được. Mỗi bài ghi 2-3 ý vì sao chọn và 1 điều còn chưa chắc.

| Rank | Problem | Vì sao chọn (2-3 ý) | Điều còn chưa chắc |
|---|---|---|---|
| VD | Weekly Report | Workflow 7 bước vẽ được ngay, đã bấm giờ 3 tuần, bottleneck gọn ở bước viết | Chưa biết chấm narrative "đủ tốt" bằng gì |
| 1 | | | |
| 2 | | | |
| 3 | | | |

## Problem Card #1 (bài muốn pitch nhất)

```text
Problem 1 câu (ai + mất bao lâu + nghẽn ở đâu + hậu quả):

Actor (ai làm, ai đọc/nhận, deadline nào):

Thời điểm / bối cảnh (khi nào, khung giờ nào, tần suất):

Current workflow 3-7 bước:
1.
2.
3.
4.
5.

Bottleneck (bước mấy, mất bao nhiêu phút, vì sao kẹt):

Impact (mất bao nhiêu phút/tuần, trễ thì ai bị ảnh hưởng):

Success metric (từ bao nhiêu xuống bao nhiêu, đếm bằng gì):

Non-AI alternative (template/checklist/dashboard giải được tới đâu):

AI hypothesis (AI vào sau bước nào, trước bước nào, ai kiểm tra):

Quick gut: [ ] No AI / [ ] Rule / [ ] Workflow / [ ] Agent / [ ] Chưa biết
```

Draft workflow trước/sau (ghi thời gian từng bước, đánh dấu bottleneck và fallback nếu AI sai):

```text
CURRENT STATE — ... phút (ghi thời gian từng bước, đánh dấu bottleneck)
[1 ...: ...'] → [2 ...] → ...

FUTURE STATE — ... phút (ghi bước nào máy làm, bước nào AI làm, bước nào người giữ)
[1 ...] → [2 ...] → ...

Fallback (AI tệ là thế nào, bỏ draft hay sửa, mất thêm bao lâu):
```

Nếu vẽ ảnh riêng thì đặt tên `01-individual-problem-scan-workflow-card-1.png` để nộp kèm.

## Problem Card #2

Viết giống cấu trúc card #1: problem 1 câu, actor, bối cảnh, workflow 3-7 bước, bottleneck, impact, metric, non-AI alternative, AI hypothesis và quick gut. Bài này viết ngắn hơn cũng được nhưng bắt buộc phải có actor cụ thể, bottleneck ở 1 bước, và metric đo được.

## Problem Card #3

Viết giống card #2. Nếu bài này yếu hơn thì ghi rõ điều còn chưa chắc để nhóm challenge giúp bạn.

## Card tôi muốn pitch nhất và câu hỏi cho nhóm

- Card muốn pitch nhất (ghi tên 1 bài trong top 3):
- Vì sao (2-3 câu: workflow gì, số đo gì, impact gì):
- Câu hỏi muốn nhóm challenge tôi (ví dụ workflow có thật không, metric đo được không, scope có to quá không):

## Tự kiểm trước khi nộp

- [ ] [12đ] Có 5+ problems từ việc thật, mỗi dòng có actor và dấu hiệu đo được. Top 3 đủ rõ để pitch 2 phút.
- [ ] [12đ] Pitch được mạch ai đau, workflow nào, nghẽn ở bước nào. Có ít nhất 1 câu hỏi challenge bài của bạn khác.
- [ ] Draft workflow có thời gian từng bước, bottleneck và fallback nếu AI sai.
