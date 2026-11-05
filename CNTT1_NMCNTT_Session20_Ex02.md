# SESSION 19 – EXERCISE 02
# BẢO VỆ MẬT KHẨU VÀ PASSWORD MANAGER

# 1. VẤN ĐỀ

## Câu 1. Cơ chế Hacker sử dụng mật khẩu bị rò rỉ để chiếm đoạt nhiều tài khoản

Đây là kiểu tấn công **Credential Stuffing (tấn công nhồi nhét thông tin đăng nhập)**.

Cơ chế hoạt động:

1. Hacker xâm nhập một diễn đàn công nghệ nhỏ và lấy được dữ liệu tài khoản bị rò rỉ.
2. Hacker thu thập tên đăng nhập và mật khẩu của người dùng.
3. Hacker sử dụng công cụ tự động thử những thông tin đăng nhập này trên các nền tảng lớn như Gmail, Facebook và GitHub.
4. Nếu người dùng sử dụng cùng một mật khẩu trên nhiều website, hacker có thể đăng nhập thành công vào các tài khoản đó.
5. Hacker tiếp tục lợi dụng những tài khoản bị chiếm đoạt để truy cập dữ liệu hoặc thực hiện các hành vi trái phép.

**Ví dụ:**

Người dùng sử dụng mật khẩu `123456` cho cả 4 tài khoản:

- Diễn đàn công nghệ.
- Gmail.
- Facebook.
- GitHub.

Khi mật khẩu diễn đàn bị lộ, hacker thử lại mật khẩu đó trên Gmail, Facebook và GitHub. Nếu các tài khoản vẫn dùng mật khẩu cũ, chúng có nguy cơ bị chiếm đoạt.

Đây chính là hiệu ứng domino: Một tài khoản bị lộ có thể kéo theo nhiều tài khoản khác.

---

# 2. YÊU CẦU

## Câu 2. Vì sao mật khẩu cảm tính dễ bị bẻ khóa hơn mật khẩu do máy tính sinh ra?

**Mật khẩu cảm tính** là mật khẩu do con người tự nghĩ ra, thường sử dụng những thông tin dễ đoán như:

- Ngày sinh.
- Tên cá nhân hoặc người thân.
- Số điện thoại.
- Những dãy số phổ biến như `123456`, `111111`.
- Tên kết hợp với năm sinh.

Những mật khẩu này dễ bị đoán vì hacker có thể sử dụng danh sách mật khẩu phổ biến và thông tin cá nhân để thử tự động.

**Mật khẩu do máy tính sinh ra:**

- Được tạo ngẫu nhiên.
- Có độ dài lớn.
- Kết hợp chữ hoa, chữ thường, chữ số và ký tự đặc biệt.
- Khó đoán hơn vì không dựa trên những thông tin quen thuộc của con người.

**So sánh:**

| Tiêu chí | Mật khẩu cảm tính | Mật khẩu máy tính sinh ra |
|---|---|---|
| Cách tạo | Con người tự nghĩ | Tạo ngẫu nhiên |
| Độ khó đoán | Thường thấp | Thường cao |
| Tính ngẫu nhiên | Thường thấp | Cao nếu dùng bộ tạo an toàn |
| Khả năng bị đoán | Dễ bị đoán hơn | Khó đoán hơn |
| Ví dụ | `123456`, `baobao2008` | Chuỗi ngẫu nhiên dài, phức tạp |

**Kết luận:** Nên sử dụng Password Manager để tạo mật khẩu ngẫu nhiên, dài và khác nhau cho từng tài khoản.

## Câu 3. Vì sao lưu mật khẩu trong Password Manager an toàn hơn ghi chép thủ công?

Password Manager là công cụ quản lý mật khẩu, giúp tạo, lưu trữ và tự động điền mật khẩu cho các tài khoản.

Một số công cụ phổ biến:
- Bitwarden.
- 1Password.
- KeePass.

### Nguyên lý AES-256

**AES-256 (Advanced Encryption Standard 256-bit)** là tiêu chuẩn mã hóa đối xứng sử dụng khóa mã hóa có độ dài 256 bit.

Nguyên lý hoạt động:

1. Người dùng tạo Master Password để bảo vệ kho mật khẩu.
2. Password Manager sử dụng khóa mã hóa được tạo từ thông tin xác thực để mã hóa dữ liệu.
3. Dữ liệu mật khẩu được mã hóa trước khi lưu trữ hoặc đồng bộ lên máy chủ.
4. Khi người dùng xác thực thành công, ứng dụng sử dụng khóa phù hợp để giải mã dữ liệu trên thiết bị.

**Vì sao an toàn hơn ghi chép thủ công?**

- Mật khẩu được mã hóa bằng thuật toán AES-256 thay vì lưu dưới dạng văn bản thông thường.
- Người khác không thể đọc trực tiếp dữ liệu đã mã hóa nếu không có khóa giải mã phù hợp.
- Có thể tạo mật khẩu dài, ngẫu nhiên và riêng biệt cho từng tài khoản.
- Không cần ghi nhớ hoặc ghi chép nhiều mật khẩu.
- Giảm nguy cơ mất mật khẩu do giấy ghi chép bị thất lạc hoặc người khác nhìn thấy.


# 3. CÁCH LÀM

## Câu 4. Giải pháp khắc phục và phòng tránh hiệu ứng domino

### Bước 1. Xử lý các tài khoản có nguy cơ bị lộ

- Sử dụng thiết bị sạch để thay đổi mật khẩu Gmail, Facebook và GitHub.
- Thu hồi các phiên đăng nhập và thiết bị không nhận diện được.
- Kiểm tra hoạt động đăng nhập bất thường.
- Bật xác thực hai yếu tố (2FA).

### Bước 2. Sử dụng Password Manager

- Cài đặt một Password Manager đáng tin cậy như Bitwarden.
- Tạo Master Password mạnh và không sử dụng lại mật khẩu ở nơi khác.
- Sử dụng Generator để tạo mật khẩu ngẫu nhiên.
- Lưu mật khẩu riêng biệt cho từng tài khoản.

### Bước 3. Thiết lập nguyên tắc bảo mật

- Không sử dụng chung mật khẩu giữa các tài khoản.
- Không chia sẻ mật khẩu qua tin nhắn hoặc email.
- Không lưu mật khẩu trong file văn bản không được bảo vệ.
- Không nhập mật khẩu vào website không rõ nguồn gốc.
- Thường xuyên kiểm tra cảnh báo bảo mật của các tài khoản.

## Câu 5. Kết luận

Việc sử dụng chung mật khẩu là một rủi ro lớn vì chỉ cần một website bị rò rỉ dữ liệu, các tài khoản khác cũng có thể bị ảnh hưởng.

Sử dụng Password Manager kết hợp với mật khẩu ngẫu nhiên, AES-256 và xác thực hai yếu tố giúp tăng cường bảo vệ tài khoản cá nhân.


