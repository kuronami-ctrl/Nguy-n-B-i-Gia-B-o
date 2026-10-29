
# Session14_Ex01 – Local Storage vs Cloud Storage

## Phần 1. Phân tích rủi ro dữ liệu

Nam lưu code trên máy tính cá nhân và tạo nhiều file như `main_v1.py`, `main_v2_final.py`. Khi Nam xóa nhầm đoạn code quan trọng trong file `final.py` rồi nhấn `Ctrl + S`, nội dung cũ đã bị ghi đè.

Các rủi ro Nam đang gặp phải:

1.  **Mất dữ liệu:** Nếu không có bản sao hoặc lịch sử phiên bản chứa đoạn code cũ, Nam có thể không khôi phục được dữ liệu.
    
2.  **Rủi ro hỏng thiết bị:** Code chỉ lưu trên máy cá nhân. Nếu máy tính hoặc ổ cứng gặp sự cố, dữ liệu có thể bị mất.
    
3.  **Xung đột phiên bản:** Có nhiều file với tên gần giống nhau khiến Nam và các thành viên dễ nhầm lẫn giữa bản cũ và bản mới.
    
4.  **Thiếu lịch sử chỉnh sửa:** Việc lưu nhiều file thủ công không giúp Nam dễ dàng xác định và khôi phục trạng thái code trước khi xảy ra lỗi.
    

**Kết luận:** Lưu nhiều file trên cùng một máy tính không đảm bảo an toàn dữ liệu. Nam cần kết hợp lưu trữ đám mây và quản lý phiên bản.

## Phần 2. Thiết lập Hybrid Workflow

Nam nên kết hợp Local Storage, Cloud Storage và GitHub theo quy trình sau:

### Bước 1. Lưu code trên máy tính

Nam tiếp tục viết và chạy thử code trên máy cá nhân bằng VS Code.

### Bước 2. Đồng bộ code lên Cloud Storage

Nam lưu thư mục dự án trong OneDrive và bật đồng bộ. Sau khi đồng bộ hoàn tất, cần kiểm tra file đã xuất hiện trên OneDrive trực tuyến.

### Bước 3. Khôi phục bằng Version History

Khi vô tình xóa code và nhấn `Ctrl + S`, Nam thực hiện:

1.  Mở OneDrive trên trình duyệt.
    
2.  Tìm file `final.py`.
    
3.  Chọn **Version history**.
    
4.  Chọn phiên bản trước khi xảy ra lỗi.
    
5.  Chọn **Restore** để khôi phục phiên bản cũ.
    

Cách này chỉ thực hiện được khi phiên bản cần khôi phục đã được lưu và vẫn còn trong lịch sử.

### Bước 4. Quản lý code bằng GitHub


### Bước 4. Quản lý code bằng GitHub

Nam sử dụng Git để lưu lại các phiên bản code quan trọng.

```
git add .
git commit -m "Luu code"
```

-   `git add .`: Chọn các file cần lưu.
    
-   `git commit -m "Luu code"`: Lưu phiên bản code vào lịch sử Git.
    

Sau đó, Nam sử dụng GitHub để lưu trữ code trực tuyến và hỗ trợ cộng tác nhóm.

Nhờ đó, Nam có thể xem lại lịch sử commit và khôi phục code từ một phiên bản đã lưu khi cần.

