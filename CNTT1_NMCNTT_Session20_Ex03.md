# SESSION 19 – EXERCISE 03

Chủ đề: Khôi phục quyền truy cập AWS bằng Backup Codes

## 1. Phân tích tình huống

Trong quá trình làm việc, Lead Developer bị mất điện thoại chứa mã xác thực Google Authenticator. Do đó, không thể lấy mã OTP để đăng nhập vào tài khoản AWS.

Để giải quyết vấn đề, cần sử dụng Backup Codes (mã dự phòng) đã được tạo và lưu trữ an toàn từ trước.

Mục tiêu là khôi phục quyền truy cập AWS mà không để người nhặt được điện thoại có cơ hội xâm nhập tài khoản.

## 2. Báo cáo phân tích IPO

Thành phần

Nội dung

Input

Mã Backup Code dự phòng đã được lưu trữ an toàn trước đó.

Process

Nhập mã dự phòng để xác thực danh tính. Hệ thống kiểm tra tính hợp lệ và xác nhận quyền truy cập. Sau khi đăng nhập, thu hồi phương thức xác thực cũ, thiết lập MFA mới và tạo bộ Backup Codes mới.

Output

Khôi phục quyền truy cập AWS, thiết lập bảo mật mới và đảm bảo hệ thống an toàn.

## 3. Quy trình thực hiện

1.  Sử dụng thiết bị an toàn: Truy cập AWS từ máy tính đáng tin cậy.
    
2.  Nhập Backup Code: Sử dụng một mã dự phòng chưa từng được sử dụng để xác thực.
    
3.  Xác thực tài khoản: Hệ thống kiểm tra mã dự phòng có hợp lệ hay không.
    
4.  Thu hồi bảo mật cũ: Báo mất điện thoại, thu hồi phiên đăng nhập và phương thức MFA trên thiết bị đã mất theo quy trình của AWS.
    
5.  Thiết lập MFA mới: Cài đặt lại Google Authenticator trên thiết bị mới và liên kết với tài khoản AWS.
    
6.  Tạo Backup Codes mới: Thu hồi bộ mã dự phòng cũ và tạo bộ mã mới để sử dụng khi cần thiết.
    

Lưu ý: Mỗi Backup Code chỉ được sử dụng một lần. Không chia sẻ mã dự phòng cho người khác.

## 4. Tại sao không được lưu Backup Codes dưới dạng ảnh trong thư viện điện thoại?

Việc lưu Backup Codes dưới dạng ảnh trong thư viện điện thoại tiềm ẩn nhiều rủi ro bảo mật:

-   Dễ bị đánh cắp: Người nhặt được điện thoại có thể mở thư viện ảnh và tìm thấy mã dự phòng.
    
-   Đồng bộ đám mây: Ảnh có thể tự động đồng bộ lên Google Photos hoặc iCloud, làm tăng nguy cơ lộ thông tin nếu tài khoản đám mây bị xâm nhập.
    
-   Sao lưu không an toàn: Ảnh có thể xuất hiện trong các bản sao lưu hoặc được chia sẻ ngoài ý muốn.
    
-   Mất quyền kiểm soát: Kẻ xấu có thể sử dụng mã dự phòng để vượt qua bước xác thực MFA.
    

Giải pháp: Lưu Backup Codes trong trình quản lý mật khẩu có mã hóa hoặc bản giấy được cất giữ tại nơi an toàn, tách biệt với điện thoại.

## 5. Các biện pháp bảo mật bổ sung

-   Không sử dụng chung mật khẩu cho nhiều tài khoản.
    
-   Bật MFA để tăng cường bảo mật.
    
-   Không chia sẻ OTP và Backup Codes.
    
-   Kiểm tra lịch sử đăng nhập và các thiết bị đang được cấp quyền.
    
-   Thu hồi ngay các phiên đăng nhập đáng ngờ khi mất thiết bị.
