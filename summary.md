# CẨM NANG VẬN HÀNH KỸ THUẬT: CHIẾN LƯỢC TƯ DUY VÀ QUY TRÌNH THỰC THI HỆ THỐNG

## 1. Tuyên ngôn và Hệ giá trị Cốt lõi (Core Mindset)

Trong quản trị kỹ thuật cao cấp, tư duy (Mindset) không phải là một khái niệm trừu tượng để thảo luận — nó chính là "hệ điều hành" (Operating System) điều khiển mọi hành vi của đội ngũ. Một hệ thống sụp đổ thường không bắt đầu từ một dòng code lỗi, mà từ một lỗ hổng trong tư duy tiếp cận. Tư duy kỹ sư đúng đắn là rào cản phòng thủ đầu tiên và kiên cố nhất chống lại sự hỗn loạn, đảm bảo rằng mọi giải pháp không chỉ giải quyết phần ngọn mà còn bảo vệ sự ổn định lâu dài và giá trị kinh doanh.

### 1.1. Nguyên tắc Tư duy Kỹ sư (Engineering Mindset)

Chúng ta vận hành dựa trên 07 nguyên tắc cốt lõi để chuyển hóa từ một người "chỉ viết code" thành một kỹ sư thực thụ:

1. Business luôn đứng trước kỹ thuật: Kỹ thuật không tồn tại độc lập. Mọi thay đổi phải trả lời được câu hỏi: "Nó giải quyết vấn đề gì cho business?".
2. Engineer không chỉ viết code: Trách nhiệm bao gồm hiểu vấn đề, đề xuất giải pháp, đánh giá đánh đổi và vận hành sau phát hành.
3. Đơn giản là ưu tiên cao nhất: Chọn giải pháp đơn giản nhất có thể hoạt động ổn định. Đừng thêm sự phức tạp (complexity) nếu chưa thực sự cần.
4. Mọi thứ đều là trade-off: Không có giải pháp "tốt tuyệt đối", chỉ có sự lựa chọn phù hợp nhất với bối cảnh (Context).
5. Hiểu vấn đề trước khi nghĩ đến solution: Tuyệt đối không bắt đầu từ code. Phải xác định rõ Problem, Context và Constraint.
6. Production là sự thật: Mọi giả định đều sai cho đến khi chạy ổn định trên Production. Nếu có sự khác biệt giữa thiết kế và thực tế, Production luôn đúng.
7. Trách nhiệm không kết thúc khi merge: Công việc chỉ hoàn thành khi tính năng chạy ổn định, không gây sự cố và được giám sát (monitor) đầy đủ.

Tư duy Đúng (Engineer) Anti-pattern (Chỉ viết code)
Business trước Kỹ thuật: Ưu tiên giải quyết bài toán kinh doanh. Thích kỹ thuật: Chọn công nghệ vì sở thích cá nhân hoặc xu hướng.
Đơn giản hóa: Chọn cách đơn giản để đạt hiệu quả ổn định. Over-engineering: Phức tạp hóa bài toán đơn giản một cách vô ích.
Production là chân lý: Kiểm chứng mọi giả định bằng vận hành thực tế. Chủ quan: Chỉ quan tâm code chạy được trên máy cá nhân.
Trách nhiệm toàn diện: Theo sát từ lúc intake đến khi vận hành ổn định. Coi Merge là kết thúc: Nghĩ rằng xong việc ngay khi đẩy code lên.

**Quy tắc bắt buộc:**

* Không code khi chưa hiểu vấn đề (problem).
* Không tối ưu khi chưa có dữ liệu thực tế.
* Không thêm complexity nếu chưa cần thiết.

### 1.2. Khung Ra quyết định Kỹ thuật (Decision-Making)

Mọi quyết định kỹ thuật đều là sự đánh đổi.
Việc xác định Constraint (Ràng buộc) như thời gian, hiệu năng, nhân lực và hạ tầng không chỉ là liệt kê thông số, mà là xác định "Safety Envelope" (Vùng an toàn) của dự án.
"So what?" cho Constraint & Trade-off: Nếu không xác định rõ ràng, đội ngũ sẽ sa vào technical debt không kiểm soát hoặc cháy túi nguồn lực vì theo đuổi những giải pháp "hoàn hảo" nhưng không phù hợp.

**Quy trình 07 bước thực thi:**

1. Xác định vấn đề: Vấn đề thực sự là gì? Ai bị ảnh hưởng?
2. Xác định mục tiêu: Làm rõ mục tiêu business và kỹ thuật.
3. Xác định Constraint: Thời gian, Performance, Team size, Hạ tầng, Legacy system.
4. Liệt kê phương án: Tìm kiếm Option A, B...
5. So sánh Trade-off: Đánh giá dựa trên Performance, Complexity, Maintainability, Risk, và Cost.
6. Ra quyết định: Chọn phương án phù hợp nhất với Context, không chọn theo cảm tính.
7. Ghi lại quyết định: Lưu vết qua tài liệu (Redmine, nhóm chung) để đảm bảo khả năng truy vết.

