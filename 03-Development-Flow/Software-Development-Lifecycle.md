# Software Development Lifecycle

## Mục tiêu

Định nghĩa vòng đời chuẩn của một feature trong team, từ lúc nhận requirement đến khi vận hành production.

Mục tiêu chính:

- Không bỏ sót bước quan trọng
- Giảm làm sai ngay từ đầu
- Tạo flow làm việc nhất quán trong team

---

## Nguyên tắc

### 1. Mọi feature đều đi qua cùng một vòng đời

Không có feature “đặc biệt” được bỏ qua quy trình.

---

### 2. Không được code trước khi qua design/analysis

Implementation luôn là bước sau cùng.

---

### 3. Mỗi bước trong SDLC đều có output rõ ràng

Không có bước nào chỉ “làm cho xong”.

---

### 4. Fail sớm tốt hơn fix muộn

Sai ở requirement rẻ hơn sai ở production.

---

## Vòng đời chuẩn

### Bước 1: Requirement Intake

Input:

- Yêu cầu từ PM / Business / Customer

Output:

- Requirement đã được làm rõ cơ bản

---

### Bước 2: Requirement Analysis

Input:

- Requirement thô

Output:

- Scope rõ ràng
- Edge cases
- Acceptance criteria

---

### Bước 3: Technical Decision

Input:

- Requirement đã rõ

Output:

- Approach được chọn
- Trade-off được ghi nhận (nếu cần)

---

### Bước 4: Design

Input:

- Solution đã chọn

Output:

- Cách implement rõ ràng
- Data flow
- Impact system

---

### Bước 5: Implementation

Input:

- Design rõ ràng

Output:

- Code hoàn chỉnh
- Pass review

---

### Bước 6: Code Review

Input:

- PR/MR

Output:

- Approved hoặc request changes

---

### Bước 7: Testing

Input:

- Code đã merge / staging

Output:

- Feature verified hoạt động đúng

---

### Bước 8: Release

Input:

- Build sẵn sàng

Output:

- Feature lên production

---

### Bước 9: Monitoring

Input:

- Feature trên production

Output:

- Không có vấn đề, bug / hoặc vấn đề/ bug đã được xử lý

---

### Bước 10: Feedback Loop

Input:

- Data production

Output:

- Cải tiến system / chất lượng code

---

## Quy tắc của team (bắt buộc)

- Không code khi chưa qua requirement analysis
- Không merge khi chưa review
- Không release khi chưa test
- Không coi release là kết thúc công việc
- Luôn có monitoring sau release

---

## Anti-pattern

- Code trực tiếp từ requirement mơ hồ
- Bỏ qua design phase
- Merge trước review để “kịp deadline”
- Release mà không test kỹ
- Không theo dõi production sau khi deploy
- Không update quy trình sau incident

---

## Liên quan

- [[Code-Review]]
- [[Git-Workflow]]
