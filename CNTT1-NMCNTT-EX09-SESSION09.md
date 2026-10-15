## Phần 1. Phân tích và thiết kế giải pháp

### 1. Phân tích bài toán theo mô hình I/O

Mô hình I/O gồm Input (đầu vào), quá trình xử lý và Output (đầu ra).
|Thành phần|Nội dung
|-|-|-
|Input|Tên CLB, mô tả hoạt động, danh sách các ban, tên trưởng ban, email liên hệ, quy trình gia nhập, nhiệm vụ thành viên mới, deadline và quy tắc ứng xử
|Xử lý|Sử dụng cú pháp Markdown để tổ chức nội dung thành tiêu đề, bảng, danh sách, khối mã lệnh, checklist và trích dẫn
|Output|File `README.md` hoàn chỉnh, hiển thị rõ ràng trên GitHub, giúp thành viên mới dễ đọc, dễ làm theo và dễ cập nhật
### 2. Đề xuất giải pháp

Tổ chức file `README.md` thành 5 phần theo yêu cầu:
|Phần|Cú Pháp Markdown|Mục đích
|-|-|-
|1. Giới thiệu CLB|`#`, `##`, `**...**`|Tạo tiêu đề phân cấp và làm nổi bật thông tin
|2. Danh sách Ban|Bảng `\|`|Trình bày tên ban, trưởng ban và email liên hệ
|3. Hướng dẫn gia nhập|Danh sách `1.`, khối mã ` ```bash`|Hướng dẫn các bước và lệnh Git
|4. Checklist|`- [x]`, `- [ ]`|Phân biệt nhiệm vụ đã hoàn thành và cần thực hiện
|5. Lưu ý quan trọng|>|Nhấn mạnh deadline và quy tắc ứng xử
### 3. Thiết kế các bước thực hiện

1.  Thu thập và xác định nội dung cần đưa vào tài liệu.
2.  Tạo thư mục dự án và file `README.md`.
3.  Viết nội dung theo 5 phần đã thiết kế, sử dụng đúng cú pháp Markdown.
4.  Kiểm tra bảng, email `mailto:`, các lệnh Git, checklist và nội dung trích dẫn.
5.  Xem trước cách hiển thị Markdown, sửa lỗi cú pháp và kiểm tra liên kết.
6.  Đưa file lên GitHub để các thành viên truy cập và cập nhật khi cần
## Phần 2. Triển khai và chống lỗi

### 4. Source file `README.md` hoàn chỉnh:

# CLB Lập trình PTIT

## 1. Giới thiệu CLB

CLB Lập trình PTIT là cộng đồng dành cho sinh viên yêu thích công nghệ thông tin, lập trình và phát triển phần mềm.

**Điểm nổi bật:** Học tập thực hành, làm dự án thực tế và hỗ trợ nhau cùng tiến bộ.

## 2. Danh sách Ban

| Tên Ban | Trưởng Ban | Liên hệ
|-|-|-
|Ban Kỹ thuật|NguyễN Bùi Gia Bảo|[GiaBao@ptit.edu.vn](mailto:GiaBao@ptit.edu.vn)|
|Ban Truyền thông|Nguyễn Bùi Gia Bảo|[GiaBao@ptit.edu.vn](mailto:GiaBao@ptit.edu.vn)|
|Ban Sự kiện|Nguyễn Bùi Gia Bảo|[GiaBao@ptit.edu.vn](mailto:GiaBao@ptit.edu.vn)|

## 3. Hướng dẫn Gia nhập

1. Đăng ký tham gia CLB theo thông báo tuyển thành viên.
2. Cài đặt Git trên máy tính.
3. Mở Terminal và sao chép kho mã nguồn của CLB:

   ```bash
   git clone https://github.com/example/ptit-programming-club.git
   ```

4. Di chuyển vào thư mục dự án:

   ```bash
   cd ptit-programming-club
   ```

5. Đọc tài liệu, hoàn thành checklist và liên hệ Ban Kỹ thuật nếu cần hỗ trợ.

## 4. Checklist Nhiệm vụ Thành viên Mới

- [x] Đọc nội quy CLB.
- [x] Tham gia nhóm trao đổi chính thức.
- [x] Hoàn thiện thông tin thành viên.
- [ ] Cài đặt Git và trình soạn thảo mã nguồn.
- [ ] Đọc hướng dẫn đóng góp mã nguồn.
- [ ] Tham gia buổi sinh hoạt đầu tiên.

## 5. Lưu ý quan trọng

> **Deadline:** Hoàn thành các nhiệm vụ onboarding trong vòng 7 ngày kể từ ngày gia nhập CLB.
>
> **Quy tắc ứng xử:** Tôn trọng mọi thành viên, giao tiếp lịch sự, không chia sẻ thông tin nội bộ khi chưa được phép và chủ động báo cáo khi gặp khó khăn.
### 5. Trả lời hai bẫy dữ liệu

Bẫy 1: Vì sao email phải là liên kết `mailto:`?
Cú pháp đúng:
```
[GiaBao@ptit.edu.vn](mailto:GiaBao@ptit.edu.vn)
```
-   Phần trong ngoặc vuông là nội dung hiển thị.
-   Phần trong ngoặc tròn bắt đầu bằng `mailto:` để tạo liên kết mở ứng dụng email khi người dùng bấm vào.
-   Nếu chỉ viết `GiaBao@ptit.edu.vn`, địa chỉ có thể được hiển thị như văn bản thông thường và không đảm bảo là liên kết có thể bấm.

Bẫy 2: Điều gì xảy ra khi thành viên dán URL không hợp lệ?

Có ba trường hợp thường gặp:
-   URL sai cú pháp: Markdown có thể không tạo được liên kết bấm được.
-   URL đúng cú pháp nhưng không tồn tại: Liên kết vẫn có thể hiển thị và khi bấm có thể dẫn đến trang lỗi hoặc trang không tìm thấy.
-   URL trỏ nhầm địa chỉ: Người dùng có thể bị chuyển đến một trang không mong muốn
.
