

## PHẦN 1. PHÂN TÍCH BÀI TOÁN (I/O)

### 1. Đầu vào và đầu ra

**Đầu vào (Input):**
- Engineering: 3 người.
- Design: 2 người.
- Business: 2 người.
- Nhà đầu tư bên ngoài: 1 người.
- Tài liệu: mã nguồn, thiết kế, kế hoạch kinh doanh, Pitch Deck, khóa API và dữ liệu khách hàng.
- Yêu cầu: phân quyền bảo mật, lưu lịch sử phiên bản tối thiểu 30 ngày, nhà đầu tư hết quyền sau 14 ngày.

**Đầu ra (Output):**
- Cấu trúc thư mục Google Drive.
- Bảng phân quyền cho từng nhóm.
- Quy trình chia sẻ, kiểm tra và thu hồi quyền.

### 2. Cấu trúc thư mục Google Drive

    CampusPay/
    |-- 01_Technical/
    |   |-- Source_Code/
    |   |-- API_Test/
    |   |-- Technical_Docs/
    |
    |-- 02_Design/
    |   |-- UI_UX/
    |   |-- Graphic_Assets/
    |
    |-- 03_Business/
    |   |-- Business_Plan/
    |   |-- Partner_Info/
    |
    |-- 04_Shared/
    |   |-- Business_Summary/
    |   |-- Pitch_Deck/
    |
    |-- 05_Restricted/
        |-- API_Keys/
        |-- Customer_Data/

**Giải thích:**

- `01_Technical`: Chứa mã nguồn và tài liệu kỹ thuật.
- `02_Design`: Chứa bản thiết kế và hình ảnh.
- `03_Business`: Chứa kế hoạch kinh doanh và thông tin đối tác.
- `04_Shared`: Chứa tài liệu được phép chia sẻ có kiểm soát.
- `05_Restricted`: Chứa khóa API và dữ liệu khách hàng. Chỉ người được cấp quyền mới có thể truy cập.

### 3. Các bước thiết lập

**Bước 1: Tạo thư mục**

Tạo thư mục chính `CampusPay`, sau đó tạo các thư mục con theo cấu trúc trên.

**Bước 2: Đặt tên file**

Đặt tên file ngắn gọn, dễ hiểu, sử dụng tiếng Anh và dấu gạch dưới.

Ví dụ: `Business_Plan.docx`, `Pitch_Deck.pdf`.

**Bước 3: Phân quyền**

- Engineering: Chỉnh sửa mã nguồn và tài liệu kỹ thuật.
- Design: Chỉnh sửa tài liệu thiết kế.
- Business: Chỉnh sửa kế hoạch kinh doanh và tài liệu giới thiệu.
- Nhà đầu tư: Chỉ xem tài liệu được phép chia sẻ.

**Bước 4: Bảo vệ dữ liệu nhạy cảm**

Thư mục `05_Restricted` chỉ cấp quyền cho người thực sự cần thiết. Không chia sẻ công khai khóa API và dữ liệu khách hàng.

**Bước 5: Kiểm tra lịch sử phiên bản**

Sử dụng Version History của Google Docs, Sheets hoặc Slides. Kiểm tra khả năng khôi phục và chính sách lưu trữ để đáp ứng yêu cầu tối thiểu 30 ngày.

**Bước 6: Chia sẻ cho nhà đầu tư**

Chỉ chia sẻ tài liệu cần thiết, ưu tiên bản PDF của Pitch Deck. Cấp quyền Viewer và đặt thời hạn 14 ngày nếu tài khoản hỗ trợ. Nếu không hỗ trợ, thu hồi quyền thủ công đúng hạn.

**Bước 7: Kiểm tra quyền**

Kiểm tra bằng tài khoản đại diện từng nhóm để đảm bảo mỗi nhóm chỉ truy cập được tài liệu phù hợp.

**Bước 8: Thu hồi quyền**

Khi thành viên rời dự án, xóa quyền trực tiếp và quyền thông qua nhóm. Khi hết 14 ngày, thu hồi quyền của nhà đầu tư.

---

## PHẦN 2. BẢNG PHÂN QUYỀN

### 1. Quy ước quyền

- **E - Editor:** Được chỉnh sửa.
- **C - Commenter:** Được nhận xét.
- **V - Viewer:** Chỉ được xem.
- **R - Restricted:** Không được truy cập nếu chưa được cấp quyền riêng.

### 2. Bảng phân quyền chi tiết

| Loại tài liệu | Engineering | Design | Business | Nhà đầu tư | Ghi chú bảo mật |
|---|---|---|---|---|---|
| Mã nguồn và tài liệu kỹ thuật | E | R | V | R | Chỉ Engineering chỉnh sửa mã nguồn |
| Tài liệu thiết kế và hình ảnh | V | E | V | R | Chỉ Design chỉnh sửa |
| Business Plan và thông tin đối tác | V | R | E | V | Engineering chỉ xem, không chỉnh sửa |
| Business Summary và Pitch Deck | V | V | E | V | Nhà đầu tư chỉ xem bản được chia sẻ |
| Khóa API và dữ liệu khách hàng | R | R | R | R | Chỉ người được ủy quyền riêng mới được truy cập |

**Lưu ý:** R có nghĩa là không được cấp quyền truy cập theo mặc định. Người cần truy cập dữ liệu nhạy cảm phải được phê duyệt riêng.

### 3. Xử lý các tình huống bảo mật

**Tình huống 1: Engineering cần xem Business Plan nhưng không được sửa.**

Giải pháp: Cấp quyền Viewer cho Engineering. Thành viên có thể xem nội dung nhưng không thể chỉnh sửa trực tiếp.

**Tình huống 2: Nhà đầu tư muốn tải Pitch Deck về máy nhưng không được sửa.**

Giải pháp:
- Xuất Pitch Deck thành file PDF.
- Chia sẻ file PDF với quyền Viewer.
- Cho phép tải xuống nếu cần.
- Đặt thời hạn truy cập 14 ngày nếu tài khoản hỗ trợ.

Lưu ý: Quyền Viewer không ngăn được mọi hình thức sao chép nội dung. Vì vậy, chỉ chia sẻ thông tin thực sự cần thiết.

**Tình huống 3: Thành viên rời dự án.**

Giải pháp:
- Xóa thành viên khỏi nhóm được cấp quyền.
- Kiểm tra và xóa các quyền chia sẻ trực tiếp.
- Kiểm tra quyền truy cập vào các thư mục và file quan trọng.
- Nếu sử dụng tài khoản do tổ chức quản lý, quản trị viên có thể khóa tài khoản khi cần.


