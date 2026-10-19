# Phần 1 – Hoàn thiện SRS bằng Heading Styles và Auto TOC

## 1.1. Khung tiêu đề SRS hoàn chỉnh
1. Giới thiệu dự án — Heading 1

1.1. Mục tiêu — Heading 2

Xây dựng hệ thống giúp quản lý thông tin sách và quy trình mượn, trả sách trong thư viện trường. Tự động hóa việc theo dõi phiếu mượn nhằm giảm sai sót và tiết kiệm thời gian.

1.2. Đối tượng sử dụng — Heading 2

Hệ thống phục vụ sinh viên, nhân viên thư viện và người quản trị. Mỗi nhóm người dùng được cấp quyền phù hợp với nhiệm vụ.

2. Chức năng hệ thống — Heading 1

Hệ thống cho phép tra cứu sách, tạo phiếu mượn và ghi nhận tình trạng mượn trả. Nhân viên thư viện có thể cập nhật thông tin sách, xác nhận trả sáchvà theo dõi các phiếu quá hạn.

2.1. Quản lý mượn sách — Heading 2

2.1.1. Luồng mượn sách qua thẻ sinh viên — Heading 3
Sinh vin xuất trình thẻ để hệ thống xác minh mã sinh viên và kiểm tra điều kiện mượn. Nếu hợp lệ, nhân viên ghi nhận sách, ngày mượn và tạo phiếu mượn.

2.2. Quản lý trả sách — Heading 2
Hệ thống ghi nhận ngày trả, cập nhật trạng thái phiếu và xác định các trường hợp quá hạn để nhân viên xử lý.

3. Yêu cầu bảo mật — Heading 1

Hệ thống phải yêu cầu xác thực trước khi cho phép người dùng truy cập các chức năng quản lý. Quyền truy cập dữ liệu phải được phân theo vai trò và chỉ cho phép người dùng thực hiện các thao tác được cấp quyền

### 1.2. Cách gán Heading và tạo mục lục

| Cấp tiêu đề | Các dòng áp dụng | Phím tắt |
|---|---|---|
| Heading 1 | Mục 1, 2, 3 | `Ctrl + Alt + 1` |
| Heading 2 | Mục 1.1, 1.2, 2.1, 2.2 | `Ctrl + Alt + 2` |
| Heading 3 | Mục 2.1.1 | `Ctrl + Alt + 3` |
Thao tác tạo Auto TOC:

1.  Đặt con trỏ ở đầu tài liệu, tạo một trang dành cho mục lục.
    
2.  Chọn References → Table of Contents → Automatic Table.
    
3.  Đặt các phần nội dung SRS sau mục lục.
    
4.  Thêm nội dung vào tài liệu để mục 3 chuyển sang trang sau.
    
5.  Nhấp chuột phải vào mục lục → Update Field → Update entire table.

# Phần 2 – Chuẩn hóa dữ liệu và AutoFilter

## 2.1. Xác định chính xác 3 lỗi

| Lỗi | Vị trí | Quy tắc bị vi phạm |
|---|---|---|
| 1. Gộp ô A1:E1 để làm tiêu đề lớn | Hàng 1 | Không gộp ô trong vùng dữ liệu; mỗi cột cần có tiêu đề riêng. |
| 2. Có một hàng trống hoàn toàn | Hàng 5 | Không để hàng trống xen giữa các bản ghi. |
| 3. Dòng “Tổng cộng” nằm xen giữa vùng dữ liệu | Hàng 6 | Không đặt dòng tổng kết trong vùng dữ liệu cần lọc và xử lý. |

Hàng 1 là tiêu đề trang trí, không phải bản ghi dữ liệu. Khi chuẩn hóa, hãy bỏ vùng gộp ô này khỏi bảng dữ liệu và đặt tên bảng ở phía trên nếu cần.

## 2.2. Bảng sau khi sửa

Sheet `PhieuMuon` nên có cấu trúc như sau:

| MSSV | Họ Tên | Mã Sách | Ngày Mượn | Tình Trạng |
|---|---|---|---|---|
| SV001 | Nguyễn Văn An | S001 | 01/10/2026 | Đang mượn |
| SV002 | Trần Thị Bình | S002 | 03/10/2026 | Quá hạn |
| SV003 | Lê Văn Cường | S003 | 10/10/2026 | Đã trả |
| SV004 | Phạm Thu Hà | S099 | 12/10/2026 | Đang mượn |

**Dòng tổng kết** được chuyển ra ngoài vùng dữ liệu, ví dụ:

`Tổng cộng: 4 phiếu`
Dòng tổng kết được chuyển ra ngoài vùng dữ liệu, chẳng hạn đặt tại hàng 7:

`Tổng cộng: 4 phiếu`

Như vậy, vùng dữ liệu liên tục từ hàng tiêu đề đến bản ghi cuối cùng. Khi bổ sung cột Tên Sách ở Phần 3, vùng bảng sẽ có thêm một cột.

