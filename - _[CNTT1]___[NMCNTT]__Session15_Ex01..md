# Bài 1 : Hệ thống Quản lý Tài liệu Dự án Doanh nghiệp
## 1. VẤN ĐỀ:
Bạn A chỉ lưu file thiết kế 3D trên ổ cứng máy tính (Local), không đồng bộ lên Cloud thường xuyên. Khi ổ cứng bị lỗi Bad Sector, file thiết kế bị hỏng. Bản gửi qua Zalo cũng hết hạn tải về.

Vấn đề chính: Dữ liệu không có bản sao lưu an toàn và không có phương án khôi phục khi xảy ra sự cố.
## 2. YÊU CẦU:
Bài toán cần giải quyết 3 yêu cầu:

-   **Hybrid Workflow:** Kết hợp lưu trữ trên máy tính (Local) và Cloud.
-   **Auto Sync:** Tự động đồng bộ file lên Cloud sau khi nhấn Ctrl + S.
-   **Version History:** Lưu lịch sử phiên bản để khôi phục bản vẽ cũ khi bản hiện tại bị lỗi.
## 3. GIẢI QUYẾT
**a. Thiết lập luồng dữ liệu**

```text
Designer chỉnh sửa file 3D
          ↓
     Nhấn Ctrl + S
          ↓
    Lưu trên Local SSD
          ↓
       Auto Sync
          ↓
      Cloud Storage
          ↓
      Version History
```

**b. Xử lý sự cố**

-   Khi mất Internet: File vẫn được lưu trên máy tính. Khi có mạng trở lại, phần mềm tiếp tục đồng bộ lên Cloud.    
-   Khi máy tính sập nguồn: Những thay đổi đã lưu thành công trên ổ cứng vẫn có thể được đồng bộ khi máy hoạt động trở lại. Thay đổi chưa lưu có thể bị mất.    
-   Khi file bị lỗi: Mở Version History, chọn phiên bản ổn định trước đó và khôi phục.   
-   Khi xảy ra xung đột phiên bản: Kiểm tra các bản khác nhau, so sánh nội dung và chọn hoặc kết hợp những thay đổi phù hợp trước khi lưu bản hoàn chỉnh.
    

**c. Ba bước thiết lập Auto Sync**
1.  Cài đặt Google Drive for desktop và đăng nhập tài khoản.    
2.  Tạo thư mục chứa file thiết kế 3D và bật đồng bộ tự động.    
3. Đưa thư mục đồng bộ vào google drive
    
