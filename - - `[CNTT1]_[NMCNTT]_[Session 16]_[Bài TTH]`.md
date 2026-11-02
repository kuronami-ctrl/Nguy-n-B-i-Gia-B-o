
# PHẦN A. QUẢN LÝ BROWSER PROFILE VÀ BOOKMARK

## 1. Vấn đề khi dùng chung một Profile
Khi sử dụng chung một Chrome Profile cho tài khoản cá nhân và công ty, dữ liệu như Cookies, History và Bookmarks có thể bị trộn lẫn. Điều này dễ gây nhầm lẫn tài khoản và xung đột phiên đăng nhập.

## 2. Thiết lập 3 Chrome Profiles

| Profile | Mục đích sử dụng |
|---|---|
| Personal | Sử dụng mạng xã hội, email và GitHub cá nhân |
| Company_Work | Sử dụng GitHub công ty, email công ty và công cụ nội bộ |
| Sandbox_Test | Kiểm thử website, API và tiện ích mở rộng |

Mỗi Profile có dữ liệu riêng như Cookies, History, Bookmarks và Extensions.

## 3. Tổ chức Bookmark

- **01_Work:** GitHub công ty, Email công ty.
- **02_Development:** MDN Web Docs, Stack Overflow.
- **03_Learning:** W3Schools, GitHub cá nhân.

## 4. Cho người khác mượn máy tính
Nên sử dụng **Guest Profile** thay vì Profile cá nhân.

- Tạo phiên duyệt web tạm thời.
- Không sử dụng dữ liệu đăng nhập của Profile chính.
- Đóng toàn bộ cửa sổ Guest sau khi sử dụng để xóa dữ liệu phiên Guest.

---

# PHẦN B. EXTENSIONS

## 1. Chọn tiện ích phù hợp

Sử dụng tiện ích **JSON Viewer** thuộc nhóm Dev Suite để hiển thị dữ liệu JSON dễ đọc hơn.

- Dev Suite: hỗ trợ lập trình và phát triển web.
- Productivity Suite: hỗ trợ công việc và năng suất.
- Security Suite: hỗ trợ bảo mật.

## 2. Thiết lập quyền truy cập

Nên chọn **Site Access: On click**.

Lý do:
- Chỉ kích hoạt tiện ích khi cần.
- Hạn chế quyền truy cập website không cần thiết.
- Tăng khả năng kiểm soát quyền riêng tư.

---

# PHẦN C. HTTP REQUEST FLOW VÀ DEVTOOLS

## 1. Bốn giai đoạn khi truy cập website

1. **DNS Lookup:** Chuyển tên miền thành địa chỉ IP.
2. **TCP/TLS Connection:** Thiết lập kết nối với máy chủ và bảo mật bằng TLS.
3. **HTTP Request/Response:** Trình duyệt gửi yêu cầu và nhận phản hồi từ máy chủ.
4. **Rendering:** Trình duyệt xử lý HTML, CSS, JavaScript để hiển thị trang web.

## 2. Phân biệt HTTP Status Code

| Mã lỗi | Ý nghĩa | Cách xử lý |
|---|---|---|
| 404 Not Found | Không tìm thấy tài nguyên được yêu cầu | Kiểm tra URL và đường dẫn API |
| 500 Internal Server Error | Máy chủ gặp lỗi nội bộ | Kiểm tra log và xử lý phía Backend |

## 3. Công dụng 4 tab trong DevTools

| Tab | Công dụng |
|---|---|
| Elements | Kiểm tra và chỉnh sửa HTML, CSS |
| Console | Xem lỗi JavaScript và thông báo |
| Network | Theo dõi HTTP Request/Response |
| Application | Kiểm tra Cookies, Cache và Local Storage |

---

# PHẦN D. CACHE VÀ COOKIES

## 1. Website vẫn hiển thị CSS cũ sau khi nhấn F5

Nguyên nhân có thể do trình duyệt đang sử dụng CSS được lưu trong Cache.

**Cách xử lý:**

Nhấn tổ hợp phím:

`Ctrl + Shift + R`

Đây là thao tác Hard Reload, giúp trình duyệt tải lại tài nguyên thay vì sử dụng bản Cache thông thường.

## 2. Rủi ro khi Cookie thiếu HttpOnly

Nếu Cookie `session_id` không có thuộc tính `HttpOnly`, JavaScript có thể đọc Cookie thông qua `document.cookie`.

Nếu website tồn tại lỗ hổng XSS, kẻ tấn công có thể lợi dụng để lấy Cookie phiên đăng nhập và chiếm quyền sử dụng phiên đó.

**Giải pháp:** Thiết lập thuộc tính `HttpOnly` cho Cookie chứa thông tin phiên đăng nhập.

## 3. Đăng xuất nhưng vẫn giữ Cache

Thực hiện:

1. Mở DevTools bằng phím `F12`.
2. Chọn tab **Application**.
3. Chọn **Storage → Cookies**.
4. Chọn tên miền website.
5. Xóa riêng Cookie `session_id`.
6. Không chọn xóa toàn bộ dữ liệu trình duyệt.


---

# PHẦN E. INSPECT ELEMENT VÀ NETWORK DEBUGGING

## 1. Thay đổi màu nút bằng Inspect Element

Các bước thực hiện:

1. Mở website cần kiểm tra.
2. Nhấn `F12` để mở DevTools.
3. Chọn tab **Elements**.
4. Nhấn biểu tượng Inspect Element và chọn nút cần chỉnh sửa.
5. Trong phần **Styles**, tìm thuộc tính `background-color`.
6. Thay đổi màu để kiểm tra giao diện.


### 2. Quy trình kiểm tra API bị lỗi
**Bước 1: Identify – Xác định**
- Mở tab Network.
- Chọn yêu cầu API đang bị lỗi.

**Bước 2: Inspect – Kiểm tra**

- Kiểm tra URL.
- Kiểm tra Method (GET, POST, PUT, DELETE).
- Kiểm tra Status Code.

**Bước 3: Analyze – Phân tích**

- Kiểm tra Headers.
- Kiểm tra Payload.
- Kiểm tra Response để tìm nguyên nhân lỗi.

**Bước 4: Fix & Verify – Sửa và xác nhận**

- Báo lỗi và thông tin liên quan cho người phụ trách Backend.
- Kiểm tra lại yêu cầu API sau khi sửa.
- Xác nhận API hoạt động bình thường.

### 3. Sử dụng Network để kiểm tra API

- Chọn bộ lọc **Fetch/XHR** để chỉ hiển thị các yêu cầu API.
- Chọn **Disable cache** để tránh sử dụng dữ liệu Cache khi kiểm tra.
- Kiểm tra Status Code và Response của từng yêu cầu.


