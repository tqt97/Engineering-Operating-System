# Ra quyết định - Decision Making

## Mục tiêu

Định nghĩa cách team đưa ra quyết định kỹ thuật một cách nhất quán, giảm cảm tính và giảm phụ thuộc vào cá nhân.

---

## Nguyên tắc

### 1. Không có quyết định “đúng tuyệt đối”

Mọi quyết định đều là trade-off.

Không có solution hoàn hảo, chỉ có solution phù hợp với context hiện tại.

---

### 2. Quyết định phải dựa trên problem, không dựa trên solution

Không bắt đầu từ:

- Framework
- Pattern
- Tool

Mà bắt đầu từ:

- Vấn đề cần giải quyết là gì?

---

### 3. Tách rõ problem và constraint

Trước khi chọn giải pháp phải xác định:

- Problem (vấn đề cần giải quyết)
- Constraint (giới hạn hệ thống, thời gian, team, business)

---

### 4. Quyết định phải có lý do rõ ràng

Mỗi quyết định phải trả lời được:

- Tại sao chọn cách này?
- Vì sao không chọn cách khác?

Nếu không trả lời được → chưa được phép quyết định.

---

### 5. Quyết định phải có thể review lại được

Mọi quyết định quan trọng phải được ghi lại (Báo lên nhóm, note vào redmine, thông báo với mọi người, ...)

Không để quyết định chỉ nằm trong đầu cá nhân.

---

## Quy trình ra quyết định

### Bước 1: Xác định vấn đề

- Vấn đề thực sự là gì?
- Ai bị ảnh hưởng?

---

### Bước 2: Xác định mục tiêu

- Mục tiêu business là gì?
- Mục tiêu kỹ thuật là gì?

---

### Bước 3: Xác định constraint

- Thời gian
- Performance
- Team size
- Hạ tầng
- Legacy system

---

### Bước 4: Liệt kê phương án

Cố gắng tìm ra các phương án và liệt kê chúng

- Option A
- Option B
- ...

---

### Bước 5: So sánh trade-off

Mỗi option phải so sánh:

- Performance
- Complexity
- Maintainability
- Risk
- Cost

---

### Bước 6: Ra quyết định

Chọn phương án phù hợp nhất với context hiện tại.

Không chọn theo cảm giác.

---

### Bước 7: Ghi lại quyết định

Nếu là decision quan trọng:

- Ghi vào tài liệu, báo lên nhóm, note vào redmine,...
- Nêu rõ lý do chọn

---

## Quy tắc của team (bắt buộc)

- Không được quyết định một mình với thay đổi lớn
- Không được chọn solution chỉ vì quen tay
- Không được bỏ qua trade-off 
- Không được merge code mà không có lý do design rõ ràng
- Mọi quyết định quan trọng phải có thể review lại

---

## Anti-pattern

- Chọn solution vì “em thấy hay”
- Copy kiến trúc từ project khác mà không phân tích context
- Không so sánh phương án trước khi quyết định
- Quyết định không có lý do rõ ràng
- Không ghi lại quyết định quan trọng
- Thay đổi kiến trúc liên tục không kiểm soát

---

## Liên quan

- [[Team-Principles]]
- [[Engineering-Mindset]]
