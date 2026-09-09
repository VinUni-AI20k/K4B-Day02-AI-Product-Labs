# Ví dụ bản nộp — Weekly Report trước và sau AI

> Ví dụ này cho thấy một bài nộp Day 02 hoàn chỉnh trông như thế nào. Đừng copy số liệu hay nội dung. Hãy học cách đi từ việc quan sát thật quanh mình, vẽ workflow hiện tại, kiểm chứng với người khác, đọc xem thị trường đã có gì, rồi mới viết Problem Statement và quyết định có nên dùng AI hay không.
>
> Lăng kính trong bài này chỉ là góc nhìn để soi việc, không phải nhãn phân loại chuẩn. Minh dùng 4 góc: việc nào lặp đi lặp lại mỗi tuần, việc nào mỗi lần làm rất nặng, việc nào AI có thể đỡ được một bước đọc/viết/tổng hợp, và việc nào người khác đang kêu.

Case ví dụ: **Tổng hợp weekly report**

Nhân vật ví dụ: Minh, Junior Product Manager tại một công ty SaaS khoảng 50 người. Mỗi tuần Minh phải tổng hợp số liệu từ Jira, Google Sheets và Slack để viết báo cáo tuần cho Engineering Manager và CEO. Minh đã bấm giờ 3 tuần liên tiếp nên con số 80-90 phút/tuần là số đo thật, không phải ước chừng.

## Vì sao đây là ví dụ tốt?

Bài này dễ học vì nó hội đủ 6 điểm mà rubric Day 02 yêu cầu. Actor là một người cụ thể (Minh) chứ không phải "user nói chung". Workflow lặp lại hằng tuần nên đo được baseline. Bước nghẽn nằm ở một bước duy nhất là viết narrative, chứ không phải đau lan man cả quy trình. Metric là thời gian nên đếm được bằng đồng hồ. Vì workflow có cả bước rõ (lấy số) lẫn bước mờ (viết đoạn văn), nhóm so được Rule với Workflow với Agent thay vì nhảy ngay sang Agent. Cuối cùng là vẽ được before/after để thấy AI nằm ở đâu và người kiểm tra ở đâu.

---

# 01 — Individual Problem Scan

## Scan rộng

Minh scan 10 problems, vượt mức tối thiểu 5.

> Lăng kính ở đây chỉ là góc nhìn để soi việc, không phải nhãn phân loại chuẩn. Một problem có thể soi bằng nhiều lăng kính cùng lúc. Dùng 4 góc này để khỏi sót việc: việc nào lặp đi lặp lại, việc nào mỗi lần làm rất nặng, việc nào AI có thể đỡ được một bước đọc/viết/tổng hợp, và việc nào người khác đang kêu.

| # | Lăng kính | Problem quan sát được | Ai chịu ảnh hưởng? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Lặp lại + Tốn thời gian | Mỗi sáng thứ Hai, Minh phải mở Jira, Google Sheets và Slack để gom số liệu rồi viết Weekly Report gửi trước buổi leadership sync | Minh (người viết và gửi), EM và CEO (nhận trễ thì họp thiếu context) | Bấm giờ 3 tuần liên tiếp đều ~80-90 phút/tuần; tuần nhiều thread Slack thì lố sang 2 tiếng và hay gửi trễ sau 10h sáng thứ Hai |
| 2 | Lặp lại | Mỗi thứ Hai copy sprint velocity và burndown từ Jira vào slide update tuần, làm tay từng số | Minh (người copy), EM (người đọc slide) | Tuần nào cũng làm, mất ~15-20 phút/lần; đã 2 lần copy nhầm số sprint cũ nên bị EM hỏi lại trong họp |
| 3 | Tốn thời gian | Nhận PRD dài 10-15 trang, phải đọc hết để hiểu context rồi mới comment được | Minh khi làm reviewer, design lead chờ comment để làm tiếp | Mỗi bản mất ~45 phút đọc + note; tuần có 2-3 PRD là mất gần nửa ngày, hay phải đọc lướt nên comment sót |
| 4 | Tốn thời gian | Sau mỗi buổi họp cross-team 4-5 người, Minh phải nghe lại record và viết meeting notes chia action items | Minh (người viết), cả team (đọc để biết việc của mình) | Mất ~30 phút/buổi, tuần 2 buổi; hay sót action vì mỗi người nhớ một kiểu, phải hỏi lại trên Slack |
| 5 | AI có thể tốt hơn | Mỗi sáng Minh mở Notion thấy 15-20 task dàn trải, phải tự đoán việc nào làm trước theo deadline và context nhắn trên Slack | Minh (người xếp việc), team member chờ Minh chốt thứ tự | Không có số đo cứng, nhưng Minh hay để task quan trọng trôi 1-2 ngày vì xếp theo cảm tính; muốn AI gợi ý thứ tự để tham khảo, Minh vẫn là người chốt |
| 6 | AI có thể tốt hơn + Pain từ người khác | Cần tìm lại quyết định cũ trong Slack (ví dụ vì sao đổi deadline, ai chốt scope) nhưng search keyword ra hàng chục thread rời rạc | Cả team, nhiều nhất là PM và newbie mới vào | Mỗi lần tìm mất ~10-15 phút, tuần gặp 2-3 lần; cách workaround hiện tại là hỏi lại người cũ trên Slack |
| 7 | Pain từ người khác | Designer nhận spec từ PM còn mập mờ (thiếu empty state, thiếu rule validate) nên phải hỏi lại mới dám vẽ | Designer (bị chặn việc), Minh (bị hỏi chen ngang) | Mỗi spec bị hỏi lại 2-3 vòng trên Slack/Figma comment; có spec delay 1 ngày vì chờ làm rõ |
| 8 | Pain từ người khác | Sáng thứ Hai CEO/EM nhắn hỏi update tuần nhưng report của Minh chưa gửi xong | CEO/EM (thiếu số để họp), Minh (bị dí) | Xảy ra 2/4 tuần gần nhất; đây là hậu quả của problem #1 chứ không phải problem độc lập, nên nhóm gộp vào #1 khi deep-dive |
| 9 | Tốn thời gian + Lặp lại | Cuối tháng phải mở 3-4 dashboard (Jira, Sheets, Mixpanel) để gom KPI vào một báo cáo tháng | Minh (người gom), manager (người đọc) | Mỗi tháng mất ~2 tiếng, hay lệch số giữa các nguồn nên phải dò lại công thức Sheets |
| 10 | Lặp lại | Mỗi sáng viết standup update cùng format (hôm qua/hôm nay/blocker) vào Slack | Minh (người viết) | Mất ~5-10 phút/ngày, cộng lại ~30-50 phút/tuần; việc nhỏ nhưng nhàm nên hay viết qua loa, thiếu blocker thật |