## 2.3. Phân biệt Record và Field

-   Record (bản ghi): Một hàng dữ liệu đại diện cho một phiếu mượn. Ví dụ, hàng của `SV001` mượn sách `S001` là một Record.
    
-   Field (trường dữ liệu): Một cột biểu diễn một thuộc tính. Ví dụ, `MSSV`, `Mã Sách` và `Tình Trạng` là các Field.
    

Mẹo nhớ: Hàng = Record, cột = Field.

## 2.4. Bật AutoFilter và lọc phiếu quá hạn

1.  Chọn một ô bất kỳ trong bảng dữ liệu.
    
2.  Nhấn `Ctrl + Shift + L` để bật bộ lọc.
    
3.  Nhấp mũi tên lọc ở cột `Tình Trạng`.
    
4.  Bỏ chọn các giá trị khác, chỉ giữ `Quá hạn`.
    
5.  Nhấn OK.
 Kết quả chỉ còn một bản ghi:
 
| MSSV | Họ Tên | Mã Sách | Tình Trạng |
|---|---|---|---|
| SV002 | Trần Thị Bình | S002 | Quá hạn |
# Phần 3 – Nối dữ liệu bằng VLOOKUP

## 3.1. Công thức lấy Tên Sách

Giả sử trong Sheet `PhieuMuon`, cột C là `Mã Sách`, cột D là `Tên Sách`. Trong Sheet `DanhMucSach`, cột A là `Mã Sách`, cột B là `Tên Sách`.

Nhập công thức tại ô `D2`:

```
=VLOOKUP(C2,DanhMucSach!$A$2:$B$4,2,FALSE)
```

**Giải thích 4 tham số:**

| Tham số | Ý nghĩa |
|---|---|
| `C2` | Mã sách cần tìm |
| `DanhMucSach!$A$2:$B$4` | Vùng bảng tra cứu được cố định bằng `$` |
| `2` | Lấy kết quả ở cột thứ 2 của vùng tra cứu |
| `FALSE` | Tìm kiếm chính xác |
Kéo công thức xuống các hàng còn lại.

## 3.2. Mã S099 trả về lỗi gì?

Công thức VLOOKUP thông thường trả về `#N/A`, vì mã `S099` không tồn tại trong danh mục sách. Với chế độ `FALSE`, Excel không tìm thấy mã trùng khớp chính xác.

## 3.3. Bọc IFERROR để xử lý lỗi

Sử dụng công thức:

```
=IFERROR(VLOOKUP(C2,DanhMucSach!$A$2:$B$4,2,FALSE),"Không tìm thấy sách")
```

**Kết quả dự kiến:**

| Mã Sách | Tên Sách |
|---|---|
| S001 | Lập Trình C Căn Bản |
| S002 | Giải Tích 1 |
| S003 | Kỹ Năng Mềm |
| S099 | Không tìm thấy sách |

`IFERROR` giúp bảng dễ đọc hơn, nhưng không tự sửa dữ liệu sai. Với mã `S099`, cần kiểm tra lại mã hoặc bổ sung sách vào danh mục nếu đó là sách hợp lệ.

# Phần 4 – Thiết kế slide báo cáo tiến độ

## 4.1. Nội dung slide duy nhất

**BÁO CÁO TIẾN ĐỘ · HỆ THỐNG QUẢN LÝ THƯ VIỆN**

# 3/4 phiếu mượn khớp danh mục; mã S099 cần xác minh

### Các số liệu nổi bật

- **4 phiếu mượn**
- **3 mã sách hợp lệ**
- **1 mã sách chưa tìm thấy**

### Số phiếu theo tình trạng

| Tình trạng | Số phiếu |
|---|---:|
| Đang mượn | 2 |
| Quá hạn | 1 |
| Đã trả | 1 |

**Hành động tiếp theo:** Kiểm tra mã S099 hoặc bổ sung sách vào danh mục trước khi xác nhận phiếu.

### Vì sao chọn biểu đồ thanh (Bar Chart)?

- Dữ liệu có ba nhóm tình trạng: Đang mượn, Quá hạn và Đã trả.
- Biểu đồ thanh giúp so sánh số lượng giữa các nhóm nhanh chóng.
- Không chọn Line Chart vì dữ liệu không thể hiện xu hướng theo thời gian; không cần Flowchart vì mục tiêu là so sánh số liệu.

## 4.2. Áp dụng Rule 10/20/30

| Quy tắc | Áp dụng |
|---|---|
| 10 slides | Slide này chiếm 1/10 tổng số slide. |
| 20 minutes | Nếu phân bổ đều, dự kiến khoảng 2 phút/slide. |
| 30-point font | Ưu tiên cỡ chữ lớn, khoảng 30 pt cho nội dung chính khi bố cục cho phép; nhãn biểu đồ có thể nhỏ hơn để dễ trình bày. |

