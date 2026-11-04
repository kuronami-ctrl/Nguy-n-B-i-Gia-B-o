# BÀI TỔNG HỢP SESSION 18 – AN TOÀN THÔNG TIN CÁ NHÂN CHO DEVELOPER

# 1. VẤN ĐỀ

## PHẦN 1 – NHẬN DIỆN RỦI RO VÀ XỬ LÝ SỰ CỐ

### Câu 1. Tình huống 1: Email giả mạo GitHub

- Loại tấn công chính: **Phishing (tấn công giả mạo)**.
- Thủ thuật được sử dụng: **Typosquatting (chiếm dụng tên miền gần giống)**.

**Chi tiết đáng ngờ:**

- Tên miền `githuh-security.com` giả mạo tên miền GitHub chính thức bằng cách thay chữ `b` thành chữ `h`.
- Email yêu cầu người dùng bấm vào đường link lạ để mở khóa tài khoản.
- Trang web yêu cầu nhập lại mật khẩu, có nguy cơ đánh cắp thông tin đăng nhập.

**Kết luận:** Đây là email Phishing sử dụng Typosquatting để lừa người dùng truy cập website giả mạo.

### Câu 2. Tình huống 2: Phần mềm Crack

- Loại cạm bẫy: **Malware (mã độc)** được ngụy trang trong phần mềm Crack.
- Đây có thể là **Trojan (mã độc giả dạng phần mềm hợp pháp)**.

**Vì sao yêu cầu tắt Windows Defender nguy hiểm?**

- Windows Defender có nhiệm vụ phát hiện và ngăn chặn mã độc.
- Khi tắt Defender, máy tính mất đi một lớp bảo vệ quan trọng.
- File Crack có thể chứa mã độc đánh cắp mật khẩu, Cookie, dữ liệu cá nhân hoặc thông tin dự án.
- Hacker có thể lợi dụng máy tính bị nhiễm mã độc để xâm nhập các tài khoản khác.

### Câu 3. Áp dụng Quy tắc 5 KHÔNG

| Quy tắc | Tình huống 1 – Phishing | Tình huống 2 – Crack |
|---|---|---|
| Không bấm vào link lạ | Không truy cập link giả mạo GitHub | Không truy cập link tải Crack đáng ngờ |
| Không cung cấp mật khẩu | Không nhập mật khẩu vào website lạ | Không nhập thông tin tài khoản vào phần mềm không rõ nguồn gốc |
| Không tải file không rõ nguồn gốc | Không tải tệp đính kèm đáng ngờ | Không tải và chạy file Crack |
| Không tắt phần mềm bảo mật | Không làm theo yêu cầu đáng ngờ trong email | Không tắt Windows Defender |
| Không chủ quan trước cảnh báo | Kiểm tra kỹ địa chỉ người gửi và tên miền | Không bỏ qua cảnh báo của Windows Defender |

### Câu 4. Quy trình Cấp cứu 4 Bước khi đã chạy file Crack

1. **Ngắt kết nối:** Ngắt Wi-Fi và dây mạng để hạn chế mã độc tiếp tục liên lạc hoặc truyền dữ liệu.
2. **Báo cáo:** Thông báo ngay cho trưởng nhóm hoặc bộ phận IT để phối hợp xử lý.
3. **Bảo vệ tài khoản:** Sử dụng một thiết bị sạch để đổi mật khẩu, thu hồi các phiên đăng nhập và token đáng ngờ. Ưu tiên tài khoản email, GitHub và Vercel.
4. **Làm sạch thiết bị:** Quét mã độc bằng công cụ bảo mật đáng tin cậy. Nếu cần, nhờ IT cài đặt lại hệ điều hành từ nguồn chính thức trước khi sử dụng lại.

**Lưu ý:** Không đăng nhập tài khoản quan trọng trên máy tính đang nghi nhiễm mã độc.

---

## PHẦN 2 – CHUYỂN SANG PASSWORD MANAGER

### Câu 1. Nguy cơ khi sử dụng chung mật khẩu

Nhóm đang dùng chung một mật khẩu cho GitHub, Vercel và Email.

Nếu email nhóm bị lộ mật khẩu, hacker có thể thử sử dụng chính mật khẩu đó để đăng nhập vào GitHub và Vercel.

Kiểu tấn công này gọi là **Credential Stuffing (tấn công nhồi nhét thông tin đăng nhập)**.

**Hậu quả:**

- GitHub có thể bị truy cập trái phép, làm lộ mã nguồn.
- Vercel có thể bị lợi dụng để truy cập hoặc thay đổi dự án triển khai.
- Email nhóm có thể bị chiếm quyền kiểm soát.

### Câu 2. Zero-Knowledge Architecture là gì?

Zero-Knowledge Architecture là kiến trúc bảo mật trong đó nhà cung cấp dịch vụ không biết và không thể trực tiếp đọc dữ liệu đã mã hóa của người dùng.

