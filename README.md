# Hệ thống quản lý thư viện — Mô hình hóa UML

Repository bài tập nhóm dùng để thiết kế các **sơ đồ UML** cho **Hệ thống quản lý thư viện**.

## 1. Nhóm thực hiện

Lớp: **DH23TIN01**

| STT | Thành viên        | MSSV   | Vai trò       |
| --- | ------------------- | ------ | -------------- |
| 1   | Ngô Gia Bảo       | 239922 | Nhóm trưởng |
| 2   | Huỳnh Hoàng Khang | 232583 | Thành viên   |
| 3   | Hồ Văn Tài       | 233015 | Thành viên   |
| 4   | Dương Trí Thành | 233012 | Thành viên   |

Giảng viên hướng dẫn: **ThS. Lê Thanh Trúc**

## 2. Lộ trình

- [X] Sơ đồ use case
- [ ] Sơ đồ lớp (Class)
- [ ] Sơ đồ tuần tự (Sequence)
- [ ] Sơ đồ hoạt động (Activity)
- [ ] Sơ đồ trạng thái (State machine)

## 3. Sơ đồ Use Case

### 3.1. Cấu trúc thư mục

```text
.
├── README.md
└── use-case/
    ├── UC_Library_Management.mdj   # Project StarUML chứa các sơ đồ use case
    └── doc/                        # Đặc tả use case và báo cáo (.docx)
```

### 3.2. Các tác nhân (Actor)

| Actor               | Mô tả                                                                                             |
| ------------------- | --------------------------------------------------------------------------------------------------- |
| Người dùng chung | Actor cơ sở cho mọi người dùng: đăng nhập, đăng xuất, thông tin cá nhân, thông báo |
| Độc giả          | Tra cứu sách, gửi yêu cầu mượn, theo dõi trạng thái yêu cầu và lịch sử mượn trả   |
| Thủ thư           | Quản lý sách, độc giả, thẻ thư viện, yêu cầu mượn và việc trả sách                 |
| Quản trị viên    | Quản lý tài khoản, phân quyền và thống kê                                                  |

### 3.3. Các use case chính

Sơ đồ tổng quát (`Use case tổng quát hệ thống quản lý thư viện`) gồm các use case chính sau:

| Actor               | Use case chính                                                                                                                                                                 |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Người dùng chung | Đăng nhập, Đăng xuất, Quản lý thông tin cá nhân, Xem thông báo                                                                                                     |
| Độc giả          | Tra cứu sách, Xem thông tin chi tiết sách, Đăng ký mượn sách trực tuyến, Gia hạn mượn sách, Xem trạng thái yêu cầu mượn, Theo dõi lịch sử mượn trả |
| Thủ thư           | Quản lý sách, Quản lý danh mục sách, Quản lý độc giả, Quản lý yêu cầu mượn, Xử lý trả sách, Xem thống kê                                                |
| Quản trị viên    | Quản lý tài khoản, Đặt hạn mức mượn, Xem thống kê                                                                                                                   |

### 3.4. Các use case phân rã

Một số use case chính được phân rã thành các use case con, mỗi use case có một sơ đồ riêng:

| Use case chính            | Phân rã thành                                                                                                                                  |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| Tra cứu sách             | Tra cứu theo tên, tác giả, năm xuất bản, thể loại; xem chi tiết sách                                                                   |
| Quản lý sách            | Quản lý đầu sách, quản lý bản sách                                                                                                       |
| Quản lý danh mục sách  | Quản lý tác giả, thể loại, nhà xuất bản                                                                                                  |
| Quản lý độc giả       | Quản lý hồ sơ độc giả, thẻ thư viện (tra cứu, cấp, khóa, gia hạn), tài khoản độc giả (đặt lại mật khẩu, khóa, mở khóa) |
| Quản lý yêu cầu mượn | Xem danh sách yêu cầu, kiểm tra tính hợp lệ, duyệt yêu cầu, lập phiếu mượn, in phiếu mượn                                        |
| Xử lý trả sách         | Kiểm tra tình trạng sách, tính tiền phạt quá hạn, lập biên bản sách mất hoặc hỏng, xác nhận hoàn tất trả sách               |
| Quản lý tài khoản      | Xem danh sách tài khoản, thêm tài khoản, phân quyền, khóa, mở khóa                                                                     |

### 3.5. Tài liệu

Thư mục [use-case/doc](use-case/doc) chứa phần phân rã và đặc tả của từng nhóm use case: quản lý tài khoản, thông tin cá nhân, tra cứu sách, yêu cầu mượn, xử lý trả sách và thống kê. Thư mục này cũng có bản mô tả use case tổng quát và báo cáo tổng hợp lần 1.

## 4. Công cụ

- [StarUML](https://staruml.io/) — mở và chỉnh sửa file mô hình `.mdj`.
- Microsoft Word (hoặc trình soạn thảo tương thích) — đọc các tài liệu `.docx`.

## 5. Bắt đầu

1. Clone repository:

   ```bash
   git clone <repository-url>
   ```
2. Mở `use-case/UC_Library_Management.mdj` bằng StarUML.
3. Đọc file `.docx` tương ứng trong `use-case/doc` để xem mô tả từng use case.

## 6. Quy trình làm việc nhóm

1. Chạy `git pull` để lấy thay đổi mới nhất trước khi chỉnh sửa.
2. Chỉ sửa sơ đồ hoặc tài liệu được phân công, để file `.mdj` dùng chung không bị xung đột. File mô hình dạng này rất khó merge.
3. Commit với thông điệp rõ ràng, ví dụ `update return processing use case`.
4. Push, và báo cho nhóm khi bạn thay đổi mô hình dùng chung.
