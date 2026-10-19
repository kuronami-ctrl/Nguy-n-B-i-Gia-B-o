## Phần 1. Phân tích 4 tham số của VLOOKUP

Cú pháp hàm:

```
=VLOOKUP(lookup_value, table_array, col_index_num, FALSE)
```
Ý nghĩa từng tham số:
|Tham số|Ý nghĩa|Áp dụng vào bài toán
|-|-|-
|lookup_value|Giá trị cần tìm|Mã linh kiện trong Sheet `Don_Hang`, ví dụ `LK01` ở ô `A2`
|table_array|Vùng bảng dùng để tra cứu|Bảng dữ liệu trong Sheet `Danh_Muc`, ví dụ `$A$2:$C$101`
|col_index_num|Số thứ tự cột cần lấy kết quả, tính từ cột đầu tiên của vùng tra cứu|`2` để lấy Tên linh kiện; `3` để lấy Đơn giá
|FALSE|Yêu cầu tìm kiếm chính xác|Chỉ trả về kết quả khi mã linh kiện khớp chính xác


Ví dụ cấu trúc dữ liệu

Sheet Danh_Muc:
|A – Mã linh kiện|B – Tên linh kiện|C – Đơn giá
|-|-|-
|LK01|Cảm biến nhiệt độ|150000
|LK02|Cảm biến độ ẩm|120000
|LK03|Máy bơm mini|250000
Sheet Don_Hang:
|A – Mã linh kiện|B – Tên linh kiện|C – Đơn giá
|-|-|-
|LK01|Tự tra cứu|Tự tra cứu
|LK02|Tự tra cứu|Tự tra cứu

### Vì sao phải dùng dấu `$`?

Khi kéo công thức xuống các dòng dưới, vùng bảng tra cứu phải giữ nguyên.

-   Không cố định: `Danh_Muc!A2:C101` — vùng tra cứu có thể bị dịch chuyển.
    
-   Có cố định: `Danh_Muc!$A$2:$C$101` — vùng tra cứu không thay đổi.
    

Bôi đen địa chỉ vùng trong thanh công thức rồi nhấn F4 để thêm dấu `$` 

## Phần 2. Triển khai công thức hoàn chỉnh

Giả sử:

-   Sheet `Don_Hang`: cột A chứa mã linh kiện, cột B là Tên linh kiện, cột C là Đơn giá.
    
-   Sheet `Danh_Muc`: cột A là Mã linh kiện, cột B là Tên linh kiện, cột C là Đơn giá.
    

### 1. Công thức lấy Tên linh kiện

Nhập tại ô `B2` của Sheet `Don_Hang`:

```
=IFERROR(VLOOKUP(TRIM(A2),Danh_Muc!$A$2:$C$101,2,FALSE),"Không tìm thấy mã")
```

### 2. Công thức lấy Đơn giá

Nhập tại ô `C2`:

```
=IFERROR(VLOOKUP(TRIM(A2),Danh_Muc!$A$2:$C$101,3,FALSE),"Không tìm thấy mã")
```

Sau đó kéo công thức xuống hết 100 dòng.

-   `TRIM(A2)`: loại bỏ khoảng trắng thừa ở đầu và cuối mã đang tra cứu.
    
-   `IFERROR(...,"Không tìm thấy mã")`: hiển thị thông báo dễ hiểu thay vì lỗi `#N/A`.
    
-   `2` và `3`: xác định cột kết quả cần lấy trong vùng tra cứu.
    
-   `FALSE`: tìm mã chính xác.
    
-   `$A$2:$C$101`: cố định vùng tra cứu.
    

### 3. Xử lý bẫy khoảng trắng trong bảng Danh_Muc

Chú ý: `TRIM(A2)` chỉ xử lý khoảng trắng trong mã ở Sheet `Don_Hang`. Nếu mã trong Sheet `Danh_Muc` cũng có khoảng trắng thừa, công thức trên chưa chắc tìm được.

Cách đơn giản và ổn định nhất là tạo một cột phụ trong `Danh_Muc`, chẳng hạn cột D, để làm sạch mã.

Tại `D2`, nhập:

```
=TRIM(A2)
```
