# Production Rules

## Mục tiêu

Định nghĩa cách team vận hành hệ thống sau khi deploy lên production, nhằm:

- Giảm sự cố, phát sinh, bug không đáng có
- Tăng khả năng kiểm soát hệ thống
- Phát hiện lỗi sớm
- Phản ứng nhanh khi có sự cố

---

## Nguyên tắc

### 1. Production là môi trường quan trọng nhất

Mọi quyết định kỹ thuật đều phải xét impact lên production.

---

### 2. Không có feature nào “xong” nếu chưa chạy production ổn định

Merge không phải là kết thúc.

Release mới là bắt đầu thực sự.

---

### 3. Mọi hệ thống đều có thể fail

Không tồn tại hệ thống “không lỗi”.

Chỉ tồn tại hệ thống:

- Phát hiện nhanh
- Xử lý nhanh
- Giảm thiểu tác động

---

### 4. Logging và monitoring là bắt buộc

Không có log = không thể debug production.

Không có monitoring = không biết hệ thống đang chết.

---

### 5. Fix production phải ưu tiên tốc độ và an toàn

Trong sự cố:

- không tối ưu code trong lúc emergency
- rollback nếu cần

---

## Quy trình khi deploy production

### Bước 1: Pre-check

- Code đã được review
- Test đã pass
- Không còn vấn đề

---

### Bước 2: Deploy

- Deploy theo process chuẩn
- Không bypass CI/CD

---

### Bước 3: Verify

Sau deploy phải kiểm tra:

- Code, tính năng hoạt động, chạy đúng yêu cầu
- UI đúng design
- Test lại theo test case và các tiêu chí yêu cầu

---

### Bước 4: Monitor

Theo dõi:

- Báo lỗi trên chatwork room log
- Response time
- Log system

---

### Bước 5: Feedback loop

Nếu có issue:

- Ghi nhận vấn đề
- Phân tích nguyên nhân
- Cập nhật, thông báo lên group

---

## Xử lý sự cố

### Khi có sự cố

#### Bước 1: Xác định mức độ

- Critical
- High
- Medium
- Low

---

#### Bước 2: Tìm phương án xử lý

Ưu tiên:

- Rollback
- Disable feature
- Fix nhanh

---

#### Bước 3: Giao tiếp trong team

- Thông báo team
- Không im lặng
- Cập nhật trạng thái liên tục

---

#### Bước 4: Phân tích nguyên nhân

Sau khi hệ thống ổn định:

- Tìm nguyên nhân gốc
- Không dừng ở vấn đề. chỗ lỗi, nghi hoặc

---

#### Bước 5: Postmortem

- Ghi lại sự cố
- Xác định lỗi quy trình
- Đưa ra giải pháp cải tiến

---

## Quy tắc của team (bắt buộc)

- Không deploy khi chưa qua review
- Không ignore error trên production
- Không fix production mà không rollback option
- Không im lặng khi có bug, vấn đề hoặc nghi vấn
- Luôn có monitoring sau release
- Luôn có postmortem sau khi có vấn đề

---

## Anti-pattern

- Deploy không qua CI/CD
- Fix production trực tiếp mà không ghi nhận
- Bỏ qua log system
- Không rollback khi hệ thống lỗi
- Không làm postmortem
- Chờ “tự hết lỗi”

---

## Best practice

- Feature flag cho thay đổi lớn
- Rollback plan luôn sẵn sàng
- Monitoring real-time
- Alert rõ ràng theo mức độ
- Sự cố được ghi lại đầy đủ
- Tự động hóa deploy

---
