# Phần 1. Phân tích lỗi cú pháp Markdown

Đoạn mã ban đầu có ít nhất 4 lỗi cần sửa:
|Lỗi|Nguyên nhân|Cách sửa
|-|-|-
|1. Nhảy cấp tiêu đề|Dùng `###` (H3) ngay sau H1, bỏ qua H2|Đổi `###` thành `##` để tạo H2
|2. Cấu trúc tiêu đề chưa hợp lý|Nếu `# Lợi ích của rau sạch` và `### Danh sách các loại rau` là hai tiêu đề cùng cấp nội dung chính thì thứ bậc bị sai|Dùng một H1 chính, các mục bên dưới dùng H2, H3 theo thứ tự
|3. Sai cú pháp liên kết ảnh|`[Logo Dự án](https://greentech.vn/logo.png)` không hiển thị ảnh, chỉ tạo liên kết có chữ|Dùng `![Logo Dự án](https://greentech.vn/logo.png)`
|4. Chưa in đậm|`*Rất quan trọng*` chỉ tạo chữ in nghiêng|Dùng `**rất quan trọng**` để in đậm
# Phần 2. Hoàn thiện đoạn mã Markdown


# Lợi ích của rau sạch

## Danh sách các loại rau

![Logo Dự án](https://dalatfarm.net/wp-content/uploads/2021/07/combo-rau-cu-tuy-chon.jpg)

**Rất quan trọng**