Vì sao phần scan này mạnh:

Bảng trên không phải list ý tưởng cho dài. Nó mạnh vì Minh scan rộng trước khi chốt, soi bằng cả 4 góc nhìn nên không sót việc. Mỗi dòng đều ghi ai chịu ảnh hưởng và dấu hiệu đo được (mất bao lâu, mấy lần/tuần, có log hay quote nào), chứ không ghi chung chung kiểu "cần tối ưu". Quan trọng nhất là Minh chưa hề nhắc tới chatbot hay agent ở bước này. Minh chỉ mô tả việc người đang làm thật, để dành chuyện chọn AI cho phase sau.

## Top 3

Minh lọc từ 10 problems xuống 3 bài đáng pitch nhất với nhóm. Tiêu chí lọc là actor có cụ thể không, workflow có vẽ được không, bottleneck có nằm ở một bước không, và impact có đo được không.

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Weekly Report | Workflow 7 bước vẽ được ngay, Minh đã có baseline bấm giờ 3 tuần, bottleneck nằm gọn ở bước viết narrative | Thế nào là narrative "đủ tốt" thì vẫn chưa có cách chấm, sợ mỗi người hiểu một kiểu |
| 2 | Review PRD | Pain thật vì tuần nào cũng có PRD 10-15 trang chờ comment, AI có thể giúp đọc và tóm tắt trước | Cải thiện chất lượng comment thì đo bằng gì, đếm số comment hay hỏi designer có đỡ bị chặn không |
| 3 | Slack Search | Nhiều người cùng đau, từ PM tới newbie, impact rộng nếu giải được | Chưa rõ lấy data Slack thế nào, scope dễ phình thành hệ thống search cho cả công ty |

Card Minh muốn pitch nhất là Weekly Report, vì đây là bài duy nhất Minh hiểu workflow từ đầu tới cuối và đã có số đo trong tay.

## Problem Card #1 — Weekly Report

**Problem 1 câu:**  
Mỗi sáng thứ Hai, Minh mất khoảng 80-90 phút để gom dữ liệu từ Jira, Sheets và Slack rồi viết Weekly Report. Bước viết narrative từ số liệu thô là tốn sức nhất, hay bị nhìn trang trắng không biết bắt đầu từ đâu, nên report thường gửi trễ sau 10h sáng.

**Actor:**  
Minh, Junior PM, là người chịu trách nhiệm gom số và gửi report. Người đọc là Engineering Manager và CEO, hai người cần report đúng giờ để có context trước buổi leadership sync lúc 11h.

**Thời điểm / bối cảnh:**  
Sáng thứ Hai hằng tuần, khung 8h30-10h, trước buổi leadership sync. Tuần nào nhiều thread Slack hoặc sprint có incident thì thời gian đội lên gần 2 tiếng.

**Current workflow:**

