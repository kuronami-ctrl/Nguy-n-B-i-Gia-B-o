## Phần 1. Phân tích

### 1. Những sai lầm của Nam

Sai lầm 1: Sử dụng Word (.docx) để lưu trữ tài liệu dự án trên GitHub.
-   Word là định dạng Rich Text, hỗ trợ định dạng văn bản phức tạp như phông chữ, màu sắc, bảng biểu, hình ảnh và bố cục.    
-   Tệp `.docx` có cấu trúc phức tạp, thường chứa nhiều thành phần XML, hình ảnh và dữ liệu định dạng được đóng gói trong một tệp nén.    
-   Git khó so sánh trực tiếp những thay đổi bên trong tệp Word như cách nó so sánh các dòng văn bản thông thường.    
-   Trong khi đó, Markdown (`.md`) là định dạng văn bản thuần có quy tắc cú pháp đơn giản, phù hợp để viết tài liệu dự án và quản lý bằng Git.
    

Sai lầm 2: Cho rằng Git có thể so sánh mọi loại tệp giống nhau.
-   Với tệp văn bản Markdown, Git có thể hiển thị cụ thể dòng nào được thêm, sửa hoặc xóa.    
-   Với tệp Word, Git thường không thể hiển thị nội dung thay đổi trực tiếp dưới dạng văn bản thông thường nếu chưa có công cụ chuyển đổi phù hợp.    
-   Vì vậy, khi nhiều thành viên cùng sửa tài liệu Word, việc theo dõi thay đổi và xử lý xung đột sẽ khó khăn hơn.
### 2. Tại sao Markdown an toàn và nhẹ hơn?
|Tiêu chí|Word|Markdown
|-|-|-
|bản chất|Định dạng Rich Text, có cấu trúc đóng gói phức tạp|Văn bản thuần
|Dung lượng|Thường lớn hơn khi có nhiều định dạng, hình ảnh|Thường nhỏ đối với tài liệu chỉ có văn bản
|Git Diff|Khó so sánh trực tiếp|Dễ theo dõi từng dòng thay đổi
|Git Merge|Có thể khó xử lý xung đột|Thường dễ hợp nhất các thay đổi không trùng dòng
|Khả năng đọc|Thường cần ứng dụng tương thích|Có thể đọc bằng trình soạn thảo văn bản
|Hiển thị trên GitHub|Thường cần tải xuống hoặc dùng công cụ xem tệp|Có thể hiển thị trực tiếp dưới dạng tài liệu đã định dạng
## Phần 2. Hoàn thiện

# Dự án GreenTech

## 1. Giới thiệu

GreenTech là dự án hướng đến việc ứng dụng công nghệ nhằm bảo vệ môi trường và thúc đẩy phát triển bền vững.

## 2. Mục tiêu
- Giảm thiểu tác động tiêu cực đến môi trường.
- Nâng cao ý thức bảo vệ môi trường.
- Ứng dụng công nghệ vào các giải pháp xanh.

## 3. Ý nghĩa
Dự án khuyến khích cộng đồng sử dụng công nghệ để xây dựng một môi trường sống xanh, sạch và bền vững hơn
  
