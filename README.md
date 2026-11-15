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
- [x] Sơ đồ lớp (Class)
- [X] Sơ đồ tuần tự (Sequence)
- [X] Sơ đồ hoạt động (Activity)
- [x] Sơ đồ trạng thái (State machine)
- [x] Báo cáo tổng hợp lần 1 và lần 2
- [x] Báo cáo cá nhân (Bảo, Tài)

## 3. Cấu trúc thư mục

```text
.
├── README.md
├── use-case/
│   ├── all-usse-case.mdj          # Tất cả sơ đồ use case (StarUML)
│   └── doc-share/                 # Đặc tả và phân rã use case (.docx)
├── class-diagram/
│   └── ClassDiagram.mdj           # Sơ đồ lớp
├── sequence-diagram/
│   ├── all-sequence-diagram.mdj   # Tất cả sơ đồ tuần tự
│   └── sequence-diagram-for-bao.mdj
├── activity-diagram/
│   ├── activity-diagram-thu-vien.mdj
│   ├── activity-diagram-for-bao-report.mdj
│   └── activity_Tai.mdj
├── state-diagram/
│   └── all-state-diagram.mdj      # Sơ đồ trạng thái
├── bao-report-main/               # Báo cáo cá nhân của Bảo (.docx, .mdj, ảnh .png)
├── Tai-report_main/               # Báo cáo cá nhân của Tài (.docx, .mdj)
└── summary-report-doc/            # Báo cáo tổng hợp lần 1, lần 2 (.docx, .pdf)
```

## 4. Sơ đồ Use Case

### 4.1. Các tác nhân (Actor)

| Actor               | Mô tả                                                                                             |
| ------------------- | --------------------------------------------------------------------------------------------------- |
| Người dùng chung | Actor cơ sở cho mọi người dùng: đăng nhập, đăng xuất, thông tin cá nhân, thông báo |
| Độc giả          | Tra cứu sách, gửi yêu cầu mượn, theo dõi trạng thái yêu cầu và lịch sử mượn trả   |
| Thủ thư           | Quản lý sách, độc giả, thẻ thư viện, yêu cầu mượn và việc trả sách                 |
| Quản trị viên    | Quản lý tài khoản, phân quyền và thống kê                                                  |

### 4.2. Các use case chính

Sơ đồ tổng quát (`Use case tổng quát hệ thống quản lý thư viện`) gồm các use case chính sau:

| Actor               | Use case chính                                                                                                                                                                 |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Người dùng chung | Đăng nhập, Đăng xuất, Quản lý thông tin cá nhân, Xem thông báo                                                                                                     |
| Độc giả          | Tra cứu sách, Xem thông tin chi tiết sách, Đăng ký mượn sách trực tuyến, Gia hạn mượn sách, Xem trạng thái yêu cầu mượn, Theo dõi lịch sử mượn trả |
| Thủ thư           | Quản lý sách, Quản lý danh mục sách, Quản lý độc giả, Quản lý yêu cầu mượn, Xử lý trả sách, Xem thống kê                                                |
| Quản trị viên    | Quản lý tài khoản, Đặt hạn mức mượn, Xem thống kê                                                                                                                   |

### 4.3. Các use case phân rã

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

### 4.4. Tài liệu

Thư mục [use-case/doc-share](use-case/doc-share) chứa phần phân rã và đặc tả use case: quản lý tài khoản, thông tin cá nhân, tra cứu sách, quản lý sách, danh mục sách, độc giả và xử lý trả sách, cùng bản đặc tả use case tổng quát. Các báo cáo tổng hợp nằm trong [summary-report-doc](summary-report-doc).

## 5. Các sơ đồ khác

| Sơ đồ       | File                                                                                                                   |
| ------------ | ---------------------------------------------------------------------------------------------------------------------- |
| Lớp        | [class-diagram/ClassDiagram.mdj](class-diagram/ClassDiagram.mdj)                                                       |
| Tuần tự    | [sequence-diagram/all-sequence-diagram.mdj](sequence-diagram/all-sequence-diagram.mdj)                                 |
| Hoạt động | [activity-diagram/activity-diagram-thu-vien.mdj](activity-diagram/activity-diagram-thu-vien.mdj)                       |
| Trạng thái | [state-diagram/all-state-diagram.mdj](state-diagram/all-state-diagram.mdj)                                             |

## 6. Công cụ

- [StarUML](https://staruml.io/) — mở và chỉnh sửa file mô hình `.mdj`.
- Microsoft Word (hoặc trình soạn thảo tương thích) — đọc các tài liệu `.docx`.

## 7. Bắt đầu

1. Clone repository:

   ```bash
   git clone <repository-url>
   ```
2. Mở `use-case/all-usse-case.mdj` (hoặc file `.mdj` của sơ đồ cần xem) bằng StarUML.
3. Đọc file `.docx` tương ứng trong `use-case/doc-share` để xem mô tả từng use case.

## 8. Quy trình làm việc nhóm

1. Chạy `git pull` để lấy thay đổi mới nhất trước khi chỉnh sửa.
2. Chỉ sửa sơ đồ hoặc tài liệu được phân công, để file `.mdj` dùng chung không bị xung đột. File mô hình dạng này rất khó merge.
3. Commit với thông điệp rõ ràng, ví dụ `update return processing use case`.
4. Push, và báo cho nhóm khi bạn thay đổi mô hình dùng chung.