```text
1. Export Jira sprint data
2. Lấy metrics từ Google Sheets
3. Đọc Slack recap tuần
4. Tổng hợp vào Google Docs
5. Viết narrative: insight, highlight, risk, next action
6. Self-review + format
7. Gửi email cho stakeholders
```

Minh làm cả 7 bước một mình, không có ai chia. Handoff duy nhất là bước 7 gửi cho EM và CEO.

**Bottleneck:**  
Bước 5 — viết narrative từ raw data. Minh đã có số nhưng phải tự biến số thành câu chuyện: đâu là insight, đâu là risk, tuần tới làm gì. Bước này mất khoảng 25 phút, và là bước duy nhất không thể làm nhanh bằng cách copy-paste.

**Impact:**  
Riêng Minh mất 80-90 phút/tuần, tức khoảng 6 tiếng/tháng chỉ để viết report. Team có 3 PM làm việc tương tự nên tổng công sức rơi vào khoảng 4-4,5 tiếng/tuần cho cả team. Tác hại rõ nhất không phải số phút mà là report trễ: 2/4 tuần gần nhất Minh gửi sau 10h, EM phải họp mà chưa đọc số.

**Success metric:**  
Giảm tổng thời gian từ 80-90 phút xuống dưới 30 phút, đo bằng cách bấm giờ 4 tuần liên tiếp. Điều kiện kèm theo là chất lượng không tụt: số câu CEO/EM phải hỏi lại sau khi đọc report (đếm trong email và Slack thread) không tăng so với baseline hiện tại là 1-2 câu/tuần.

**Non-AI alternative:**  
Làm template report cứng + Jira dashboard tự cập nhật + checklist các mục phải có. Cách này giảm được thời gian format ở bước 6, Minh ước chừng tiết kiệm 10-15 phút. Nhưng nó không giải quyết bước 5, vì mỗi tuần số liệu và ngữ cảnh Slack đều khác nhau, template không tự viết câu chuyện được.

**AI hypothesis:**  
Sau khi Minh gom xong dữ liệu thô vào một doc, AI giúp cấu trúc lại dữ liệu và draft đoạn narrative 5-7 câu theo template highlight-risk-next. Minh vẫn là người đọc lại, đối chiếu số và sửa trước khi gửi. AI không được tự gửi mail.

**Quick gut:**  
Workflow. Vì các bước đi theo đường thẳng, AI chỉ cần hỗ trợ 2 bước ngôn ngữ ở giữa, còn đầu vào và đầu ra đều do Minh kiểm soát.

### Draft current workflow

Minh bấm giờ từng bước trong 3 tuần để biết chính xác thời gian đi đâu, chứ không ước chừng.

```text
CURRENT STATE — 90 phút

[1 Export Jira: 10']
→ [2 Lấy metrics: 10']
→ [3 Đọc Slack: 15']
→ [4 Tổng hợp vào Docs: 15']
→ [5 Viết narrative: 25']  <-- bottleneck
→ [6 Review + format: 10']
→ [7 Gửi: 5']
```

### Draft future workflow

Hướng đi là máy làm phần lấy và xếp dữ liệu, AI draft đoạn văn, Minh giữ quyền sửa và gửi. Nếu AI viết dở thì Minh bỏ draft và tự viết như cũ, không kẹt.

```text
FUTURE STATE — 21 phút

[1 Auto-pull data: 2']
→ [2 AI cấu trúc dữ liệu: 1']
→ [3 AI draft narrative: 1']
→ [4 PM review + edit: 15']  <-- human boundary
→ [5 PM gửi: 2']

Fallback: AI draft tệ, bịa số hoặc viết nhạt → PM bỏ draft và tự viết lại như workflow cũ.
```

## Problem Cards #2 và #3 — tóm tắt

Minh vẫn viết đủ 2 cards còn lại để có cái pitch với nhóm, nhưng viết ngắn hơn vì đây không phải bài chính.

| Card | Actor | Bottleneck | Metric | Quick gut | Vì sao chưa chọn làm #1 |
|---|---|---|---|---|---|
| Review PRD | Minh khi làm reviewer, design lead chờ comment | Phải đọc 10-15 trang mới hiểu đủ context để comment, mất ~45 phút/bản | Phấn đấu từ 45 phút xuống ~20 phút đọc + note, nhưng chưa biết đo chất lượng comment bằng gì | Workflow | Metric chất lượng khó thống nhất trong 1 buổi lab, dễ cãi nhau thế nào là comment tốt |
| Slack Search | Team member cần tìm quyết định cũ, nhiều nhất là newbie | Search keyword ra hàng chục thread, phải mở từng thread đọc, mất 10-15 phút/lần | Phấn đấu từ 10-15 phút xuống dưới 2 phút/lần tìm | Agent / Workflow | Cần quyền đọc toàn bộ Slack history, scope dễ phình thành search cho cả công ty, nhóm không đủ thời gian lab để làm |

