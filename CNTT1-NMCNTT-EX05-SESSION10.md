## 1. Phần 1 — Phân tích
-   Input: Dữ liệu từ cảm biến nhiệt độ, độ ẩm và cấu hình ngưỡng tưới.    
-   Output: Thông tin môi trường, lệnh điều khiển máy bơm và nhật ký hệ thống.    
-   Sơ đồ phần cứng: Cảm biến → Raspberry Pi/SoC → Mạch relay → Máy bơm.
    

## 2. Phần 2 — Triển khai README.md

File README cần có đủ các mục:
1.  Tên dự án kèm emoji 🚀 và mô tả.    
2.  Sơ đồ hệ thống có hình ảnh và Alt Text.    
3.  Hướng dẫn cài đặt bằng Code Block.   
4.  Tính năng bằng Task List.    
5.  Bảng thông số thiết bị bằng Table.    
6.  Chu trình Fetch–Decode–Execute bằng Blockquote.    
7.  Mô hình kim tự tháp DIKW.    
8.  Mục lưu ý vận hành và kiểm tra trước khi bàn giao.
    

## 3. Phần 3 — Kiểm thử khi RAM đầy

Trong mục Lưu ý của README, cần hướng dẫn:
-   Dùng `free -h` và `top` để kiểm tra RAM.    
-   Ghi nhật ký trực tiếp vào tệp, tránh giữ toàn bộ dữ liệu trong RAM.    
-   Thiết lập xoay vòng nhật ký (log rotation).    
-   Sao lưu trước khi xóa nhật ký cũ.    
-   Dùng `df -h` để kiểm tra dung lượng ổ đĩa.    
-   Không tùy tiện xóa tệp hệ thống hoặc kết thúc tiến trình quan trọng.