**Quy tắc bắt buộc:**

* Không được quyết định một mình với những thay đổi lớn.
* Mọi quyết định quan trọng phải có lý do rõ ràng và có thể review lại.

> Khi tư duy đã thông suốt, bước tiếp theo là chuyển hóa các yêu cầu mơ hồ thành các tham số kỹ thuật chính xác.

## 2. Kỹ thuật Yêu cầu và Quản trị Phạm vi (Requirement Engineering)

Sai sót ở giai đoạn phân tích yêu cầu gây tốn kém gấp nhiều lần khi đã lên Production. Một kỹ sư giỏi là người biết hoài nghi các yêu cầu mơ hồ để tìm ra bản chất vấn đề.

### 2.1. Xử lý và Làm rõ Yêu cầu (Analysis & Clarification)

**Quy trình 06 bước để đảm bảo không "xây nhầm nhà":**

1. Đọc requirement thô: Tiếp nhận các mô tả sơ khởi (Ví dụ: "Làm booking phòng").
2. Đặt câu hỏi làm rõ: Chuyển requirement thành câu hỏi: "Ai sử dụng?", "Mục đích là gì?", "Input/Output là gì?", "Có quyền hạn (Permission) không?".
3. Xác định Scope: Phân loại theo Must have, Should have, Could have, Won't have.
4. Xác định Edge cases: Giả định các tình huống: Data rỗng, Data lớn, Duplicate, Conflict, Race condition.
5. Chốt tiêu chí tối thiểu (Acceptance Criteria): Định nghĩa rõ trạng thái DONE/FAIL.
6. Chuyển sang Decision-Making: Chỉ bắt đầu thiết kế khi yêu cầu đã tuyệt đối rõ ràng.

### 2.2. Thiết lập Tiêu chuẩn Hoàn thành (Acceptance Criteria)

Tiêu chuẩn hoàn thành phải cụ thể và có thể kiểm chứng. Ví dụ: Với yêu cầu "Export CSV", tiêu chí DONE bao gồm: Đúng format, đúng filter, không timeout với dữ liệu lớn, và có check permission.

**Quy tắc bắt buộc:**

* Không code khi requirement chưa rõ hoặc chưa có Acceptance Criteria.
* Không nhận task mà không đặt câu hỏi ngược lại cho PM/Business.

**Anti-pattern cần tránh:**

* Code theo mô tả mơ hồ.
* Bỏ qua Edge cases vì nghĩ "chắc không xảy ra".
* Nghĩ rằng requirement ban đầu luôn đúng tuyệt đối.

Sau khi yêu cầu đã rõ ràng và scope đã chốt, đội ngũ sẽ bước vào chu trình phát triển (Build) với kỷ luật thép.

## 3. Quy trình Phát triển và Kiểm soát Chất lượng (Development Flow)

Sự ổn định của hệ thống tỷ lệ thuận với tính kỷ luật của SDLC và Git Workflow. Đây không phải là thủ tục hành chính, mà là quy chuẩn để bảo vệ mã nguồn.

### 3.1. Vòng đời Phát triển Phần mềm (SDLC)

Mọi feature, không ngoại lệ, phải đi qua 10 bước chuẩn:

| Bước | Input | Output |
|------|------|--------|
| 1. Intake | Yêu cầu từ PM/Business Requirement | Yêu cầu được làm rõ cơ bản |
| 2. Analysis | Requirement thô | Scope, Edge cases, Acceptance criteria |
| 3. Technical Decision | Requirement đã rõ | Approach được chọn & Trade-off |
| 4. Design Solution | Requirement + Tech Decision | Cách implement, Data flow, Impact system |
| 5. Implementation | Design rõ ràng | Code hoàn chỉnh, Pass review |
| 6. Code Review | PR/MR | Trạng thái Approved / Request changes |
| 7. Testing | Code trên staging/merged | Feature được verify hoạt động đúng |
| 8. Release | Build sẵn sàng | Feature lên Production |
| 9. Monitoring | Feature trên Production | Hệ thống ổn định, không bug phát sinh |
| 10. Feedback Loop | Dữ liệu thực tế | Cải tiến system và chất lượng code |

### 3.2. Quản trị Luồng công việc với Git (Git Workflow)

Git là nơi quản lý trạng thái hệ thống. Nhánh chính (Main/Master/Release) phải luôn ổn định và tuyệt đối không commit trực tiếp.

1. Branching: 1 feature = 1 branch. Tên theo mẫu: feature/login, bugfix/validate-email.
2. Commit: Phải có ý nghĩa theo logic thay đổi. Ví dụ: add validation email, fix race condition in booking.
3. Pull Request (PR): Đơn vị review duy nhất. Phải mô tả mục tiêu, link requirement và highlight rủi ro.

**Quy tắc bắt buộc:**

* Luôn pull nhánh chính mới nhất trước khi làm.
* Không reuse branch cho nhiều feature. Không giữ branch lâu ngày không update.