---

# 02 — Group Problem Statement

## Group convergence

Nhóm 3-4 người, mỗi người mang top 3 tới. Tổng cộng khoảng 9-12 candidates nên nhóm không vote ngay. Nhóm gom các bài na ná nhau thành cụm, rồi mới shortlist và chấm điểm để chọn 1 bài đào sâu.

| Cluster | Candidate examples | Pattern chung |
|---|---|---|
| Báo cáo / tổng hợp thông tin | Weekly Report của Minh, meeting recap của Lan, lab progress summary của Tuấn | Đều phải gom thông tin từ nhiều nguồn rời rạc rồi viết lại cho người khác đọc và ra quyết định |
| Tìm kiếm / hỏi đáp tài liệu | Slack Search, LMS Search, FAQ lab | Đều kẹt ở bước tìm đúng thông tin trong đống tài liệu cũ, search keyword không ra |
| Review / feedback | Review PRD, check Problem Statement, review assignment | Đều phải đọc bản nháp dài và chỉ ra chỗ thiếu, khó ở chỗ thế nào là feedback tốt |
| Planning / follow-up | Action item tracking, deadline reminder | Đều đau sau cuộc họp: việc bị rơi, không ai nhớ ai làm gì, phải đi nhắc |

## Shortlist và score

Nhóm hỏi 7 câu trước khi chấm: có ai hiểu workflow thật không, actor có cụ thể không, bottleneck có nằm ở một bước không, impact có đo được không, có vẽ được before/after không, có so được Rule/Workflow/Agent không, và có làm kịp trong lab hôm nay không. Bài nào trả lời không được thì loại.

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Weekly Report | 5 | 5 | 4 | 5 | 5 | 5 | 5 | 34 |
| Slack Search | 4 | 4 | 4 | 4 | 3 | 4 | 4 | 27 |
| Review PRD | 4 | 5 | 3 | 3 | 5 | 4 | 4 | 28 |

Điểm 4 ở cột evidence của Weekly Report là vì baseline 80-90 phút hiện mới là số của Minh, chưa hỏi thêm PM khác. Điểm 3 ở cột làm trong lab của Slack Search là vì bài đó cần quyền đọc Slack history, nhóm thấy không kịp.

Nhóm chọn: **Weekly Report**.

Vì sao chọn:

Bài này có workflow 7 bước mà Minh đã bấm giờ thật nên cả nhóm nhìn vào hiểu ngay, không phải đoán. Baseline thời gian rõ nên đặt target dưới 30 phút rất dễ kiểm. Nhóm có thể hỏi nhanh 2-3 PM khác trong giờ lab để validate, không cần ra ngoài tìm user lạ. Trên thị trường đã có sẵn tool làm dashboard và tóm tắt nên nhóm research được ngay, khỏi nghĩ trong chân không. Cuối cùng là vẽ before/after rất rõ: máy lấy số, AI viết nháp, người review.

Vì sao không chọn các bài còn lại:

Slack Search nghe thì impact rộng vì cả team cùng đau, nhưng data access phức tạp. Chỉ cần thiếu quyền đọc private channel là kẹt, mà có đủ quyền thì scope dễ trượt sang xây cả hệ thống search. Nhóm thấy 30 phút validation không đủ để chốt scope nên gác lại.

Review PRD thì workflow rõ, nhưng metric chất lượng khó thống nhất. Giảm từ 45 phút xuống 20 phút thì dễ, nhưng comment nhanh hơn có tốt hơn không thì mỗi người một ý. Trong thời gian lab, nhóm không muốn cãi nhau về định nghĩa comment tốt.

## Quick validation

Nhóm không chốt problem ngay mà đi hỏi nhanh 3 PM/PO quen biết và làm 1 poll nhỏ trong lớp. Mỗi người được hỏi 5 câu: lần gần nhất gặp vấn đề là khi nào, đang xử lý bằng workflow nào, bước nào khó chịu nhất, mất bao lâu, và muốn điều gì thay đổi.

| Nguồn | Số người | Tín hiệu xác nhận | Tín hiệu phản bác | Nhóm sửa problem thế nào |
|---|---:|---|---|---|
| Quick interview | 3 PM/PO | 2/3 người vẫn viết weekly/monthly update thủ công. Cả hai đều nói đau nhất ở đoạn biến số thành đoạn văn, một bạn nói nguyên văn "lấy số thì 10 phút xong, ngồi viết sao cho sếp hiểu mới mất cả buổi" | 1 người nói team họ chỉ cần nhìn dashboard là đủ họp, không cần narrative | Thu hẹp problem lại: không phải "tự động hóa report" nói chung, mà là "draft đoạn narrative từ data đã gom sẵn". Bài nào chỉ cần số thì dashboard là đủ, khỏi cần AI |
| Mini poll trong lớp | 6 bạn | 4/6 từng phải tổng hợp report/update từ nhiều nguồn, 3 bạn chấm mức đáng giải quyết 4-5/5 | 2 bạn nói report của họ chỉ cần điền template là xong, không cần AI viết | Thêm phương án không dùng AI vào bài: template + dashboard cho các report đơn giản, AI chỉ vào các report cần narrative |

