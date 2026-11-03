# QUẢN LÝ COOKIES VÀ CACHE TRONG TRÌNH DUYỆT

## PHẦN 1. PHÂN TÍCH

### 1. So sánh Cache và Cookies

| Tiêu chí | Cache | Cookies |
|---|---|---|
| Dung lượng | Có thể từ MB đến GB | Thường giới hạn khoảng 4KB mỗi Cookie |
| Mục đích | Lưu hình ảnh, CSS, JavaScript để tải trang nhanh hơn | Lưu thông tin phiên đăng nhập và tùy chọn người dùng |
| Thời gian lưu | Tùy chính sách Cache của trình duyệt | Có thể lưu theo phiên hoặc thời hạn được thiết lập |
| Ví dụ | Logo, hình ảnh, file CSS | Session Token, tùy chọn ngôn ngữ |

### 2. Phân biệt Session Cookies và Persistent Cookies

- **Session Cookies:** Thường bị xóa khi phiên trình duyệt kết thúc. Người dùng có thể phải đăng nhập lại.
- **Persistent Cookies:** Có thời hạn lưu trữ cụ thể bằng `Max-Age` hoặc `Expires`. Cookie vẫn tồn tại sau khi đóng và mở lại trình duyệt, nếu chưa hết hạn hoặc bị xóa.

**Giải pháp:** Sử dụng Persistent Cookie để duy trì trạng thái đăng nhập và giỏ hàng của shipper.

Lưu ý: Giỏ hàng nên được lưu ở phía Server hoặc cơ sở dữ liệu. Cookie chỉ nên lưu mã định danh hoặc Token cần thiết, không nên lưu toàn bộ dữ liệu giỏ hàng.

---

## PHẦN 2. TRIỂN KHAI

### 1. Cấu trúc Cookie đề xuất

Ví dụ cấu hình Cookie:

```http
Set-Cookie: session_token=RANDOM_TOKEN; Max-Age=604800; Path=/; HttpOnly; Secure; SameSite=Lax
```
### 2. Giải thích các thành phần
|thành phần|chức năng|
|-|-|
|session_token|Tên Cookie lưu mã Token phiên đăng nhập|
|RANDOM_TOKEN|Token ngẫu nhiên do Server tạo
|Max-Age=604800|Cookie tồn tại trong 7 ngày
|Path=/|Cookie có hiệu lực trên toàn bộ website
|HttpOnly|Ngăn JavaScript phía Client đọc Cookie
|Secure|Chỉ gửi Cookie qua kết nối HTTPS
|SameSite=Lax|Hạn chế Cookie được gửi trong một số yêu cầu từ website khác
### 3. Cơ chế hoạt động

1.  Shipper đăng nhập thành công.    
2.  Server tạo một Token ngẫu nhiên và gửi Cookie về trình duyệt.    
3.  Trình duyệt lưu Cookie theo thời hạn `Max-Age`.    
4.  Khi shipper đóng rồi mở lại trình duyệt, Cookie vẫn còn hiệu lực.    
5.  Khi truy cập website, trình duyệt tự động gửi Cookie đến Server.    
6.  Server kiểm tra Token để xác nhận phiên đăng nhập và tải lại giỏ hàng từ cơ sở dữ liệu.
    

### 4. Đảm bảo bảo mật

-   Sử dụng `HttpOnly` để JavaScript không thể đọc Token qua `document.cookie`.
    
-   Sử dụng `Secure` để Cookie chỉ được truyền qua HTTPS.
    
-   Sử dụng `SameSite` để giảm nguy cơ tấn công CSRF.
    
-   Token phải được tạo ngẫu nhiên, khó đoán và có thể bị thu hồi khi đăng xuất.
    
-   Không lưu mật khẩu hoặc thông tin nhạy cảm trực tiếp trong Cookie.
    

## PHẦN 3. KIỂM THỬ

### 1. Tình huống

Shipper thay đổi giao diện website nhưng sau khi tải lại trang, trình duyệt vẫn hiển thị màu sắc cũ.

### 2. Nguyên nhân

Trình duyệt có thể đang sử dụng file CSS cũ được lưu trong Cache thay vì tải phiên bản mới từ máy chủ.

### 3. Cách xử lý bằng Hard Reload

Thực hiện các bước:

1.  Mở website cần kiểm tra.
    
2.  Nhấn `F12` để mở Developer Tools.
    
3.  Nhấn tổ hợp phím `Ctrl + Shift + R`.
    
4.  Trình duyệt sẽ tải lại trang và yêu cầu tải mới các tài nguyên thay vì sử dụng Cache thông thường
