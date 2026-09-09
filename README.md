# Day 02 Lab — Tìm Đúng Bài Toán Cho AI

> Lab này không thi ai build AI ngầu nhất. Lab chấm ai tìm đúng việc để làm.
> Đi theo mạch này: quan sát vấn đề thật quanh mình, vẽ workflow hiện tại ra giấy, tìm bước nghẽn nhất, rồi mới quyết định có nên dùng Rule, Workflow hay Agent. Viết Problem Statement sao cho người khác đọc vào là đo được và biết ranh giới ở đâu, cuối cùng chốt Go, Not Yet hay No-Go kèm lý do.

## Tài liệu trong folder này

Folder này chỉ giữ 2 file bạn cần đọc:

| File | Dùng để làm gì | Đọc khi nào |
|---|---|---|
| `01-worksheet.md` | Hướng dẫn chính cho toàn bộ lab 4 tiếng. Mỗi phase đều có sẵn gợi ý quan sát, prompt AI, và checklist tự kiểm ngay trong phase đó nên bạn không phải nhảy qua file khác. | Mở xuyên suốt lab, làm tới phase nào đọc phase đó. |
| `02-deliverable-example.md` | Bài mẫu của bạn Minh về Weekly Report. Đọc để biết output đạt yêu cầu trông như thế nào, từ bảng scan tới workflow tới quyết định cuối. Đừng copy số liệu, hãy học cách lập luận. | Đọc trước 15 phút ở Phase 0, rồi mở ra đối chiếu mỗi khi bí. |

## Cấu trúc repo nộp bài

Mỗi học viên nộp **một repo cá nhân** đặt tên theo mã và tên của mình. Trong repo có 3 thư mục tương ứng 3 đầu việc: việc cá nhân, việc nhóm, và reflection cá nhân.

```text
Day02-MãHọcViên-HọVàTên/
├── README.md
├── 01-individual-problem-scan/
├── 02-group-problem-statement/
└── 03-individual-reflection/
```

Trong đó:

- `01-individual-problem-scan/`: bài cá nhân. Gồm bảng scan ít nhất 5 problems từ trải nghiệm thật, top 3 Problem Cards đủ rõ để pitch, và draft workflow trước/sau cho từng card.
- `02-group-problem-statement/`: **bản nộp nhóm**. Nhóm 3-4 người làm chung một bản gồm nhật ký hội tụ từ 9-12 candidates về 1 bài, kiểm chứng nhanh với người thật, research tool có sẵn, workflow trước/sau, Problem Statement v0 rồi v1, bảng so Rule/Workflow/Agent, và quyết định Go/Not Yet/No-Go. Mỗi học viên copy bản cuối này vào repo cá nhân của mình.
- `03-individual-reflection/`: reflection cá nhân. Viết trung thực mình đã dùng AI ở đâu, AI sai chỗ nào, mình sửa bằng ý của mình ra sao, vai trò của mình trong nhóm là gì, và nếu làm lại sẽ đổi gì.

Nếu có file phụ như ảnh workflow, Mermaid, survey screenshot, research notes, đặt cùng prefix với phần liên quan:

```text
01-individual-problem-scan-workflow-card-1.png
02-group-problem-statement-workflow.pdf
02-group-problem-statement-research-notes.md
```

## Đọc file nào để làm gì?

Lab 4 tiếng đi nhanh nên đọc đúng thứ tự sẽ đỡ rối:

1. Mở `02-deliverable-example.md` trước, đọc lướt 15 phút ở Phase 0 để biết đích đến. Chú ý cách bạn Minh đi từ bảng scan sang workflow rồi sang quyết định, chứ đừng chép số liệu của Minh.
2. Làm theo `01-worksheet.md` từ Phase 1 đến Phase 7. Worksheet là hướng dẫn tư duy từng bước, không phải form điền cho xong. Tới phase nào thì đọc kỹ gợi ý và checklist của phase đó.
3. Khi nộp, kiểm tra repo cá nhân có đủ 3 phần không: scan cá nhân, bản nhóm đã copy về, và reflection cá nhân viết bằng trải nghiệm thật.

## Tiêu chí đánh giá (100 điểm)

Điểm của mỗi học viên gồm **điểm nhóm 60 điểm** và **điểm cá nhân 40 điểm**. Điểm nhóm chấm trên bản nộp chung của nhóm, nhưng mỗi bạn vẫn phải copy bản đó vào repo cá nhân. Bài không cần chọn Agent mới được điểm cao. Điểm nằm ở chỗ nhóm có hiểu đúng bài toán không, lập luận có rõ không, và có biết vì sao nên hoặc không nên dùng AI không. Chọn Rule mà đúng vẫn hơn chọn Agent mà sai.

Ngoài 100 điểm chính, học viên có thể có **tối đa +10 điểm bonus**.

### A. Điểm nhóm — 60 điểm

| Thành phần | Điểm | Cần thể hiện rõ |
|---|---:|---|
| Workflow trước/sau | 15 | Vẽ được workflow hiện tại 3-7 bước và workflow sau tối ưu. Mỗi bước ghi ai làm, mất bao lâu, bàn giao cho ai. Chỉ rõ bước nghẽn nằm ở bước nào và AI hoặc tự động hóa sẽ nằm ở bước nào, ai kiểm tra nếu AI sai. |
| Problem Statement + metric + boundary | 20 | Viết đủ 6 field: ai gặp vấn đề, workflow hiện tại, điểm nghẽn, tác động, success metric và boundary. Metric phải có số hiện tại, số mục tiêu và cách đo (bấm giờ, đếm ticket, đếm câu hỏi lại), chứ không viết chung chung kiểu "nhanh hơn". Boundary phải liệt kê AI được làm gì và tuyệt đối không được làm gì. |
| Độ phù hợp với AI + phương án thay thế | 15 | So được cả 4 mức No AI, Rule, Workflow và Agent trên cùng một bài. Giải thích vì sao chọn mức đó và vì sao loại các mức còn lại. Ghi rõ AI được phép làm tới đâu và chỗ nào bắt buộc có người kiểm tra. |
| Chất lượng quyết định | 10 | Chốt một trong ba: Go, Not Yet hoặc No-Go, kèm lý do dựa trên bằng chứng đã validate, link research hoặc giả định ghi rõ là giả định. Không chấm điểm cao nếu quyết định chỉ vì "muốn làm AI cho ngầu". |