Insight sau validation:

```text
Pain thật không nằm ở việc "lấy số" đơn thuần, vì lấy số thì dashboard làm được.
Pain nằm ở đoạn biến nhiều nguồn rời rạc (Jira + Sheets + Slack) thành một đoạn narrative
đủ rõ để EM và CEO ra quyết định trong buổi sync. Ai chỉ cần số thì không cần AI.
```

## Research giải pháp

Nhóm tìm các hướng đã có sẵn để khỏi nghĩ trong chân không, và để biết mình không cần build từ đầu. Mỗi tool nhóm đều xem nó giải được bước nào trong workflow 7 bước, và còn hổng bước nào.

| Nguồn / tool / case | Link | Họ giải quyết phần nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| Atlassian Jira Reports | https://www.atlassian.com/software/jira/features/reports | Làm dashboard và report từ data Jira ở bước 1-2 | Mạnh với số liệu structured, ra chart nhanh | Không viết được business narrative theo context Slack và Sheets, mỗi tuần ngữ cảnh khác nhau | Phần lấy số cứ dùng rule và dashboard có sẵn, đừng tốn sức build lại. AI chỉ cần vào bước viết |
| Slack AI | https://slack.com/help/articles/25076892548883-Guide-to-Slack-AI | Tóm tắt và search hội thoại trong Slack ở bước 3 | Recap thread dài khá tốt, đỡ phải lội channel | Chỉ là một nguồn trong 3 nguồn, không gom được Jira và Sheets | Dùng output của Slack AI làm đầu vào cho workflow, không coi nó là solution hoàn chỉnh |
| Gemini in Drive | https://support.google.com/drive/answer/15141241 | Tóm tắt nội dung file Docs và Sheets ở bước 4 | Tóm tắt tài liệu nhanh, tiện vì team đã dùng Drive | Hay tóm tắt chung chung, cần kiểm lại nguồn, tuyệt đối không để tự gửi | Bài học về boundary: AI draft thì được, người phải review trước khi gửi |
| Fellow AI Meeting Notes | https://fellow.ai/features/ai | Viết meeting notes và action items có cấu trúc | Recap họp gọn, chia action rõ | Không giải bài toán Jira và Sheets của weekly report | Học pattern chung của các sản phẩm tốt: AI viết nháp, người thật duyệt |

Research takeaway:

```text
Không nên build agent tự chạy toàn bộ báo cáo ngay, vì phần lấy số đã có tool làm tốt.
Hướng hợp lý hơn là Workflow đi theo đường thẳng: script tự kéo data ở các bước rõ,
AI chỉ draft đoạn narrative ở bước 5, PM review ở bước 6 trước khi gửi. Nhiều sản phẩm
ngoài thị trường cũng đi theo pattern này: AI draft, người duyệt.
```

## Workflow before/after

File nhóm nộp kèm (ảnh hoặc Mermaid để dễ đọc trong repo):

```text
02-group-problem-statement-workflow.png/pdf/md
```

Nội dung workflow bản nhóm vẽ kỹ hơn bản cá nhân. Mỗi bước đều ghi ai làm, mất bao lâu, và handoff ở đâu.

```text
CURRENT STATE — 7 bước, 90 phút, Minh làm tay toàn bộ

[1 Export Jira: 10']
→ [2 Lấy metrics từ Sheets: 10']
→ [3 Đọc Slack recap: 15']
→ [4 Tổng hợp vào Docs: 15']
→ [5 Viết narrative: 25']  <-- bottleneck
→ [6 Review + format: 10']
→ [7 Gửi email: 5']

FUTURE STATE — 5 bước, 21 phút, máy + AI làm 3 bước đầu

[1 Auto-pull Jira/Sheets: 2']  -- Rule/script, máy tự kéo
→ [2 AI cấu trúc input: 1']    -- Workflow step, xếp dữ liệu vào template
→ [3 AI draft narrative: 1']   -- Workflow step, viết nháp 5-7 câu
→ [4 PM review + edit: 15']    -- Human boundary, Minh đối chiếu số và sửa
→ [5 PM gửi: 2']               -- Minh bấm gửi

Fallback:
Nếu AI draft sai số, bịa insight hoặc viết nhạt tới mức Minh phải viết lại hơn 70%
thì Minh bỏ draft và tự viết như workflow cũ. Lỗi số liệu thì dừng dùng AI cho report đó.

Bottleneck mới:
Bước 4 PM review + edit. Đây là bottleneck chấp nhận được vì đó là điểm kiểm soát
chất lượng. Thà review 15 phút còn hơn gửi nhầm số cho CEO.
```

