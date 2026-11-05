# SESSION 19 – EXERCISE 01
# NHẬN DIỆN HOMOGRAPH ATTACK

# 1. VẤN ĐỀ

## Câu 1. Chỉ ra ký tự lạ trong URL
URL được cung cấp:
`https://githúb.com/login`
Ký tự đáng ngờ là **`ú`** trong tên miền `githúb.com`.
- Chữ `ú`   (chữ u có dấu sắc).
- Hai ký tự có hình dáng khá giống nhau khi nhìn nhanh, khiến người dùng dễ nhầm `githúb.com` với tên miền chính thức `github.com`.

Đây là **Homograph Attack (tấn công giả mạo ký tự tương đồng)**.

Kẻ xấu lợi dụng những ký tự có hình dáng giống hoặc gần giống ký tự thật để tạo tên miền giả mạo, đánh lừa người dùng truy cập và nhập thông tin đăng nhập.


# 2. YÊU CẦU

## Câu 2. Quy trình kiểm tra URL trước khi nhập Master Password

### Bước 1. Kiểm tra bằng mắt thường

- Đọc kỹ toàn bộ tên miền, đặc biệt là phần nằm trước dấu `/`.
- Kiểm tra lỗi chính tả, ký tự lạ, dấu tiếng Việt và các ký tự trông giống nhau.
- So sánh với tên miền chính thức `github.com`.
- Không chỉ nhìn biểu tượng ổ khóa HTTPS vì website giả mạo cũng có thể sử dụng HTTPS.

### Bước 2. Kiểm tra địa chỉ thực tế

- Di chuột lên đường link để xem địa chỉ đích trước khi nhấp.
- Không tin đường link chỉ vì tên hiển thị là GitHub.
- Nếu nhận được thông báo bảo mật bất ngờ, không dùng link trong email hoặc tin nhắn để đăng nhập.

### Bước 3. Sử dụng công cụ hỗ trợ

- **Trình duyệt:** Kiểm tra thanh địa chỉ và cảnh báo bảo mật. Một số trình duyệt có thể hiển thị tên miền Unicode dưới dạng Punycode khi phát hiện nguy cơ giả mạo.
- **Công cụ kiểm tra Unicode:** Sử dụng Unicode Character Inspector để kiểm tra mã Unicode của từng ký tự và phát hiện ký tự bất thường.
- **Password Manager:** Kiểm tra tên miền có khớp với địa chỉ đã lưu hay không. Password Manager thường không tự điền mật khẩu nếu tên miền không khớp.

### Bước 4. Truy cập GitHub an toàn

- Tự nhập địa chỉ `https://github.com` vào thanh địa chỉ trình duyệt.
- Đăng nhập từ trang chính thức, không truy cập qua đường link đáng ngờ.
- Chỉ nhập Master Password khi đã xác minh đúng tên miền.

# 3. CÁCH LÀM

## Quy trình kiểm tra nhanh

```text
Nhận được thông báo Security Alert
              |
              v
      Kiểm tra tên miền
              |
              v
  Có ký tự lạ hoặc sai chính tả?
          /           \
        Có             Không
        |                |
        v                v
 Không nhập mật khẩu   Kiểm tra tiếp
        |                |
        v                v
 Tự nhập github.com   Kiểm tra bằng
 vào trình duyệt      công cụ hỗ trợ
                         |
                         v
                Xác minh đúng tên miền
                         |
                         v
                Đăng nhập an toàn
