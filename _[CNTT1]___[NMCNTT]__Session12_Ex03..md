
#  FASTMOVE — TỰ ĐỘNG HÓA QUY TRÌNH KHO

## PHẦN 1. PHÂN TÍCH VLOOKUP

### 1.1. Bối cảnh

FastMove gặp tình trạng tra cứu giá cước thủ công gây chậm trễ 16 tiếng mỗi ngày. Giải pháp là sử dụng Excel để tự động tra cứu giá, giảm thao tác nhập liệu và chuẩn hóa quy trình vận hành kho.

### 1.2. Mapping 4 tham số VLOOKUP

Cú pháp:

```excel
=VLOOKUP(lookup_value,table_array,col_index_num,range_lookup)
```

| Tham số | Ý nghĩa | Ví dụ tại kho |
|---|---|---|
| `lookup_value` | Giá trị cần tìm | Mã dịch vụ của đơn hàng |
| `table_array` | Vùng bảng tra cứu | Bảng giá trên Sheet GiaCuoc |
| `col_index_num` | Số thứ tự cột trả về | 2, tức cột giá cước |
| `range_lookup` | Kiểu tìm kiếm | FALSE để tìm chính xác |

### 1.3. Công thức VLOOKUP

Giả sử mã dịch vụ nằm ở ô B2, bảng giá nằm trên Sheet `GiaCuoc`, cột A chứa mã dịch vụ và cột B chứa giá cước.

```excel
=VLOOKUP(B2,GiaCuoc!$A$2:$B$101,2,FALSE)
```

**Giải thích:**

- `B2`: mã dịch vụ cần tra cứu.
- `GiaCuoc!$A$2:$B$101`: vùng bảng giá cần cố định.
- `2`: lấy giá trị từ cột thứ hai.
- `FALSE`: chỉ chấp nhận kết quả khớp chính xác.
- Dấu `$`: cố định vùng tra cứu khi kéo công thức xuống.

Lưu ý: Nếu bảng giá thực tế được xác định theo mã dịch vụ hoặc mã tuyến, cần dùng đúng loại mã đó để tra cứu, không mặc định rằng mã vận đơn chính là mã giá cước.

---

## PHẦN 2. TRIỂN KHAI GIẢI PHÁP FASTMOVE

### 2.1. Quy trình vận hành kho

1. **Tiếp nhận đơn:** Quét mã vận đơn và kiểm tra thông tin.
2. **Tra cứu giá:** Sử dụng mã dịch vụ hoặc mã tuyến để tra bảng giá tự động.
3. **Đối soát:** Kiểm tra mã không hợp lệ, giá bất thường và lỗi tra cứu.
4. **Bàn giao:** Xác nhận kiện hàng và bàn giao thông tin cho shipper.
5. **Cập nhật:** Ghi nhận trạng thái giao hàng và kết quả xử lý.

### 2.2. Quy tắc Vàng khi thiết kế Excel

- Mỗi cột chỉ chứa một loại dữ liệu.
- Hàng đầu tiên là hàng tiêu đề duy nhất.
- Không gộp ô trong vùng dữ liệu.
- Không chèn hàng tổng cộng vào giữa các bản ghi.
- Mã dữ liệu phải thống nhất, tránh khoảng trắng và ký tự không cần thiết.

### 2.3. Tự động tra cứu 500 dòng

Tại ô F2 của Sheet `DonHang`, nhập:

```excel
=IFERROR(VLOOKUP(B2,GiaCuoc!$A$2:$B$6,2,FALSE),"Kiểm tra mã")
```

Sau đó kéo công thức từ F2 xuống F501.

**Kết quả:**

- Mã hợp lệ: trả về giá cước tương ứng.
- Mã không tồn tại: hiển thị `Kiểm tra mã`.
- Vùng bảng giá giữ nguyên nhờ các dấu `$`.

### 2.4. Hướng dẫn shipper nhận đơn

Áp dụng Miller's Law bằng cách giới hạn tối đa 3–4 ý chính trên slide:

- Quét mã vận đơn và xác nhận thông tin.
- Kiểm tra địa chỉ, số liên hệ và ghi chú.
- Kiểm tra tuyến giao và giá cước đã tra cứu.
- Xác nhận nhận đơn và cập nhật trạng thái.

### 2.5. Báo cáo KPI giao hàng

Các chỉ số nên theo dõi:

| KPI | Công thức |
|---|---|
| Tỷ lệ giao thành công | Đơn giao thành công / Tổng đơn đã xử lý × 100% |
| Tỷ lệ giao đúng hạn | Đơn đúng hạn / Tổng đơn đã xử lý × 100% |
| Tỷ lệ tra cứu lỗi | Đơn tra cứu lỗi / Tổng đơn tra cứu × 100% |

Biểu đồ sử dụng dạng **Bar Chart**, có nhãn dữ liệu và màu cam để làm nổi bật chỉ số cần chú ý.

Tiêu đề slide phải là kết luận dựa trên dữ liệu, ví dụ:

**“Tỷ lệ giao thành công cao nhất ở tuyến Nội thành”**

Chỉ sử dụng kết luận này nếu dữ liệu thực tế xác nhận điều đó. Không nên đặt tiêu đề chung chung như “KPI tháng 7”.

---

## PHẦN 3. KIỂM THỬ

### 3.1. Xử lý lỗi #N/A bằng IFERROR

Công thức:

```excel
=IFERROR(VLOOKUP(B2,GiaCuoc!$A$2:$B$6,2,FALSE),"Kiểm tra mã")
```

Nếu mã tra cứu không tồn tại, Excel sẽ hiển thị thông báo dễ hiểu thay vì lỗi `#N/A`.

### 3.2. Xử lý ký tự lạ và khoảng trắng

Nếu mã có khoảng trắng thừa, có thể tạo cột phụ và dùng:

```excel
=TRIM(B2)
```

Nếu dữ liệu chứa khoảng trắng không ngắt:

```excel
=TRIM(SUBSTITUTE(B2,CHAR(160)," "))
```

Sau khi chuẩn hóa, kiểm tra lại mã với danh mục giá cước.

### 3.3. Bảng kiểm thử

| Mã | Nội dung kiểm thử | Kết quả mong đợi |
|---|---|---|
| TC-01 | Tra mã dịch vụ hợp lệ | Trả đúng giá cước |
| TC-02 | Kéo công thức qua 500 dòng | Vùng tra cứu không dịch chuyển |
| TC-03 | Tra mã không tồn tại | Hiển thị “Kiểm tra mã” |
| TC-04 | Kiểm tra cấu trúc bảng | Không gộp ô, không có hàng tổng cộng ở giữa |
| TC-05 | Kiểm tra slide shipper | Tối đa 4 bullet chính |
| TC-06 | Kiểm tra biểu đồ KPI | Có nhãn dữ liệu và tiêu đề dạng kết luận |


