# Đánh giá code - Code Review

## Mục tiêu

Định nghĩa cách team review code nhằm đảm bảo:

- Chất lượng hệ thống
- Tính nhất quán
- Giảm bug production
- Chia sẻ kiến thức trong team

Code review không phải để tìm lỗi cá nhân, mà là để bảo vệ hệ thống, nâng cao chất lượng team.

---

## Nguyên tắc

### 1. Review là trách nhiệm của hệ thống, không phải cá nhân

Người review không “soi lỗi”, mà đang bảo vệ production.

---

### 2. Review tập trung vào logic, không phải style

Không tranh luận về:

- Tập trung vào đáp ứng yêu cầu của spec, business
- Tập trung vào chất lượng, hiệu năng, tối ưu cũng như tốc độ
- Tuân thủ các coding rule, tiêu chuẩn chung
- Không review theo style cá nhân, sở thích

---

### 3. Review phải hiểu context

Không review code khi chưa hiểu:

- Requirement
- Mục đích của tính năng, PR/ MR đó

---

### 4. Code đúng chưa đủ

Code phải:

- Đúng logic
- Dễ hiểu
- Dễ maintain
- An toàn với production

---

### 5. Review là nơi chia sẻ kiến thức

Review code không phải để reject PR/MR, mà để:

- Giải thích trade-off
- Chia sẻ kinh nghiệm, kiến thức
- Nâng chất lượng team

---

## Quy trình Code Review

### Bước 1: Hiểu mục đích PR/MR

- Feature này giải quyết gì?
- Có liên quan system nào?

---

### Bước 2: Kiểm tra logic chính

- Có đúng requirement không?
- Có missing case không?
- Có side effect không?

---

### Bước 3: Kiểm tra production risk

- Có race condition không?
- Có deadlock không?
- Có ảnh hưởng performance không?
- Có breaking change không?

---

### Bước 4: Kiểm tra maintainability

- Code có dễ đọc không?
- Có quá phức tạp không?
- Có duplication không?

---

### Bước 5: Kiểm tra consistency

- Có đúng team standard không?
- Có đúng architecture không?

---

### Bước 6: Approve hoặc Request changes

Chỉ có 2 trạng thái:

- APPROVE
- REQUEST CHANGES

Không có trạng thái “comment cho vui”.

---

## Quy tắc của team (bắt buộc)

- Không approve khi chưa hiểu code
- Không merge nếu còn logic chưa rõ
- Không review hời hợt
- Không tranh luận cá nhân trong PR
- Không bỏ qua risk production
- PR lớn phải chia nhỏ trước khi review

---

## Anti-pattern

- Approve nhanh để “cho xong việc”
- Review chỉ nhìn syntax
- Không đọc business logic
- Comment cảm tính (“em thấy chưa ổn”)
- Không check edge cases
- Không test lại luồng chính

---

## Checklist review bắt buộc

Trước khi approve:

- [ ] Hiểu feature đang làm gì
- [ ] Check logic chính
- [ ] Check edge cases
- [ ] Check performance risk
- [ ] Check production impact
- [ ] Check consistency với system
- [ ] Code có dễ maintain không

---

## Liên quan

- [[Git-Workflow]]
- [[Software-Development-Lifecycle]]
