# BÀI TẬP: XÂY DỰNG QUY TRÌNH BÁO LỖI VÀ TÌM CÁCH KHẮC PHỤC

## 1. YÊU CẦU

- Xây dựng mẫu báo lỗi (Bug Report Template) gồm 4 nội dung:
  + Context: Hoàn cảnh xảy ra lỗi.
  + Expected: Kết quả mong muốn.
  + Actual: Kết quả thực tế.
  + Log: Thông báo lỗi.
- Đề xuất quy trình 3 bước tìm cách khắc phục:
  + Googling: Tìm kiếm trên Google.
  + Community Search: Tìm kiếm trong cộng đồng lập trình.
  + AI Translation: Nhờ AI giải thích lỗi bằng ngôn ngữ dễ hiểu.
- Giúp các thành viên tự tìm cách xử lý trước khi nhờ người khác hỗ trợ.

## 2. VẤN ĐỀ

Nhóm Startup thường xuyên gặp các lỗi khi làm việc như Docker không khởi động được hoặc hai chương trình sử dụng cùng một cổng.

Mỗi khi gặp lỗi, các thành viên thường nhắn tin liên tục vào nhóm chat mà không cung cấp đầy đủ thông tin.

Điều này dẫn đến:
- Thông tin lỗi bị trôi, khó tìm lại.
- Các thành viên hỏi đi hỏi lại cùng một vấn đề.
- Người hỗ trợ mất nhiều thời gian để tìm hiểu nguyên nhân.
- Nhóm làm việc kém hiệu quả.

Vì vậy, cần có một mẫu báo lỗi chung và quy trình tìm cách khắc phục trước khi nhờ hỗ trợ.

## 3. CÁCH LÀM

### A. Xây dựng mẫu Bug Report Template

Trước khi hỏi nhóm, mỗi thành viên phải điền đầy đủ 4 nội dung sau:

**MẪU BÁO LỖI**

- **1. Context (Hoàn cảnh):**
  - Đang sử dụng phần mềm nào?
  - Phiên bản bao nhiêu?
  - Đang thực hiện thao tác gì khi xảy ra lỗi?

- **2. Expected (Kết quả mong muốn):**
  - Tôi muốn phần mềm hoạt động như thế nào?

- **3. Actual (Kết quả thực tế):**
  - Phần mềm đã xảy ra lỗi gì?
  - Có hiện tượng gì bất thường?

- **4. Log (Thông báo lỗi):**
  - Sao chép thông báo lỗi từ màn hình hoặc Terminal.
  - Có thể đính kèm ảnh chụp màn hình.
  - Không gửi mật khẩu hoặc thông tin riêng tư.

**Ví dụ minh họa:**

- Context: Tôi đang sử dụng Docker trên Windows 11.
- Expected: Docker khởi động và chạy chương trình bình thường.
- Actual: Docker không thể khởi động.
- Log: `Port is already allocated`.

### B. Quy trình 3 bước tìm cách khắc phục

**Bước 1: Googling (Tìm kiếm trên Google)**

- Sao chép thông báo lỗi chính xác.
- Tìm kiếm bằng các từ khóa liên quan.
- Ưu tiên hướng dẫn từ trang chính thức của phần mềm.
- Kiểm tra xem cách sửa có phù hợp với máy tính đang sử dụng không.

**Bước 2: Community Search (Tìm kiếm trong cộng đồng)**

- Tìm lỗi trên StackOverflow hoặc GitHub Issues.
- Đọc những câu trả lời có nhiều lượt đồng tình.
- Kiểm tra ngày đăng và phiên bản phần mềm.
- Xem bình luận của những người đã thử cách sửa.
- Không làm theo hướng dẫn nếu chưa hiểu rõ tác dụng.

**Bước 3: AI Translation (Nhờ AI giải thích)**

- Sao chép thông báo lỗi và gửi cho AI.
- Cung cấp thông tin về hệ điều hành và phần mềm đang sử dụng.
- Yêu cầu AI giải thích nguyên nhân bằng từ ngữ dễ hiểu.
- Nhờ AI đề xuất các bước sửa lỗi an toàn.
- Kiểm tra lại câu trả lời trước khi thực hiện.

### C. Quy định khi nhờ người khác hỗ trợ

- Phải điền mẫu Bug Report Template trước khi hỏi.
- Phải thử tìm kiếm theo 3 bước trên.
- Nếu vẫn không giải quyết được, gửi báo lỗi vào đúng nhóm hỗ trợ.
- Khi đã sửa được lỗi, cần chia sẻ cách giải quyết để các thành viên khác tham khảo.

