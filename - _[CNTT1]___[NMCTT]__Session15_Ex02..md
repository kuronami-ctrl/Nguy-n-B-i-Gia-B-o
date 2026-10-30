# Bài 2 : Quản lý Quyền truy cập Báo cáo Tài chính
## 1. VẤN ĐỀ:
Startup đang lưu danh sách CV ứng viên, trong đó có những thông tin nhạy cảm:
-   Số điện thoại (SĐT).
-   Mức lương kỳ vọng.   
-   Thông tin cá nhân trong CV.   

Trưởng phòng nhân sự muốn chia sẻ tài liệu cho các trưởng bộ phận để xem và nhận xét. Tuy nhiên, một nhân viên đã vô tình gửi đường link với quyền Editor cho ứng viên bên ngoài.
Vấn đề chính:
1.  Cấp quyền truy cập không đúng đối tượng.    
2.  Người bên ngoài có thể chỉnh sửa dữ liệu gốc.    
3.  Nguy cơ rò rỉ thông tin cá nhân và mức lương ứng viên.    
4.  Chưa có quy trình kiểm tra và thu hồi quyền truy cập.
## 2. YÊU CẦU:
Có 3 yêu cầu chính:
|Yêu cầu|Ý nghĩa|
|-|-|
|Phân quyền Viewer/commenter/editer|Xác định ai được xem, nhận xét và chỉnh sửa
|Quy tắc Cờ Đỏ Bảo mật|Kiểm tra kỹ đối tượng và phạm vi chia sẻ trước khi cấp quyền
|Access Audit log|Kiểm tra lịch sử truy cập và hoạt động chia sẻ để phát hiện bất thường
## 3. Cách làm, hướng đi và gaiir quyết
### **A. Thiết kế bảng phân quyền**
|Đối tợng| Mức quyền|Lý do|
|-|-|-|
|Trờng phòng nhân sự|Chủ sở hữu|quản lí và chỉnh sửa danh sách ứng viên
|Các trưởng bộ phận|Commenter|Được nhận xét, đề xuất nhưng không sửa trực tiếp dữ liệu gốc
|Nhân viên không liên quan|Viewer|khồn được truy cập tài liệu|
|Ứng viên bên ngoài|Restricted|không đuược xem ứng viên của công ty
|HR|editer|Chỉnh sửa
### **B. Sử dụng Suggesting Mode**

-   Mở file danh sách ứng viên bằng Google Docs nếu tài liệu tương thích.
-   Chuyển chế độ chỉnh sửa sang Suggesting.    
-   Trưởng bộ phận đưa ra đề xuất thay đổi.
-   Trưởng phòng nhân sự xem xét và chấp nhận hoặc từ chối đề xuất
### **C. Xử lý sự cố trong 3 bước**

Bước 1

Thu hồi quyền ngay lập tức
-   Mở phần Share của file.    
-   Xóa email ứng viên khỏi danh sách người được chia sẻ.    
-   Chuyển phạm vi `Anyone with the link` về `Restricted`.    
-   Kiểm tra và thu hồi các liên kết chia sẻ không cần thiết

Bước 2

Kiểm tra Access Audit Log

-   Kiểm tra lịch sử chia sẻ và truy cập.   
-   Xác định tài khoản bên ngoài đã truy cập hay chưa.
-   Kiểm tra hoạt động tải xuống, chỉnh sửa hoặc sao chép nếu hệ thống có ghi nhận.    
-   Lưu lại thông tin để báo cáo sự cố.

Bước 3
Khắc phục và tăng cường bảo mật
-   Kiểm tra nội dung file và khôi phục phiên bản nếu bị chỉnh sửa.    
-   Báo cáo sự cố cho trưởng phòng nhân sự và bộ phận quản trị.    
-   Thiết lập lại quyền Viewer, Commenter, Editor đúng đối tượng.    
-   Kiểm tra lại quyền truy cập định kỳ.