Before/after impact:

| Metric | Trước | Sau kỳ vọng | Ghi chú và cách đo |
|---|---:|---:|---|
| Tổng thời gian | 90 phút | Dưới 30 phút | Target chính, đo bằng bấm giờ 4 tuần liên tiếp |
| Số bước | 7 | 5 | Ít bước hơn, và effort ở bước viết giảm hẳn |
| Bước thủ công | 7/7 | 2/5 | Minh chỉ còn review và gửi, 3 bước đầu máy làm |
| Bottleneck chính | Viết narrative 25' | Review/edit 15' | Chuyển bottleneck về chỗ có người kiểm soát, đây là human boundary |
| Risk mới | Không có | AI bịa số, bỏ sót insight | Đo bằng số lỗi phải sửa mỗi tuần, nếu tăng thì rollback |

## Problem Statement v0

Bản v0 viết sau khi đã validate và vẽ workflow, nhưng trước khi chốt chọn Rule hay Workflow hay Agent. Bản này còn hơi thô, metric chất lượng vẫn chưa có cách chấm.

| Field | Nội dung |
|---|---|
| **Actor** | Minh, Junior PM, người chịu trách nhiệm viết và gửi weekly report cho EM và CEO trước buổi leadership sync thứ Hai 11h. |
| **Workflow** | Mỗi sáng thứ Hai, Minh export Jira, lấy metrics từ Sheets, đọc Slack recap, tổng hợp vào Docs, viết narrative, tự review rồi gửi email. Cả 7 bước hiện làm tay. |
| **Bottleneck** | Bước 5 viết narrative mất khoảng 25 phút. Minh phải tự biến số liệu thô thành insight, highlight, risk và next action nên hay bị nhìn trang trắng. |
| **Impact** | Minh mất 80-90 phút/tuần, cả team 3 PM mất 4-4,5 tiếng/tuần. 2/4 tuần gần nhất report gửi trễ sau 10h khiến EM họp thiếu context. |
| **Success Metric** | Giảm tổng thời gian từ 80-90 phút xuống dưới 30 phút trong 4 tuần đo liên tiếp. Giữ số câu hỏi lại từ CEO/EM ở mức 1-2 câu/tuần như hiện tại, không tăng. |
| **Boundary** | AI không được tự gửi report. AI không được bịa số liệu ngoài 3 nguồn Jira/Sheets/Slack đã cho. Minh là người duy nhất quyết nội dung cuối cùng. |

## Rule / Workflow / Agent

Nhóm so cả 3 mức trên cùng một workflow để khỏi nhảy sang Agent quá sớm. Câu hỏi dùng để so là: Rule có giải được 70-80% case không, các bước có đủ rõ để đi theo đường thẳng không, và nếu AI sai thì ai phát hiện.

| Mức | Phương án cho bài này | Khi nào đủ | Rủi ro | Chọn? |
|---|---|---|---|---|
| **Rule** | Template cứng, script tự kéo Jira và Sheets, dashboard cố định | Đủ cho các report chỉ cần số, ví dụ team chỉ cần nhìn velocity là họp được | Không xử lý được narrative vì mỗi tuần ngữ cảnh Slack đều khác nhau | Dùng một phần cho bước 1-2, không chọn làm toàn bộ |
| **Workflow** | Script kéo data, rồi AI cấu trúc input, rồi AI draft narrative, cuối cùng Minh review và gửi | Hợp vì workflow đi thẳng một đường, AI chỉ hỗ trợ 2 bước ngôn ngữ ở giữa | Draft có thể sai số hoặc viết nhạt, nhưng Minh review 15 phút nên bắt được lỗi | Chọn |
| **Agent** | Agent tự quyết định mở tool nào, đọc thêm nguồn nào, hỏi thêm ai, rồi tự gửi report | Chỉ cần khi workflow rẽ nhiều nhánh và AI phải tự lập kế hoạch động | Quá rộng cho lab: cần cấp nhiều quyền đọc mail và Slack, khó kiểm soát, sai một bước là gửi nhầm cho CEO | Chưa chọn |

Mức chọn:

```text
Workflow.
```

Vì sao chọn Workflow mà không phải Rule hay Agent:

Phần lấy số liệu ở đầu hoàn toàn là việc rõ ràng nên script và dashboard là đủ, khỏi cần AI. Phần khó là viết đoạn văn từ số liệu và context Slack, chỗ này cần AI hỗ trợ ngôn ngữ và tổng hợp. Minh vẫn giữ bước review 15 phút nên rủi ro bịa số kiểm soát được. Agent thì thừa vì workflow này không cần tự rẽ nhánh hay tự gọi tool lạ, đi thẳng một đường là xong.

