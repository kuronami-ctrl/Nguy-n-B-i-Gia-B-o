# QUẢN LÝ BROWSER PROFILE VÀ BOOKMARK

## PHẦN 1. PHÂN TÍCH

### 1. So sánh Incognito Mode và Dedicated Profile

| Tiêu chí | Incognito Mode | Dedicated Profile |
|---|---|---|
| Mục đích | Duyệt web tạm thời | Sử dụng lâu dài cho từng mục đích |
| Cookies | Dữ liệu riêng trong phiên ẩn danh, bị xóa khi đóng toàn bộ cửa sổ ẩn danh | Được lưu riêng theo từng Profile |
| History | Không lưu lịch sử duyệt web vào lịch sử thông thường | Lưu lịch sử duyệt web riêng |
| Bookmarks | Có thể sử dụng nhưng không phù hợp để quản lý lâu dài | Lưu Bookmark riêng |
| Extensions | Không hoạt động mặc định, cần cho phép riêng | Có thể cài đặt và quản lý riêng |
| Lưu trữ | Dữ liệu phiên tạm thời, chủ yếu trong bộ nhớ và vùng lưu trữ tạm | Dữ liệu được lưu lâu dài trên ổ cứng |

### 2. Mô hình 3 Profile độc lập

Tạo 3 Profile trên Chrome:

| Profile | Mục đích | Dữ liệu sử dụng |
|---|---|---|
| Personal | Tài khoản cá nhân | Email, mạng xã hội, GitHub cá nhân |
| Work | Quản trị GreenLog | Portal công ty, Canvas LMS, GitHub công ty |
| Sandbox | Kiểm thử | Website thử nghiệm, API, công cụ lập trình |

**Lợi ích:**

- Mỗi Profile có Cookies, History, Bookmarks và Extensions riêng.
- Hạn chế nhầm lẫn giữa tài khoản cá nhân và tài khoản công việc.
- Khi trình chiếu ở Profile Work, dữ liệu cá nhân không xuất hiện trong cửa sổ trình duyệt đó.

Lưu ý: Profile giúp cách ly dữ liệu trình duyệt nhưng không đảm bảo triệt tiêu hoàn toàn mọi rủi ro đăng xuất. Máy chủ vẫn có thể giới hạn số phiên đăng nhập của cùng một tài khoản.

---

## PHẦN 2. TRIỂN KHAI

### 1. Tổ chức cây thư mục Bookmark

Đề xuất cấu trúc:

```text
BOOKMARKS
|
|-- 01_WORK
|   |-- GreenLog Portal
|   |-- Canvas LMS
|   |-- Email Cong Ty
|
|-- 02_DEVELOPMENT
|   |-- GitHub
|   |-- GitHub Documentation
|   |-- API Documentation
|
|-- 03_LEARNING
|   |-- W3Schools
|   |-- MDN Web Docs
|   |-- Stack Overflow
|
|-- 04_TOOLS
    |-- JSON Viewer
    |-- Google Translate
    |-- Developer Tools
```
### 2. Quy trình tạo Profile và Cloud Sync

Bước 1: Tạo Profile

1.  Mở trình duyệt Chrome.
    
2.  Nhấn biểu tượng Profile ở góc trên bên phải.
    
3.  Chọn Add Profile.
    
4.  Tạo lần lượt Personal, Work và Sandbox.
    
5.  Chọn màu sắc hoặc biểu tượng riêng để dễ phân biệt.
    

Bước 2: Tổ chức Bookmark

1.  Mở Profile Work.
    
2.  Nhấn `Ctrl + Shift + O` để mở Bookmark Manager.
    
3.  Tạo các thư mục theo cấu trúc phía trên.
    
4.  Lưu GitHub, Canvas LMS và Portal công ty vào đúng thư mục.
    

Bước 3: Bật Cloud Sync

1.  Đăng nhập tài khoản Google phù hợp vào Profile Work.
    
2.  Mở phần Settings.
    
3.  Chọn Sync and Google Services.
    
4.  Bật đồng bộ hóa Bookmark.
    
5.  Kiểm tra trạng thái đồng bộ.
    

Bước 4: Sử dụng khi đổi máy tính

1.  Mở Chrome trên máy tính mới.
    
2.  Đăng nhập đúng tài khoản Google của Profile Work.
    
3.  Bật đồng bộ hóa.
    
4.  Chờ Bookmark được khôi phục.
    

Lưu ý bảo mật:

-   Chỉ đồng bộ dữ liệu công việc bằng tài khoản được công ty cho phép.
    
-   Không bật đồng bộ Bookmark công việc vào Profile cá nhân.
    
-   Không sử dụng Cloud Sync trên máy tính công cộng.
    
-   Kiểm tra tài khoản đang đăng nhập trước khi trình chiếu.
## PHẦN 3. KIỂM THỬ

### 1. Tình huống sử dụng máy tính công cộng

Khi sử dụng máy tính công cộng, quản trị viên nên chọn Guest Profile thay vì đăng nhập vào Profile cá nhân hoặc Work.

### 2. Quy tắc sử dụng Guest Profile

1.  Mở Chrome.
    
2.  Nhấn biểu tượng Profile.
    
3.  Chọn Guest.
    
4.  Chỉ truy cập những website cần thiết.
    
5.  Không lưu mật khẩu trên máy tính công cộng.
    
6.  Không bật Cloud Sync hoặc đăng nhập tài khoản Google cá nhân.
    
7.  Không tải hoặc lưu tài liệu chứa thông tin nhạy cảm nếu không cần thiết.
    
8.  Đóng toàn bộ cửa sổ Guest sau khi sử dụng.
    

### 3. Vì sao nên dùng Guest Profile?

-   Không sử dụng dữ liệu đăng nhập của Profile chính.
    
-   Không lưu lịch sử duyệt web vào Profile thông thường.
    
-   Dữ liệu phiên Guest được xóa khi đóng toàn bộ cửa sổ Guest.
