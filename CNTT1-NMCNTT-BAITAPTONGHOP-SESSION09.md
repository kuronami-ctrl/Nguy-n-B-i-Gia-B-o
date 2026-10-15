## Phần 1 – Khung sườn README

# 🎓 SmartCampus

SmartCampus là **ứng dụng di động** giúp sinh viên PTIT tra cứu *lịch học*, phòng học trống và nhận thông báo mới nhất từ nhà trường.

## ✨ Tính năng chính

- Tra cứu lịch học theo mã sinh viên.
  - Ghi chú: Sử dụng mã sinh viên để tra cứu lịch học.
- Xem danh sách phòng trống theo tòa nhà.

**Trang chủ CLB:** [CLB Lập trình PTIT](https://clblaptrinh.ptit.edu.vn)

![Logo dự án SmartCampus](https://tse4.mm.bing.net/th/id/OIP.s_4p38dgwm1h0assCh6ToQHaD9?r=0&rs=1&pid=ImgDetMain&o=7&rm=3)

> ⚠️ **Cảnh báo:** SmartCampus đang trong giai đoạn phát triển, chưa dùng cho mục đích chính thức.

---

## 🚀 Cài đặt dự án

```bash
abcfefg https://github.com/clb-lap-trinh/smartcampus.git
DTH install
DTH start
```

## 📋 Trạng thái phát triển

- [x] Tra cứu lịch học theo mã sinh viên.
- [x] Xem danh sách phòng trống theo tòa nhà.
- [ ] Phát triển thông báo đẩy (push notification).
- [ ] Phát triển đăng nhập bằng tài khoản trường.

## 🧰 Thư viện sử dụng

| Thư viện | Phiên bản | Mục đích |
|:---|:---:|---|
| React Native | 0.74 | Xây giao diện đa nền tảng iOS/Android |
| Axios | 1.6 | Gọi API lấy dữ liệu lịch học |

## 🔎 Lưu ý kỹ thuật

Khi viết tài liệu Markdown, dùng dấu gạch chéo ngược để hiển thị nguyên văn ký tự đặc biệt: `\*` sẽ hiển thị dấu \* thay vì dùng nó làm ký hiệu định dạng.

Kiểm tra các yêu cầu đã đáp ứng:
-   H1 và emoji: `# 🎓 SmartCampus`.
-   Đoạn mô tả có chữ đậm và chữ nghiêng.  
-   Danh sách có thứ tự lồng nhau với đúng hai dấu cách thụt lề. 
-   Hyperlink, Image, Blockquote và Horizontal Rule 
-   Code Block có khai báo `bash` và đúng 3 dòng lệnh được cung cấp  
-   Task List có 2 mục hoàn thành và 2 mục đang làm.  
-   Bảng có dòng phân cách và cột phiên bản căn giữa bằng `:---:`.   
-   Emoji shortcode `:rocket:` ở tiêu đề phụ.   
-   Ký tự escape `\*`.
## Phần 2 – Hoàn thiện phần kỹ thuật

Trong README ở trên, các phần kỹ thuật đã được tích hợp đầy đủ. Riêng emoji shortcode, GitHub hỗ trợ `:rocket:` và sẽ hiển thị thành 🚀 khi render. Ký tự escape `\*` cho phép hiển thị dấu sao nguyên văn thay vì dùng nó để định dạng chữ.

## Phần 3 – Hỏi AI và lưu tài liệu về API

### 1. Viết Prompt theo công thức 3 phần
## Tôi là ai / Bối cảnh

Tôi là sinh viên năm nhất PTIT, đang học môn IT. Tôi chưa có nhiều kiến thức về lập trình và đang tìm hiểu các khái niệm kỹ thuật cơ bản.

## Chủ đề / Nội dung cần xử lý
Giải thích thuật ngữ API (Application Programming Interface) trong phát triển phần mềm.
## Yêu cầu
-   Dùng ngôn ngữ đời thường, dễ hiểu cho người mới học.
-   So sánh API với một vật dụng quen thuộc trong cuộc sống.  
-   Đưa ra một ví dụ thực tế về ứng dụng tra cứu lịch học SmartCampus sử dụng API.
-   Trình bày ngắn gọn, có tiêu đề và gạch đầu dòng.   
-   Kết thúc bằng một câu tóm tắt dễ ghi nhớ.
    

## Không cần
-   Không sử dụng thuật ngữ chuyên ngành phức tạp nếu chưa giải thích.
-   Không đưa mã nguồn lập trình dài.
### 2. Câu trả lời mẫu từ AI

# API là gì?

API (Application Programming Interface) là giao diện cho phép các phần mềm giao tiếp và trao đổi dữ liệu với nhau.
Hãy tưởng tượng API giống như một người phục vụ trong nhà hàng:
-   Bạn là khách hàng, muốn gọi một món ăn.    
-   Người phục vụ nhận yêu cầu và chuyển đến nhà bếp.   
-   Nhà bếp chuẩn bị món ăn rồi gửi kết quả lại qua người phục vụ.   

Trong phần mềm, API đóng vai trò trung gian tương tự, giúp một ứng dụng gửi yêu cầu đến hệ thống khác và nhận dữ liệu trả về.

Ví dụ với SmartCampus:
-   Ứng dụng gửi yêu cầu tra cứu lịch học theo mã sinh viên thông qua API. 
-   Hệ thống xử lý yêu cầu và trả về dữ liệu lịch học. 
-   Ứng dụng hiển thị lịch học cho sinh viên. 

Ghi nhớ: API là cầu nối giúp các phần mềm trao đổi dữ liệu và sử dụng chức năng của nhau.

### 3. Tóm tắt bằng chiến lược đọc 3 bước
1.  Scan Heading: Xác định chủ đề chính là định nghĩa API và ví dụ SmartCampus.  
2.  Đọc phần chữ đậm: Ghi nhớ API là giao diện giúp phần mềm giao tiếp với nhau.  
3.  Xem Bullet List: Nắm trình tự gửi yêu cầu, hệ thống xử lý và trả dữ liệu.    Bản tóm tắt tối đa 3 câu
```
- API là giao diện cho phép các phần mềm giao tiếp và trao đổi dữ  liệu với nhau. 
- Có thể hình dung API như người phục vụ tiếp nhận yêu cầu và chuyển kết quả giữa khách hàng với nhà bếp. 
- Với SmartCampus, API giúp ứng dụng gửi yêu cầu tra cứu lịch học và nhận dữ liệu từ hệ thống.
```
### 4. Lưu câu trả lời thành `api_giai_thich.md`
Thực hiện theo quy trình 4 bước:
1.  Tạo tài liệu: Mở [StackEdit](https://stackedit.io/app), tạo một tài liệu Markdown mới.
2.  Nhập nội dung: Sao chép toàn bộ câu trả lời API ở bước 2, bao gồm tiêu đề, danh sách và phần ví dụ.
3.  Kiểm tra hiển thị: Xem trước tài liệu, kiểm tra tiêu đề, chữ đậm và danh sách có hiển thị đúng không.
4.  Xuất file: Mở menu StackEdit, chọn chức năng xuất tài liệu ra đĩa (Export to disk), chọn Markdown nếu có tùy chọn định dạng, rồi lưu tên `api_giai_thich.md`.    
Sau khi lưu, kiểm tra phần mở rộng phải là `.md`, không phải `.txt` hoặc `.docx`.
## Phần 4 – Bẫy cú pháp

### 1. Chỉ ra chính xác 2 lỗi

##### Lỗi 1: Bảng thiếu dòng phân cách giữa tiêu đề và dữ liệu
Sau hàng tiêu đề phải có dòng phân cách, ví dụ `|---|---|`, để Markdown nhận diện cấu trúc bảng
##### Lỗi 2: Task List thiếu dấu cách sau dấu gạch ngang
Cú pháp đúng cần có dấu cách giữa `-` và `[x]` hoặc `[ ]`: `- [x]` và `- [ ]`
### 2. Viết lại đoạn Markdown đúng chuẩn

| Tính năng | Trạng thái |
|---|---|
| Tra cứu lịch học | Xong |
| Push notification | Đang làm |

- [x] Tra cứu lịch học
- [ ] Push notification