Vì sao không chọn mức đơn giản hơn (chỉ dùng Rule):

Nhóm đã thử nghĩ chỉ dùng template cứng. Template giúp report đều tay nhưng không viết được câu chuyện khác nhau mỗi tuần. Tuần có incident và tuần bình thường mà viết giống nhau thì EM đọc không hiểu vì sao số đỏ. Nên Rule chỉ giải được phần vỏ, không giải được bottleneck ở bước 5.

## Problem Statement v1

Bản v1 viết sau khi đã chốt chọn Workflow. Khác v0 ở 3 điểm: thêm điểm AI can thiệp chính xác, thêm mức chọn, và ghi rõ ai kiểm tra rủi ro.

| Field | Nội dung |
|---|---|
| **Actor** | Minh, Junior PM, người viết và gửi weekly report cho EM và CEO trước 10h sáng thứ Hai. |
| **Workflow** | Sáng thứ Hai: export Jira, lấy metrics Sheets, đọc Slack recap, tổng hợp vào Docs, viết narrative, review rồi gửi email. Hiện 7 bước làm tay 90 phút. |
| **Bottleneck** | Bước viết narrative mất ~25 phút vì phải biến số thô thành insight, risk và next action. Hay bị kẹt ở câu đầu tiên. |
| **Impact** | Minh mất 80-90 phút/tuần, cả team mất 4-4,5 tiếng/tuần. Report trễ 2/4 tuần khiến EM họp thiếu số. |
| **Success Metric** | Thời gian từ 80-90 phút xuống dưới 30 phút trong 4 tuần đo liên tiếp. Số câu hỏi lại từ leadership giữ ở 1-2 câu/tuần, không tăng. Đếm trong email và Slack thread sau khi gửi. |
| **Boundary** | Làm: chỉ dùng data Jira/Sheets/Slack đã gom, chỉ draft narrative. Không làm: không tự gửi mail, không bịa số, không thay Minh chốt nội dung cuối. |
| **AI intervention point** | Can thiệp sau khi data 3 nguồn đã gom vào một doc thô, và trước khi Minh viết narrative. Tức là thay thế bước 5, không đụng tới bước gửi. |
| **Mức chọn** | Workflow: script kéo data, AI cấu trúc và draft narrative, Minh review 15 phút rồi gửi. |
| **Rủi ro & người thật kiểm tra** | Rủi ro lớn nhất là AI bịa số, bỏ sót risk quan trọng, hoặc viết nhạt. Minh là người kiểm tra: đối chiếu từng con số với nguồn, đọc lại risk trước khi bấm gửi. |

## Final decision

Nhóm kiểm 6 câu trước khi chốt: actor và workflow đã rõ chưa, baseline và metric đã đo được chưa, có đủ data không, AI sai thì hậu quả có chịu được không, có ai review không, và có cách không dùng AI đơn giản hơn không. Cả 6 câu đều trả lời được nên nhóm dám Go nhỏ.

Decision:

```text
Go với scope nhỏ, làm pilot 2 tuần rồi mới quyết tiếp.
```

Pilot nhỏ nhất để kiểm chứng trong 2 tuần tới:

- Lấy data thật từ 2 tuần report gần nhất của Minh, không dùng data bịa.
- Chạy bán thủ công: Minh paste tóm tắt Jira/Sheets/Slack vào một prompt chuẩn của nhóm, AI draft narrative, Minh bấm giờ phần edit.
- Mỗi tuần ghi lại 3 số: tổng thời gian, số phút phải sửa draft, và số lỗi số liệu AI mắc.
- Cuối tuần 2 họp 15 phút xem có đạt dưới 30 phút không.

Exit / rollback nếu fail:

- Nếu 2 tuần liên tiếp Minh vẫn phải viết lại hơn 70% draft thì hạ xuống chỉ dùng template và dashboard, dừng dùng AI viết.
- Nếu AI bịa số liệu hoặc trích sai nguồn dù chỉ 1 lần trong report gửi đi thì dừng ngay, quay về viết tay và xem lại prompt và boundary.

Decision rationale:

Bài này problem rõ vì đã validate với 3 PM và có baseline bấm giờ. Workflow rõ 7 bước nên biết AI nằm ở bước 5. Metric rõ vì có cả thời gian và cách đếm câu hỏi lại. Nhóm đã giữ lại phần non-AI là script kéo số và template, AI chỉ ôm một bước ngôn ngữ. Cuối cùng là human review rõ ràng: Minh đọc và chịu trách nhiệm trước khi gửi, nên sai số không lọt ra ngoài.

---

# 03 — Individual Reflection Example

Minh viết reflection sau lab, không nhờ AI viết thay. Minh chỉ dùng AI để gợi ý câu hỏi tự soi, còn câu trả lời đều là trải nghiệm thật trong nhóm.

