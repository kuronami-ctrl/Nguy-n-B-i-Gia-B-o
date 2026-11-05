
# SESSION 20 – EXERCISE 04
## Chủ đề: So sánh lưu mật khẩu trên Google Chrome và Bitwarden

### 1. Phân tích tình huống

Công ty đang cân nhắc hai phương án quản lý mật khẩu:

- **Google Chrome:** Lưu mật khẩu trực tiếp trên trình duyệt để đăng nhập nhanh chóng.
- **Bitwarden:** Sử dụng trình quản lý mật khẩu chuyên dụng để lưu trữ và bảo vệ thông tin đăng nhập.

Tuy nhiên, mã độc Infostealer có khả năng đánh cắp dữ liệu đăng nhập được lưu trong trình duyệt, đặc biệt là file `Login Data`.

Vì vậy, công ty cần lựa chọn giải pháp có khả năng bảo vệ mật khẩu tốt hơn, hạn chế nguy cơ bị đánh cắp thông tin.

### 2. Bảng so sánh Google Chrome và Bitwarden

| Tiêu chí | Google Chrome | Bitwarden |
|---|---|---|
| Khả năng chống Infostealer | Có thể trở thành mục tiêu của mã độc khi dữ liệu đăng nhập được lưu trong hồ sơ trình duyệt. | Dữ liệu được mã hóa trong kho mật khẩu, giúp bảo vệ tốt hơn trước việc đọc trộm dữ liệu lưu trữ. |
| Zero-Knowledge Architecture | Không có kiến trúc Zero-Knowledge độc lập dành riêng cho kho mật khẩu như Bitwarden. | Có kiến trúc Zero-Knowledge, dữ liệu được mã hóa trên thiết bị trước khi đồng bộ lên máy chủ. |
| Đồng bộ chéo nền tảng | Đồng bộ thông qua tài khoản Google và các thiết bị sử dụng Chrome. | Hỗ trợ Windows, macOS, Linux, Android, iOS và nhiều trình duyệt. |
| Quản lý mật khẩu | Lưu và tự động điền mật khẩu ngay trong trình duyệt. | Quản lý mật khẩu tập trung trên nhiều thiết bị và trình duyệt. |
| Tính tiện lợi | Nhanh chóng, dễ sử dụng. | Cần thêm thao tác mở khóa bằng Master Password hoặc phương thức phù hợp. |

### 3. Tại sao Bitwarden có lợi thế về bảo mật?

**a. Mã hóa dữ liệu trước khi đồng bộ**

- Bitwarden mã hóa dữ liệu ngay trên thiết bị người dùng.
- Máy chủ Bitwarden lưu trữ dữ liệu đã mã hóa.
- Người khác không thể đọc trực tiếp mật khẩu nếu không có khóa giải mã.

**b. Kiến trúc Zero-Knowledge**

Zero-Knowledge Architecture có nghĩa là nhà cung cấp dịch vụ không thể tự đọc nội dung mật khẩu trong kho dữ liệu của người dùng.

Bitwarden sử dụng Master Password để tạo khóa mã hóa và giải mã dữ liệu. Vì vậy, người dùng cần bảo vệ Master Password cẩn thận.

**c. Hạn chế nguy cơ bị Infostealer đánh cắp**

Infostealer là loại mã độc chuyên đánh cắp thông tin nhạy cảm như mật khẩu, cookie và dữ liệu đăng nhập.

Mã độc có thể tìm kiếm và trích xuất dữ liệu đăng nhập trong hồ sơ trình duyệt Chrome, bao gồm file `Login Data`.

Bitwarden tạo thêm một lớp bảo vệ nhờ kho mật khẩu được mã hóa và cơ chế khóa bằng Master Password.

Tuy nhiên, nếu máy tính đã nhiễm mã độc và Bitwarden đang được mở khóa, dữ liệu vẫn có nguy cơ bị đánh cắp.

### 4. Vì sao Bitwarden thắng thế dù phải nhập Master Password?

| Tiêu chí | Google Chrome | Bitwarden |
|---|---|---|
| Tốc độ đăng nhập | Nhanh hơn | Có thêm thao tác mở khóa |
| Bảo vệ kho mật khẩu | Phụ thuộc cơ chế bảo vệ của trình duyệt và hệ điều hành | Có kho mật khẩu mã hóa riêng |
| Kiểm soát truy cập | Gắn với tài khoản và hồ sơ trình duyệt | Có thể khóa kho mật khẩu bằng Master Password |
| Mức độ phù hợp với doanh nghiệp | Phù hợp nhu cầu cơ bản | Phù hợp hơn khi cần quản lý mật khẩu tập trung |

**Lập luận lựa chọn:**

Công ty nên ưu tiên Bitwarden vì bảo mật tài khoản quan trọng hơn việc tiết kiệm một vài giây khi đăng nhập.

Việc nhập Master Password là một thao tác bổ sung nhưng giúp kiểm soát thời điểm mở khóa kho mật khẩu.

Khi kết hợp với mật khẩu mạnh, tự động khóa Vault và MFA, Bitwarden giúp giảm nguy cơ lộ thông tin đăng nhập.

### 5. Đề xuất giải pháp cho công ty

1. Bắt buộc nhân viên sử dụng Bitwarden để quản lý mật khẩu.
2. Yêu cầu đặt Master Password mạnh và không sử dụng lại mật khẩu cũ.
3. Bật MFA cho tài khoản Bitwarden.
4. Thiết lập tự động khóa Vault khi không sử dụng.
5. Không lưu mật khẩu quan trọng dưới dạng văn bản hoặc hình ảnh.
6. Cài đặt phần mềm bảo mật và thường xuyên kiểm tra mã độc trên máy tính.



