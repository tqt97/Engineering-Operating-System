# Kỹ thuật yêu cầu - Requirement Engineering

## Mục tiêu

Định nghĩa cách team tiếp nhận, phân tích và làm rõ requirement trước khi bắt đầu implementation.

Mục tiêu chính: giảm hiểu sai requirement và giảm bug do thiếu phân tích.

---

## Nguyên tắc

### 1. Requirement không bao giờ rõ ràng ngay từ đầu

Mọi requirement ban đầu đều mơ hồ ở một mức độ nào đó.

Nhiệm vụ của engineer là làm rõ nó trước khi code.

---

### 2. Không chuyển requirement thành code trực tiếp

Không được bắt đầu implementation khi chưa hiểu:

- Ai dùng
- Dùng khi nào
- Kết quả mong muốn là gì
- Edge cases là gì

---

### 3. Requirement phải được chuyển thành câu hỏi

Nếu không thể đặt câu hỏi về requirement → chưa hiểu requirement.

---

### 4. Mọi feature đều có edge case

Không tồn tại feature “đơn giản tuyệt đối”.

Luôn phải giả định:

- Data sai
- User thao tác sai
- System fail
- Concurrency xảy ra

---

### 5. Tối thiểu đạt các tiêu chí bắt buộc

Mỗi requirement phải có tiêu chí rõ ràng:

- Khi nào được xem là **DONE**
- Khi nào được xem là **FAIL**

---

## Quy trình xử lý requirement

### Bước 1: Đọc requirement thô

Ví dụ:

- “Thêm chức năng export”
- “Làm booking phòng”
- “Hiển thị danh sách user”

---

### Bước 2: Đặt câu hỏi làm rõ

Luôn hỏi:

- Ai sử dụng?
- Mục đích là gì?
- Input là gì?
- Output là gì?
- Có giới hạn gì không?
- Có quyền hạn không?

---

### Bước 3: Xác định scope

Chia requirement thành:

- Must have
- Should have
- Could have
- Won’t have (ở phase này)

---

### Bước 4: Xác định edge cases

Luôn kiểm tra:

- Data rỗng
- Data lớn
- Duplicate
- Conflict
- Permission
- Race condition

---

### Bước 5: Chốt tiêu chí tối thiểu cần đạt

Ví dụ:

Feature: Export CSV

- File export đúng format
- Dữ liệu đúng filter
- Không vượt timeout
- Có xử lý data lớn
- Có permission check

---

### Bước 6: Chuyển sang Decision-Making

Sau khi requirement rõ ràng:

→ mới bắt đầu chọn solution

---

## Quy tắc của team (bắt buộc)

- Không code khi requirement chưa rõ
- Không nhận task mà không đặt câu hỏi
- Không bỏ qua edge cases
- Không bắt đầu thiết kế khi chưa hiểu scope
- Luôn có acceptance criteria trước khi implementation

---

## Anti-pattern

- Code theo mô tả mơ hồ
- Không hỏi lại PM khi thấy thiếu thông tin
- Bỏ qua edge case vì “chắc không xảy ra”
- Không xác định scope rõ ràng
- Không có tiêu chí DONE rõ ràng
- Nghĩ rằng requirement luôn đúng ngay từ đầu

---
