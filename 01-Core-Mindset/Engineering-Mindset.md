# Tư duy kỹ thuật - Engineering Mindset

## Mục tiêu

Định nghĩa cách một kỹ sư trong team suy nghĩ khi giải quyết bất kỳ vấn đề kỹ thuật nào.

Đây là nền tảng cho mọi quyết định kỹ thuật.

---

## Nguyên tắc

### 1. Business luôn đứng trước kỹ thuật

Không có quyết định kỹ thuật nào tồn tại độc lập với business.

Mỗi thay đổi phải trả lời:

- Nó giải quyết vấn đề gì cho business?
- Nếu không làm thì ảnh hưởng gì?

---

### 2. Engineer không chỉ viết code

Engineer chịu trách nhiệm:

- Hiểu vấn đề
- Đề xuất giải pháp
- Đánh giá sự đánh đổi *(trade-off)*
- Vận hành sau khi release

Code chỉ là một phần nhỏ trong quá trình.

---

### 3. Đơn giản là ưu tiên cao nhất

Nếu có nhiều cách giải quyết:

→ chọn cách đơn giản nhất có thể hoạt động ổn định.

Không thêm complexity nếu chưa thật sự cần.

---

### 4. Mọi thứ đều là trade-off

Không có giải pháp “tốt tuyệt đối”.

Chỉ có:

- Nhanh hơn nhưng khó maintain hơn
- An toàn hơn nhưng chậm hơn
- Linh hoạt hơn nhưng phức tạp hơn

Engineer phải biết chọn.

---

### 5. Hiểu vấn đề trước khi nghĩ đến solution

Không được bắt đầu từ code.

Phải bắt đầu từ:

- Problem là gì?
- Context là gì?
- Constraint là gì?

---

### 6. Production là sự thật

Mọi giả định đều sai cho đến khi chạy production.

Nếu khác biệt giữa thiết kế và production xảy ra:

→ production luôn đúng.

---

### 7. Trách nhiệm không kết thúc khi merge

Merge không phải là hoàn thành.

Engineer chịu trách nhiệm đến khi:

- Feature chạy ổn định
- Không gây incident
- Được monitor đầy đủ

---

## Cách áp dụng

Trước khi bắt đầu một task, luôn trả lời:

- Tôi đang giải quyết vấn đề gì?
- Có cách nào đơn giản hơn không?
- Rủi ro là gì?
- Nếu fail thì hậu quả là gì?

Nếu không trả lời được → chưa được code.

---

## Quy tắc của team (bắt buộc)

- Không code khi chưa hiểu problem
- Không chọn solution vì “quen tay”
- Không thêm complexity nếu chưa cần
- Không tối ưu khi chưa có dữ liệu
- Không coi merge là kết thúc công việc

---

## Anti-pattern

- Code trước khi hiểu requirement
- Chọn design vì “thích kỹ thuật”
- Over-engineering cho bài toán đơn giản
- Chỉ quan tâm feature, không quan tâm production
- Đổ lỗi cho hệ thống thay vì hiểu vấn đề

---

## Liên quan

- [[Team-Principles]]
- [[Decision-Making]]
