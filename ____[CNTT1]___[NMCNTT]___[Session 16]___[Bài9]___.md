# PHẦN 1. PHÂN TÍCH KIẾN TRÚC ĐA PROFILE

## 1. Nguyên nhân lỗi Session Conflict

Khi nhiều người dùng chung một Profile Chrome, họ dùng chung dữ liệu Cookies lưu trong User Data Directory.

Cookies lưu thông tin phiên đăng nhập. Khi một người đăng nhập tài khoản khác, hệ thống có thể thu hồi phiên cũ, khiến người đang làm việc bị đăng xuất.

Giải pháp: Tạo các Profile riêng để tách biệt dữ liệu và phiên đăng nhập.
## 2. Thiết kế 3 Profile
|Profile|Mục đích|Màu nhận diện|Dữ liệu riêng|
|-|-|-|-|
|Work|Công việc CarePulse|Xanh dương|Cookies, History, Bookmarks, Extensions công việc
|Personal|Sử dụng cá nhân|Tím|Cookies, History, Bookmarks, Extensions cá nhân
|Sandbox/Test|Học tập, thử nghiệm|Cam|Cookies, History, Bookmarks, Extensions thử nghiệm
# PHẦN 2. THIẾT KẾ BOOKMARK VÀ QUY TRÌNH AN TOÀN

## 3. Cây thư mục Bookmark

Nhấn `Ctrl + Shift + O` để mở Bookmark Manager.
## 4. Kỹ thuật Favicon-Only

Thực hiện với 4 trang: CarePulse, Cổng BHYT, Dược thư và Google Dịch.

Các bước:

1.  Nhấn `Ctrl + D` để lưu Bookmark.
    
2.  Chọn lưu trên thanh Bookmarks Bar.
    
3.  Nhấn chuột phải vào Bookmark, chọn Edit.
    
4.  Xóa tên trang web, giữ lại địa chỉ.
    
5.  Nhấn Save.
    

Kết quả: Thanh Bookmark chỉ hiển thị biểu tượng, tiết kiệm diện tích và chứa được nhiều liên kết hơn.
## 5. Xử lý tình huống an ninh

Chọn Guest Profile

Khi có khách hoặc đoàn thanh tra mượn máy trong 30 phút, nên sử dụng Guest Profile thay vì Incognito.

Lý do:

-   Guest tạo phiên duyệt web tạm thời, tách biệt với Profile chính.    
-   Đóng cửa sổ Guest sẽ xóa dữ liệu duyệt web của phiên khách.  
-   Incognito vẫn hoạt động bên trong Profile hiện tại.  

Cảnh báo Cloud Sync:

Không bật Cloud Sync bằng tài khoản Google cá nhân trên máy trạm y tế vì có thể đồng bộ lịch sử, Bookmark và dữ liệu đăng nhập lên tài khoản cá nhân.

Cần đăng xuất tài khoản CarePulse và đóng hồ sơ bệnh nhân trước khi giao máy cho người khác.

