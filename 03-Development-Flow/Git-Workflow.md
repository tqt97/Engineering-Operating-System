# Git Workflow

## Mục tiêu

Định nghĩa cách team sử dụng Git để:

- Làm việc đồng bộ
- Tránh conflict logic
- Dễ review
- Dễ rollback
- Bảo vệ production

---

## Nguyên tắc

### 1. Git không chỉ là tool, mà là workflow

Git không phải nơi “push code”.

Git là nơi quản lý trạng thái thay đổi của hệ thống.

---

### 2. Main branch luôn ổn định

Branch chính (main/master/release):

- Luôn deploy được
- Không chứa code đang làm dở
- Không commit trực tiếp

---

### 3. Mỗi branch = 1 mục tiêu rõ ràng

Không làm nhiều feature trong cùng 1 branch.

---

### 4. Commit phải có ý nghĩa

Không commit kiểu:

- Fix
- Update
- Done
- Temp

---

### 5. PR là đơn vị review

Không review trực tiếp trên branch cá nhân.

---

## Quy trình Git chuẩn

### Bước 1: Tạo branch từ nhánh chính(release/master/main)

- Luôn sync với main mới nhất

---

### Bước 2: Làm feature trong branch riêng

- 1 feature = 1 branch

Ví dụ:

- feature/login
- feature/booking-room
- bugfix/validate-email

---

### Bước 3: Commit theo logic

Mỗi commit phải thể hiện một bước thay đổi rõ ràng.

Ví dụ:

- add validation email
- implement search shop logic
- fix race condition in booking

---

### Bước 4: Push branch

Không push code chưa hoàn chỉnh lên main.

---

### Bước 5: Tạo Pull Request

PR phải:

- Mô tả rõ mục tiêu
- Link requirement
- Highlight risk nếu có
- Chạy git diff và comment trong PR đối với những file lớn không hiển thị được

---

### Bước 6: Review

PR chỉ được merge khi:

- Pass code review
- Không có issue logic, UI
- Không có risk production

---

### Bước 7: Merge

Merge chỉ thực hiện khi:

- Approved
- Test pass
- Không conflict logic

---

### Bước 8: Delete branch

Sau khi merge:

- xóa branch
- giữ repo sạch

---

## Quy tắc của team (bắt buộc)

- Không commit code bừa bãi
- Không push trực tiếp lên main
- Không merge khi chưa review
- Không reuse branch cho nhiều feature
- Không giữ branch lâu ngày không update
- Luôn pull main trước khi bắt đầu work

---

## Anti-pattern

- Commit chung chung, không rõ ràng
- Push code chưa hoàn thiện lên nhánh chính
- PR/MR quá lớn (Gây khó khăn trong việc review)
- Không sync main trước khi làm feature
- Giữ branch cũ gây conflict lớn
- Merge khi chưa hiểu hết impact
- Luôn pull mới để đảm bảo code trên các nhánh là mới nhất

---

## Best practice

- PR/MR nhỏ, dễ review
- Commit rõ ràng theo logic
- Sync branch chính thường xuyên
- Tách feature nhỏ thay vì big PR/MR
- Luôn test trước khi merge

---

## Liên quan

- [[Code-Review]]
- [[Software-Development-Lifecycle]]
