# Bài 3 : Xây dựng Không gian Cộng tác Doanh nghiệp
## 1. VẤN ĐỀ:
Nhóm đang quản lý dự án bãi đỗ xe thông minh trên Messenger nên tin nhắn kỹ thuật, thông báo deadline và tin nhắn giải trí bị trộn lẫn với nhau. Điều này khiến thành viên dễ bỏ lỡ thông tin quan trọng, quên nhiệm vụ và mất tập trung khi làm việc.

Ngoài ra, việc yêu cầu mọi người trả lời ngay lập tức khiến lập trình viên bị gián đoạn trong quá trình viết code.
## 2. YÊU CẦU:
-   Thiết lập không gian cộng tác trên Lark hoặc Slack.    
-   Chia Channel theo từng mục đích để quản lý thông tin rõ ràng.    
-   Sử dụng Reply in Thread để tránh làm trôi tin nhắn chính. 
-   Áp dụng giao tiếp bất đồng bộ (Asynchronous Communication), không bắt buộc thành viên phải phản hồi ngay lập tức
 ## 3. CÁCH LÀM:
### A. Sơ đồ kiến trúc kênh
|Tên channel|Nội dung sử dụng|
|-|-|
|#general|Thông báo chung của dự án
|#announcements|Thông báo deadline, lịch họp và các mốc quan trọng
|#technical|Thảo luận về cảm biến, phần cứng và lập trình
|#bug-reports|Báo cáo lỗi và cách khắc phục.
|#task-progress|Cập nhật tiến độ và phân công công việc
|#random|Tán gẫu, chia sẻ meme và giải trí.
### B. Bản quy ước giao tiếp – 3 quy tắc vàng

Quy tắc 1: Không sử dụng No-Hello Trap

Không chỉ gửi những tin nhắn như “Chào mọi người”, “Có ai không?”. Hãy trình bày đầy đủ nội dung cần trao đổi ngay trong một tin nhắn.

Ví dụ: “Mình đang gặp lỗi cảm biến không gửi được dữ liệu lên hệ thống. Mọi người có thể hỗ trợ kiểm tra nguyên nhân không?”

Quy tắc 2: Hạn chế spam @all

Chỉ sử dụng `@all` khi có thông báo thực sự khẩn cấp hoặc ảnh hưởng đến toàn bộ nhóm. Các công việc thông thường chỉ cần tag đúng người phụ trách.

Quy tắc 3: Tôn trọng thời gian làm việc của nhau

Áp dụng Asynchronous Communication: không yêu cầu thành viên phải trả lời ngay lập tức. Người gửi cần ghi rõ nội dung, deadline và mức độ ưu tiên. Thành viên có thể phản hồi khi hoàn thành công việc đang làm hoặc trong khung giờ đã thống nhất.


