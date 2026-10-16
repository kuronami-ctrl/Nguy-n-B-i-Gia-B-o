# Phần 1. Phân tích bài toán

Trong hệ thống GreenTech – chuyên gia nông nghiệp AI, dữ liệu câu trả lời có thể được gửi dưới dạng Markdown hoặc HTML. Markdown thường ngắn gọn hơn khi biểu diễn những nội dung đơn giản, nhờ vậy có thể giảm lượng văn bản cần đưa vào mô hình AI xử lý

## 1. Token của AI là gì
Token là đơn vị mà mô hình AI sử dụng để chia nhỏ văn bản khi xử lý. 
## 2. Vì sao Markdown có thể giúp tiết kiệm chi phí?

-   Ít văn bản định dạng hơn: Với tiêu đề, danh sách và chữ in đậm đơn giản, Markdown thường cần ít ký tự hơn HTML
-   Giảm lượng token đầu vào: Nếu cách mã hóa thực tế cũng tạo ra ít token hơn, hệ thống có thể giảm chi phí xử lý đầu vào  
-   Có thể giảm độ trễ: Ít token đầu vào có thể giúp giảm thời gian xử lý, nhưng tốc độ còn phụ thuộc vào mô hình, độ dài câu trả lời và hạ tầng    
-   Dễ đọc đối với con người: Markdown có cú pháp gần với văn bản thông thường, ví dụ `**độ ẩm**` dễ nhận ra là phần cần nhấn mạnh
 # Phần 2. So sánh và đánh giá Markdown với HTML
|Tiêu chí|Markdown|HTML
|-|-|-
|Độ dài cú pháp|Thường ngắn hơn|Thường dài hơn do có thẻ mở và đóng
|Độ dễ hiểu với người đọc|Cao, gần như giống văn bản thông thường|Thấp hơn khi có thẻ lồng nhau
|Tiêu đề|## Tiêu đề (kí tự ngắn hơn)|h2>Tiêu đề<h2 (kí tự dài hơn)
|Kiểm soát giao diện chi tiết|Hạn chế|Linh hoạt hơn khi kết hợp CSS
|Phù hợp|README,nội dung AI gửi,tài liệu|Trang web, giao diện,và cấu trúc HTML chi tiết
## Phần 3. Giải pháp tối ưu cho GreenTech
Dùng Markdown làm định dạng trao đổi nội dung chính với AI, và chỉ chuyển sang HTML khi cần hiển thị trên giao diện web	
### Lý do lựa chọn

1.  Tiết kiệm tài nguyên: Markdown thường gọn hơn HTML khi biểu diễn cùng một cấu trúc đơn giản, giúp giảm token nếu bộ mã hóa thực tế xác nhận điều đó    
2.  Dễ bảo trì: Nhân viên có thể đọc và chỉnh sửa tài liệu Markdown mà không phải xử lý nhiều thẻ HTML    
3.  Dễ trình bày: Ứng dụng có thể chuyển Markdown thành giao diện có tiêu đề, danh sách, bảng và chữ in đậm   
4.  Vẫn tận dụng HTML khi cần: Những thành phần giao diện phức tạp có thể được xây dựng bằng HTML và CSS ở bước hiển thị, thay vì gửi nguyên khối HTML dài vào lời nhắc AI
