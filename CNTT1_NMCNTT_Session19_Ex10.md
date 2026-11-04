# SESSION: XÁC THỰC 2 YẾU TỐ (2FA) VÀ BACKUP CODES

## 1. VẤN ĐỀ

PixelForge Studio cần bảo vệ tài khoản GitHub Enterprise, mã nguồn game và hệ thống thanh toán. Tuy nhiên, nhóm đang tranh luận giữa SMS OTP và Authenticator TOTP.

Nếu chỉ sử dụng mật khẩu, tài khoản vẫn có nguy cơ bị chiếm đoạt khi mật khẩu bị lộ hoặc bị đánh cắp qua Phishing.

### Câu 1. Ba yếu tố xác thực danh tính số

| Yếu tố | Ý nghĩa | Ví dụ |
|---|---|---|
| Something You Know | Thứ người dùng biết | Mật khẩu, mã PIN |
| Something You Have | Thứ người dùng sở hữu | Điện thoại, khóa bảo mật |
| Something You Are | Đặc điểm sinh trắc học | Vân tay, khuôn mặt |

Khi sử dụng 2FA:

- Mật khẩu thuộc yếu tố **Something You Know**.
- Mã OTP thuộc yếu tố **Something You Have**, vì mã được tạo hoặc nhận thông qua thiết bị người dùng sở hữu.

### Câu 2. Nguyên lý hoạt động của TOTP

TOTP (Time-based One-Time Password) là thuật toán tạo mã OTP dựa trên thời gian.

Cơ chế hoạt động:

1. Khi thiết lập 2FA, máy chủ và ứng dụng Authenticator cùng lưu một khóa bí mật (Shared Secret).
2. Ứng dụng sử dụng khóa bí mật kết hợp với thời gian hiện tại để tạo mã OTP.
3. Mã thường có 6 chữ số và thay đổi sau mỗi 30 giây.
4. Máy chủ cũng tự tạo mã dựa trên khóa bí mật và thời gian để kiểm tra.

**Tại sao TOTP hoạt động khi bật Chế độ Máy bay?**

Vì ứng dụng Authenticator không cần kết nối Internet hoặc sóng điện thoại để tạo mã. Ứng dụng sử dụng khóa bí mật đã lưu trên thiết bị và đồng hồ hệ thống.

Do đó, TOTP vẫn hoạt động khi điện thoại bật Chế độ Máy bay, miễn là đồng hồ thiết bị được cài đặt chính xác.

---

## 2. YÊU CẦU

### Câu 3. So sánh SMS OTP và TOTP Authenticator

| Tiêu chí | SMS OTP | TOTP Authenticator |
|---|---|---|
| Chống SIM Swapping và SS7 | Thấp hơn, có nguy cơ bị chiếm đoạt số điện thoại hoặc chặn tin nhắn | Tốt hơn, không phụ thuộc SIM hay mạng viễn thông |
| Khả năng Offline | Cần mạng di động để nhận SMS | Tạo mã khi không có Internet hoặc sóng điện thoại |
| Tính tiện dụng và chi phí | Dễ sử dụng nhưng doanh nghiệp có thể mất phí gửi SMS | Không mất phí gửi SMS, cần cài ứng dụng Authenticator |
| Khi mất điện thoại | Có thể khôi phục số điện thoại bằng SIM mới nếu kiểm soát được số thuê bao | Cần sử dụng Backup Codes hoặc quy trình khôi phục tài khoản |

**Lưu ý:** TOTP an toàn hơn SMS trước các rủi ro chiếm đoạt SIM, nhưng không tuyệt đối an toàn. Khóa bí mật TOTP vẫn có thể bị đánh cắp nếu thiết bị bị xâm nhập hoặc người dùng bị lừa cung cấp mã.

### Câu 4. Lựa chọn giải pháp cho PixelForge Studio

**Đề xuất: Sử dụng TOTP Authenticator làm phương thức 2FA chính.**

Lý do:

- Không phụ thuộc vào SIM hoặc sóng điện thoại.
- Hoạt động được khi đi công tác nước ngoài hoặc trên máy bay.
- Giảm nguy cơ bị tấn công SIM Swapping và nghe lén SMS.
- Không phát sinh chi phí gửi tin nhắn OTP.
- Phù hợp để bảo vệ tài khoản GitHub Enterprise và hệ thống quan trọng.

Đối với tài khoản quản trị cấp cao, studio có thể cân nhắc sử dụng khóa bảo mật vật lý theo chuẩn FIDO2/WebAuthn để tăng khả năng chống Phishing.

---

## 3. CÁCH LÀM

### Câu 5. Quản lý Backup Codes

**Mục đích:**

Backup Codes là bộ mã khôi phục được cung cấp khi bật 2FA. Người dùng có thể sử dụng mã này để đăng nhập khi mất điện thoại hoặc không truy cập được ứng dụng Authenticator.

Thông thường, mỗi mã chỉ sử dụng được một lần.

**Hai vị trí lưu trữ an toàn:**

1. **Bản giấy:** In hoặc ghi mã ra giấy, đặt trong phong bì niêm phong và cất trong két sắt cá nhân hoặc két bảo mật của công ty.
2. **Bản điện tử:** Lưu trong kho lưu trữ mã hóa riêng biệt, có kiểm soát quyền truy cập và không đồng bộ công khai.

**Một sai lầm cần tránh:**

Không chụp ảnh Backup Codes rồi lưu trong thư viện ảnh, gửi qua Messenger, Zalo hoặc email thông thường.

Nếu tài khoản lưu trữ bị xâm nhập, kẻ xấu có thể lấy được toàn bộ mã khôi phục.

### Quy trình quản lý Backup Codes

1. Kích hoạt 2FA bằng ứng dụng Authenticator.
2. Tải hoặc ghi lại bộ Backup Codes.
3. Kiểm tra và bảo quản mã tại vị trí an toàn.
4. Chỉ người được ủy quyền mới được tiếp cận.
5. Khi sử dụng mã khôi phục, đánh dấu mã đã dùng.
6. Tạo bộ mã mới nếu bộ cũ bị mất hoặc có nguy cơ bị lộ.