Với Bitwarden:

- Dữ liệu được mã hóa ngay trên thiết bị người dùng.
- Máy chủ Bitwarden chỉ lưu trữ dữ liệu đã mã hóa.
- Khi đăng nhập, người dùng sử dụng Master Password để giải mã dữ liệu trên thiết bị.

**Kết luận:** Nếu máy chủ Bitwarden bị hacker xâm nhập, hacker chủ yếu chỉ lấy được dữ liệu đã mã hóa. Họ không thể đọc trực tiếp mật khẩu nếu không có khóa giải mã phù hợp. Tuy nhiên, Master Password yếu hoặc thiết bị bị nhiễm mã độc vẫn có thể khiến dữ liệu bị lộ.

### Câu 3. Cấu hình Password Generator

Nên sử dụng Password Manager để tạo 3 mật khẩu ngẫu nhiên, riêng biệt cho GitHub, Vercel và Email nhóm.

| Thông số | Giá trị cấu hình |
|---|---|
| Độ dài | 24 ký tự |
| Chữ hoa (A–Z) | Bật |
| Chữ thường (a–z) | Bật |
| Chữ số (0–9) | Bật |
| Ký tự đặc biệt | Bật |

**Yêu cầu:** Mỗi tài khoản phải có một mật khẩu riêng, không sử dụng lại mật khẩu cũ hoặc mật khẩu của tài khoản khác.

---

## PHẦN 3 – KÍCH HOẠT 2FA CHO TÀI KHOẢN GITHUB TỔ CHỨC

### Câu 1. Vì sao nên dùng Authenticator App thay SMS OTP?

Nên sử dụng **Authenticator App (TOTP)** như Google Authenticator thay vì SMS OTP.

**Hai nhược điểm của SMS OTP:**

1. **SIM Swapping:** Hacker có thể chiếm quyền sử dụng số điện thoại bằng cách lừa nhà mạng chuyển SIM, từ đó nhận được mã OTP.
2. **Phụ thuộc mạng di động:** SMS OTP cần mạng điện thoại để nhận mã, có thể gặp khó khăn khi mất sóng hoặc đi nước ngoài.

**Ưu điểm của TOTP:**

- Tạo mã OTP ngay trên điện thoại.
- Không cần kết nối Internet hoặc mạng di động để tạo mã.
- Mã thường có 6 chữ số và tự thay đổi sau khoảng 30 giây.

### Câu 2. Các bước kích hoạt 2FA bằng Google Authenticator

1. Đăng nhập tài khoản GitHub.
2. Nhấn ảnh đại diện ở góc trên bên phải.
3. Chọn **Settings**.
4. Chọn **Password and authentication**.
5. Tìm mục **Two-factor authentication**.
6. Chọn bật 2FA bằng **Authenticator App**.
7. Mở ứng dụng Google Authenticator trên điện thoại.
8. Chọn thêm tài khoản mới và quét mã QR do GitHub cung cấp.
9. Google Authenticator sẽ tạo mã OTP gồm 6 chữ số.
10. Nhập mã 6 số vào GitHub để xác nhận kích hoạt.

### Câu 3. Lưu trữ 10 mã khôi phục

**NÊN LÀM:**

- In mã khôi phục ra giấy và cất trong két hoặc tủ có khóa.
- Lưu một bản trong kho lưu trữ mã hóa riêng biệt, có kiểm soát quyền truy cập.

**KHÔNG NÊN LÀM:**

- Không lưu ảnh chụp mã khôi phục trong thư viện ảnh điện thoại.
- Không gửi mã qua Messenger, Zalo, email hoặc nhóm chat.
- Không đưa mã khôi phục lên GitHub.
- Không chia sẻ mã cho người khác.

**Lưu ý:** Mỗi mã khôi phục thường chỉ sử dụng được một lần. Khi đã sử dụng hoặc nghi bị lộ, cần tạo bộ mã mới.

---

# 2. YÊU CẦU

## PHẦN 4 – BẢO VỆ SECRETS TRƯỚC KHI PUSH CODE

### Câu 1. Xác định 2 giá trị Secrets bị hardcode

Trong file `config.js` ban đầu có 2 giá trị Secrets:

1. `API_KEY`: Khóa API dùng để xác thực với dịch vụ.
2. `DB_PASSWORD`: Mật khẩu kết nối cơ sở dữ liệu.

Đây là thông tin nhạy cảm. Nếu push lên GitHub công khai, người khác có thể nhìn thấy và lợi dụng chúng.

### Câu 2. Viết lại code sử dụng process.env

File `config.js` sau khi sửa:

```javascript
require('dotenv').config();

const API_KEY = process.env.API_KEY;
const DB_PASSWORD = process.env.DB_PASSWORD;

function connectDatabase() {
  return connect(DB_PASSWORD);
}