## Đóng góp của Minh trong nhóm

| Hoạt động | Minh đã làm gì? | Kết quả cụ thể |
|---|---|---|
| Scan cá nhân | Mang tới 10 problems đã bấm giờ, trong đó Weekly Report có số liệu 3 tuần | Nhóm có sẵn 3-4 bài về reporting để gom thành cụm, khỏi mất thời gian nghĩ từ đầu |
| Pitch | Pitch Weekly Report trong 2 phút: ai đau, workflow 7 bước, nghẽn ở bước viết 25 phút | Bài vào shortlist vì cả nhóm hiểu ngay, không phải hỏi lại workflow |
| Challenge | Hỏi nhóm "Slack Search thì lấy quyền đọc private channel kiểu gì, scope có to quá cho 30 phút không" | Nhóm nhận ra bài đó data access khó nên hạ điểm làm trong lab xuống 3, loại khỏi vòng cuối |
| Workflow | Vẽ bản current 7 bước và future 5 bước, ghi rõ fallback nếu AI bịa số | Nhóm lấy bản này làm workflow cuối, chỉ sửa thêm cột actor và thời gian |
| Research | Tìm 4 nguồn chính thức: Jira Reports, Slack AI, Gemini Drive, Fellow | Nhóm thấy pattern chung là AI draft và người duyệt, nên không ai còn đòi build agent nữa |
| Rule / Workflow / Agent | Viết bảng so sánh và lập luận vì sao Rule chỉ giải được phần lấy số | Nhóm thống nhất chọn Workflow trong 10 phút, không tranh cãi |

## Bảng dùng AI trong reflection

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai/hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình |
|---|---|---|---|---|
| Scan | Nhờ AI gợi ý thêm problems theo vai trò PM sau khi đã tự scan 6 ý | Nhắc thêm 2 ý là Slack Search và PRD Review mà Minh quên | Gợi ý 3 ý quá rộng kiểu "xây trợ lý AI toàn năng cho PM", không có workflow | Bỏ hết ý không có người thật và số đo, chỉ giữ ý Minh từng làm |
| Workflow | Nhờ AI chuyển mô tả 7 bước thành Mermaid để nộp cho đẹp | Vẽ nhanh hơn vẽ tay, đúng thứ tự bước | AI tự gộp bước viết narrative và review thành một, làm mất bottleneck | Tách lại thành 2 bước vì bottleneck nằm ở viết, còn review là boundary để kiểm soát chất lượng |
| Research | Nhờ AI tìm tool tương tự đã giải bài toán report | Gợi ý đúng 4 cái tên Jira, Slack AI, Gemini, Fellow | Bịa thêm claim "tiết kiệm 70% thời gian" mà không có nguồn | Bỏ hết số liệu không verify, chỉ giữ link docs chính thức và tự đọc |
| Problem Statement | Nhờ AI đóng vai PM khó tính phản biện bản v0 | Chỉ ra đúng chỗ yếu là metric chất lượng chưa có cách chấm | Đề xuất nhảy sang Agent tự gửi report cho nhanh | Nhóm giữ Workflow vì Agent rủi ro gửi nhầm, Minh là người chốt |

## Bài học của Minh

Bài học lớn nhất với Minh là problem tốt không phải problem nghe AI nhất. Hồi đầu Minh cũng ham bài Slack Search vì nghe giống Agent cho ngầu. Nhưng khi vẽ workflow ra mới thấy bài Weekly Report tuy chán hơn mà đo được, làm được, và biết AI nằm ở đâu. Vẽ workflow giúp Minh thấy Rule đã đủ cho phần lấy số, chỉ còn bước viết là cần AI. Đó là lý do nhóm không cần Agent.

Research cũng dạy Minh một điều: đừng copy tool, hãy copy pattern. Cả 4 sản phẩm Minh đọc đều đi chung một pattern là AI viết nháp và người duyệt. Pattern này hợp với team nhỏ vì sai số không lọt ra ngoài.

Điều khó nhất khi viết Problem Statement với Minh là viết boundary. Viết metric thì dễ vì có đồng hồ, nhưng viết "AI không được làm gì" thì phải nghĩ tới các ca fail: bịa số, tự gửi mail, chốt nội dung thay mình. Minh phải sửa 2 lần mới ghi đủ.

Nếu làm lại:

```text
Tôi sẽ validate với 4-5 PM ngoài team trước khi chốt metric 90 phút xuống 30 phút.
Baseline hiện tại chủ yếu là số của tôi trong 3 tuần, mẫu còn nhỏ. Nếu có thêm số
của 2 team khác thì target 30 phút sẽ chắc hơn, và nhóm cũng đỡ bị hỏi là số tự bịa.
```

---

*Ví dụ bản nộp — Day 02 Lab v2*