### 3.3. Quy chuẩn Code Review - Bảo vệ Hệ thống

Code Review không phải là soi lỗi cá nhân; người review là người đang bảo vệ Production.

* 6 Bước Review: (1) Hiểu mục đích PR, (2) Kiểm tra Logic chính, (3) Kiểm tra Production Risk (Race condition, Deadlock, Performance), (4) Maintainability, (5) Consistency (Standard & Architecture), (6) Approve/Request changes.
* Trạng thái: Chỉ có APPROVE hoặc REQUEST CHANGES. Không có trạng thái "comment cho vui".

**Quy tắc bắt buộc:**

* Không approve khi chưa hiểu code. Không review hời hợt.
* PR lớn phải chia nhỏ trước khi review.

Một quy trình xây dựng chặt chẽ là tiền đề để tự tin đưa hệ thống lên vận hành thực tế tại Production.

## 4. Vận hành Production và Quản trị Sự cố (Production Rules)

**Production** là môi trường quan trọng nhất. Release không phải là kết thúc, mà là sự bắt đầu của trách nhiệm thực sự.

### 4.1. Quy trình Deploy và Kiểm soát Sau phát hành

1. Pre-check: Review xong, test pass.
2. Deploy: Theo process chuẩn, tuyệt đối không bypass CI/CD.
3. Verify: Kiểm tra trực tiếp tính năng, UI và logic trên Production.
4. Monitor: Theo dõi log hệ thống, response time và báo lỗi trên chatroom.
5. Feedback loop: Ghi nhận vấn đề và cập nhật thông báo lên group.

### 4.2. Quản trị và Xử lý Sự cố (Incident Management)

**Khi sự cố xảy ra: Tốc độ và An toàn là ưu tiên số 1.**

* Xử lý: Xác định mức độ -> Tìm phương án (Ưu tiên Rollback hoặc Disable feature) -> Giao tiếp liên tục (Không im lặng) -> Phân tích nguyên nhân gốc.
* Postmortem: Không dừng lại ở sự nghi ngờ hay "chỗ lỗi". Phải tìm ra lỗi quy trình và đưa ra giải pháp cải tiến để không lặp lại.

**Quy tắc bắt buộc:**

* Không ignore error trên Production.
* Không fix Production mà không có phương án Rollback.
* Luôn có Postmortem sau mỗi sự cố.

> Sự thành công của vận hành nằm ở văn hóa trách nhiệm tập thể và kỷ luật thực thi.

## 5. Nguyên tắc Cộng tác và Văn hóa Đội ngũ (Team Principles)

Con người là yếu tố vận hành quy trình. Một đội ngũ mạnh là đội ngũ làm việc theo một chuẩn chung duy nhất, không có chỗ cho những "ngôi sao" làm việc ngoài quy chuẩn.

### 5.1. Hệ giá trị Cộng tác

**Chúng ta tuân thủ 08 nguyên tắc vàng:**

1. Team quan trọng hơn cá nhân: Ưu tiên lợi ích hệ thống. Không dùng sở thích cá nhân để quyết định kỹ thuật.
2. Không có "cách làm riêng": Chỉ có một cách làm chuẩn. Không có chỗ cho câu nói "Em thích cách khác".
3. Minh bạch: Không làm việc "ngầm". Mọi thay đổi phải được ghi lại và báo cáo công khai.
4. Không giữ kiến thức cá nhân: Phải tài liệu hóa kiến thức để bất kỳ ai cũng có thể tiếp cận.
5. Tôn trọng quy trình: Quy trình để giảm lỗi và tăng tính nhất quán (Consistency).
6. Communication là trách nhiệm: Không im lặng khi gặp khó khăn; không để người khác phải đoán trạng thái công việc.
7. Chất lượng trên tốc độ: Ưu tiên sự ổn định lâu dài hơn hoàn thành nhanh trong ngắn hạn.
8. Feedback là bắt buộc: Feedback phải trực tiếp, dựa trên tiêu chuẩn, không giả thuyết lang mang và không cảm tính.

### 5.2. Kỷ luật và Phản hồi (Feedback)

Phản hồi là để cải thiện, không phải để tấn công. Feedback phải dựa trên yêu cầu, quy định và tiêu chuẩn đã thống nhất.

**Anti-pattern trong văn hóa:**

* Làm việc theo style cá nhân, đánh giá code theo sở thích.
* Giữ logic trong đầu, tạo sự phụ thuộc vào cá nhân.
* Bỏ qua quy trình vì "cho nhanh".

**Quy tắc bắt buộc:**

* Không có "em thích cách khác".
* Không im lặng khi có vấn đề hoặc nghi vấn.
* Không bypass review hoặc SDLC dưới bất kỳ hình thức nào.

> Cẩm nang này là chuẩn vận hành chung, sẽ liên tục được cập nhật để phản ánh đúng thực tế vận hành và kinh nghiệm rút ra từ Production. Kỷ luật là sức mạnh của chúng ta.
