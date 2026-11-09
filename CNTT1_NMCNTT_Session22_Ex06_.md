# BÀI TẬP: XỬ LÝ LỖI QUYỀN TRUY CẬP KHI ĐẨY CODE LÊN GITHUB

## 1. YÊU CẦU

- Sử dụng công thức Prompt 3 thành phần để hỏi AI về lỗi.
- Hiểu nguyên nhân xuất hiện lỗi `Permission denied`.
- Thử cách mở Terminal bằng quyền Administrator nếu cần thiết.
- Chụp ảnh màn hình minh họa, làm rõ lỗi và che thông tin cá nhân.
- Nếu vẫn không sửa được, soạn tin nhắn nhờ giảng viên hỗ trợ theo mẫu báo lỗi.

## 2. VẤN ĐỀ

Khi đang đẩy code lên GitHub để nộp bài đúng hạn, Terminal hiển thị thông báo:

`error: open(".git/FETCH_HEAD"): Permission denied`

Điều này có nghĩa là Git không thể mở hoặc ghi dữ liệu vào tệp `FETCH_HEAD` trong thư mục `.git` vì không có quyền truy cập phù hợp.

Nguyên nhân có thể là:
- Tài khoản hiện tại không có quyền truy cập tệp.
- Tệp đang được một chương trình khác sử dụng.
- Quyền truy cập của thư mục dự án bị thay đổi.

Nếu cứ chạy lại lệnh mà không tìm hiểu nguyên nhân thì lỗi có thể tiếp tục xuất hiện.

## 3. CÁCH LÀM

### A. Sử dụng Prompt 3 thành phần để hỏi AI

Công thức Prompt gồm 3 phần:

- Context (Bối cảnh): Cung cấp thông tin về máy tính và công việc đang làm.
- Error (Lỗi): Gửi chính xác thông báo lỗi.
- Request (Yêu cầu): Nói rõ muốn AI giải thích và hướng dẫn điều gì.

**Prompt mẫu:**

Tôi đang sử dụng Windows 11 và Visual Studio Code để làm bài tập lập trình. Tôi đang muốn đẩy code từ máy tính lên GitHub nhưng Terminal xuất hiện lỗi:

`error: open(".git/FETCH_HEAD"): Permission denied`

Tôi đã thử chạy lại lệnh nhưng vẫn không được.

Hãy giải thích nguyên nhân lỗi bằng ngôn ngữ đơn giản, dễ hiểu cho sinh viên năm nhất. Sau đó hướng dẫn tôi từng bước kiểm tra và sửa lỗi an toàn. Không đưa ra những lệnh xóa dữ liệu hoặc thay đổi hệ thống khi chưa giải thích rõ tác dụng.

### B. Thử mở chương trình bằng quyền Administrator

Nếu đã kiểm tra và xác định có vấn đề về quyền truy cập, có thể thử cách sau:

**Bước 1:** Đóng Visual Studio Code.

**Bước 2:** Tìm biểu tượng Visual Studio Code trên màn hình máy tính.

**Bước 3:** Nhấn chuột phải vào biểu tượng và chọn `Run as administrator`.

**Bước 4:** Mở lại thư mục dự án đang làm.

**Bước 5:** Mở Terminal và thử lại thao tác Git trước đó.

**Bước 6:** Kiểm tra xem lỗi còn xuất hiện hay không.

Lưu ý:
- Chỉ thử cách này với dự án và phần mềm đáng tin cậy.
- Không sử dụng quyền Administrator cho mọi thao tác thông thường.
- Nếu vẫn lỗi, đóng chương trình và tiếp tục kiểm tra quyền truy cập thư mục `.git`.
- Không tự ý xóa thư mục `.git` vì đây là nơi lưu thông tin quản lý dự án Git.

### C. Chụp ảnh màn hình minh họa

Thực hiện theo các bước:

1. Mở Terminal và hiển thị thông báo lỗi.
2. Nhấn `Windows + Shift + S` để chụp màn hình.
3. Khoanh vùng dòng thông báo `Permission denied`.
4. Chụp thêm màn hình thể hiện thao tác mở chương trình bằng quyền Administrator và kết quả sau khi thử lại.
5. Che tên tài khoản, địa chỉ email, đường dẫn riêng tư hoặc thông tin đăng nhập nếu xuất hiện.

Đặt tên ảnh:
- `error-permission.png`
- `run-as-administrator.png`
- `result-after-fix.png`

Lưu ý: Cần tự chụp ảnh trên máy tính thực tế, không sử dụng ảnh minh họa thay cho kết quả thực hiện.

### D. Soạn tin nhắn nhờ giảng viên hỗ trợ

Nếu đã thử các bước trên nhưng vẫn không khắc phục được, tôi sẽ gửi báo lỗi theo 4 nội dung:

- Context: Hoàn cảnh xảy ra lỗi.
- Expected: Kết quả mong muốn.
- Actual: Kết quả thực tế.
- Log: Thông báo lỗi cụ thể.