### B. Điểm cá nhân — 40 điểm

| Thành phần | Điểm | Cần thể hiện rõ |
|---|---:|---|
| Scan problem + top 3 Problem Cards | 12 | Scan ít nhất 5 problems từ việc mình từng làm thật, soi bằng nhiều góc nhìn khác nhau. Mỗi problem ghi rõ ai gặp, workflow sơ bộ và dấu hiệu đo được. Top 3 Problem Cards phải đủ chi tiết để đứng pitch 2 phút mà nhóm hiểu ngay. |
| Tham gia pitch + challenge | 12 | Pitch ngắn gọn theo mạch ai đau, workflow nào, nghẽn ở bước nào, muốn đo bằng gì. Khi nghe bạn pitch thì đặt câu hỏi đúng chỗ đau: actor có cụ thể không, workflow có thật không, metric có đo được không, để giúp nhóm loại bài yếu. |
| Reflection cá nhân | 10 | Viết trung thực mình đã nhờ AI làm gì, AI giúp được chỗ nào, AI sai hoặc nói chung chung ở đâu, và mình đã sửa bằng ý của mình ra sao. Nói rõ vai trò và đóng góp thật của mình trong nhóm, điều học được, và nếu làm lại sẽ đổi gì. Không copy reflection do AI viết. |
| Kiểm tra hiểu bài cá nhân | 6 | Tự kể lại được mạch problem tới workflow tới metric tới boundary tới quyết định AI mà không cần nhìn slide. Nếu bị hỏi nhanh vì sao nhóm chọn Rule hay Workflow hay Agent và vì sao Go hay Not Yet thì trả lời được bằng lý do của nhóm. |

### C. Bonus — tối đa +10 điểm

| Phần bonus | Tối đa | Khi nào được cộng |
|---|---:|---|
| Scan rộng hơn yêu cầu | +3 | Có 8-10+ problems cụ thể, đa dạng lăng kính, không phải list dài nhưng chung chung. |
| Tương tác tích cực | +3 | Trả lời câu hỏi thảo luận, gửi bài tập nhanh lên Discord, đặt câu hỏi tốt, hoặc challenge giúp bạn/nhóm làm rõ bài toán hơn. |
| Kiểm chứng / research vượt yêu cầu | +4 | Có phỏng vấn nhanh, survey nhỏ, log thật, nguồn đáng tin cậy, hoặc kiểm chứng giúp nhóm sửa lại problem, metric hoặc quyết định cuối. |

### D. Mức xếp loại

| Mức | Điểm | Ý nghĩa |
|---|---:|---|
| Không pass | < 50 | Bài còn solution-first, chưa nắm được problem, workflow, metric hoặc độ phù hợp với AI. |
| Vừa đủ pass | 50-64 | Có đủ phần cơ bản nhưng nhiều chỗ còn mơ hồ, metric hoặc boundary chưa chắc. |
| Hiểu khá | 65-79 | Làm được đa số yêu cầu, logic tương đối rõ, còn thiếu bằng chứng hoặc so sánh phương án thay thế chưa sâu. |
| Hiểu đầy đủ | 80-89 | Workflow, Problem Statement, độ phù hợp với AI và quyết định cuối nhất quán; metric và boundary rõ. |
| Rất tốt | 90-100 | Bài có bằng chứng tốt, lập luận chặt, biết giới hạn của AI, reflection cá nhân sâu và trung thực. |

## Flow lab 4 tiếng

```text
Phase 0  Worked Example                  15'
Phase 1  Individual Scan                 25'
Phase 2  Top 3 Problem Cards             35'
         Break                            10'
Phase 3  Group Convergence               30'
Phase 4  Validation + Research            30'
Phase 5  Workflow + Problem Statement     45'
         Break                            10'
Phase 6  Rule/Workflow/Agent + Decision   25'
Phase 7  Individual Reflection            15'
```

## Điều quan trọng nhất

Bốn điều này quyết định bạn có pass lab không, đọc kỹ trước khi làm:

- Nhóm **chọn 1 candidate problem để đào sâu, chưa phải Problem Statement**. Candidate là việc thô kiểu "tổng hợp weekly report mất 90 phút". Problem Statement là bản viết chặt sau cả buổi, khi đã có số validate, workflow, metric và boundary. Đừng viết Statement ngay từ đầu giờ.
- Problem Statement chỉ viết sau khi đã làm đủ 4 việc: hỏi người thật để validate, đọc tool có sẵn để research, vẽ workflow trước/sau, và chốt metric đo được. Thiếu một trong bốn thì Statement sẽ chung chung.
- Rule không kém Agent. Nếu template và script đã giải được 70-80% việc với ít rủi ro hơn thì đó là đáp án đúng. Điểm cao thuộc về lập luận đúng, không thuộc về solution ngầu.
- AI chỉ hỗ trợ tư duy: hỏi ngược, phản biện, vẽ lại, tìm nguồn. Người học vẫn phải tự kiểm link, tự chốt số liệu, và tự chịu trách nhiệm với quyết định Go hay No-Go của nhóm.

---

*Day 02 Lab v2 — Batch 02*
