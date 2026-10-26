
#  DỰ ÁN SMART-HOME
## Nền tảng đấu giá và cho thuê nhà đất trực tuyến


# PHẦN 1. PHÂN TÍCH BẢNG EXCEL XẤU VÀ BẢNG EXCEL ĐÚNG

## 1.1. So sánh bảng Excel xấu và bảng Excel đúng

| Tiêu chí | Bảng Excel xấu | Bảng Excel đúng |
|---|---|---|
| Gộp ô | Sử dụng Merge Cells trong vùng dữ liệu | Không gộp ô trong vùng dữ liệu |
| Tiêu đề | Tiêu đề nhiều dòng, lẫn với dữ liệu | Chỉ có một hàng tiêu đề rõ ràng |
| Field | Một cột chứa nhiều loại thông tin | Mỗi cột tương ứng một trường dữ liệu |
| Record | Một hàng chứa nhiều bản ghi hoặc thiếu thông tin | Mỗi hàng tương ứng một bản ghi |
| Dòng trống | Có dòng trống chen giữa danh sách | Dữ liệu được trình bày liên tục |
| Kiểu dữ liệu | Giá thuê vừa là số vừa là chữ | Giá thuê lưu dưới dạng số |
| Mã định danh | Mã nhà đất bị trùng hoặc để trống | Mỗi bất động sản có mã riêng |
| Công thức | Gõ thủ công, dễ sai khi sao chép | Sử dụng công thức và vùng tham chiếu phù hợp |
| Trình bày | Quá nhiều màu sắc, khó đọc | Màu sắc thống nhất, dễ quan sát |

## 1.2. Khái niệm Field và Record

- **Field:** Trường dữ liệu, tương ứng với một cột trong bảng.
- **Record:** Bản ghi dữ liệu, tương ứng với một hàng trong bảng.

Ví dụ:

| Ma_NhaDat | Loai_BDS | Khu_Vuc | Gia_Thue_Thang |
|---|---|---|---:|
| SH001 | Căn hộ | Cầu Giấy | 12000000 |
| SH002 | Nhà phố | Thanh Xuân | 18000000 |
| SH003 | Căn hộ | Nam Từ Liêm | 9500000 |

Trong bảng trên:
- `Ma_NhaDat` là một Field.
- Hàng có mã `SH001` là một Record.

## 1.3. Năm quy tắc vàng khi thiết kế bảng Excel

1. Không gộp ô trong vùng dữ liệu.
2. Mỗi cột chỉ lưu một loại thông tin.
3. Mỗi cột có tiêu đề riêng biệt.
4. Không để dòng trống hoặc cột trống chen giữa bảng dữ liệu.
5. Sử dụng đúng kiểu dữ liệu và công thức nhất quán.

---

# PHẦN 2. TÀI LIỆU SRS DỰ ÁN SMART-HOME

## 1. Giới thiệu

### 1.1. Mục đích

Tài liệu SRS (Software Requirements Specification) mô tả các yêu cầu phần mềm của nền tảng Smart-Home.

Tài liệu giúp nhóm phát triển, đối tác, kiểm thử và nhà đầu tư hiểu rõ mục tiêu, chức năng và giới hạn của hệ thống.

### 1.2. Phạm vi dự án

Smart-Home là nền tảng trực tuyến hỗ trợ:

- Tìm kiếm và xem thông tin nhà đất.
- Đăng tin bất động sản.
- Kiểm duyệt và xác minh tin đăng.
- Gửi yêu cầu thuê nhà.
- Tham gia các phiên đấu giá trực tuyến.
- Tra cứu tỷ lệ hoa hồng môi giới.
- Theo dõi trạng thái giao dịch.

### 1.3. Đối tượng sử dụng

- Người mua hoặc thuê nhà đất.
- Chủ sở hữu bất động sản.
- Nhân viên môi giới.
- Nhân viên kiểm duyệt.
- Quản trị viên hệ thống.
- Nhóm phát triển và kiểm thử phần mềm.

## 2. Mô tả tổng quan

### 2.1. Nhóm người dùng

#### 2.1.1. Khách truy cập

- Tìm kiếm nhà đất.
- Xem thông tin tin đăng công khai.
- Lọc bất động sản theo khu vực và giá.

#### 2.1.2. Thành viên

- Đăng nhập và quản lý hồ sơ.
- Lưu tin yêu thích.
- Gửi yêu cầu thuê nhà.
- Đăng ký tham gia phiên đấu giá.

#### 2.1.3. Môi giới và chủ nhà

- Tạo và chỉnh sửa tin đăng.
- Theo dõi khách hàng quan tâm.
- Quản lý yêu cầu thuê.
- Tra cứu tỷ lệ hoa hồng.

#### 2.1.4. Quản trị viên

- Quản lý tài khoản.
- Kiểm duyệt tin đăng.
- Xử lý báo cáo vi phạm.
- Theo dõi nhật ký hoạt động.

### 2.2. Môi trường vận hành

Hệ thống dự kiến hoạt động trên trình duyệt web của máy tính và điện thoại.

Các thành phần chính gồm:

- Giao diện người dùng.
- Máy chủ ứng dụng.
- Cơ sở dữ liệu.
- Dịch vụ gửi thông báo.
- Cổng thanh toán hoặc đặt cọc của bên thứ ba nếu được tích hợp.

### 2.3. Giả định và giới hạn

- Tin đăng phải được kiểm duyệt trước khi công khai.
- Thông tin pháp lý của bất động sản cần được xác minh.
- Tính năng thanh toán hoặc đặt cọc chỉ triển khai khi đáp ứng yêu cầu pháp lý.
- Phiên bản MVP tập trung vào các chức năng thiết yếu.

## 3. Yêu cầu chức năng

### 3.1. Tài khoản và phân quyền

- **FR-01:** Người dùng có thể đăng ký, đăng nhập và đăng xuất.
- **FR-02:** Hệ thống phân quyền theo vai trò người dùng.
- **FR-03:** Người dùng có thể cập nhật hồ sơ và đổi mật khẩu.

### 3.2. Tìm kiếm và xem tin

- **FR-04:** Người dùng có thể lọc theo khu vực, loại bất động sản, mức giá và mục đích mua hoặc thuê.
- **FR-05:** Trang chi tiết hiển thị mã tin, khu vực, giá, diện tích, hình ảnh, mô tả và trạng thái xác minh.
- **FR-06:** Thành viên có thể lưu tin yêu thích và gửi yêu cầu liên hệ.

### 3.3. Đăng tin và kiểm duyệt

- **FR-07:** Môi giới hoặc chủ nhà có thể tạo, sửa và tạm ẩn tin đăng của mình.
- **FR-08:** Tin đăng mới có trạng thái "Chờ duyệt".
- **FR-09:** Quản trị viên có thể duyệt, từ chối hoặc yêu cầu bổ sung thông tin.
- **FR-10:** Hệ thống lưu lý do và thời điểm xử lý tin đăng.

### 3.4. Đấu giá trực tuyến

- **FR-11:** Người đủ điều kiện có thể đăng ký tham gia phiên đấu giá đang mở.
- **FR-12:** Hệ thống hiển thị giá hiện tại, bước giá tối thiểu và thời gian phiên đấu giá.
- **FR-13:** Hệ thống từ chối mức giá không hợp lệ.
- **FR-14:** Hệ thống ghi nhận thời gian của từng lượt trả giá.
- **FR-15:** Khi phiên kết thúc, hệ thống khóa lượt trả giá và lưu kết quả.
- **FR-16:** Hệ thống gửi thông báo kết quả cho các bên liên quan.

### 3.5. Quản lý thuê và hoa hồng

- **FR-17:** Người thuê có thể gửi yêu cầu thuê và thời hạn dự kiến.
- **FR-18:** Môi giới có thể theo dõi và cập nhật trạng thái yêu cầu.
- **FR-19:** Hệ thống tính giá thuê sau chiết khấu.
- **FR-20:** Hệ thống tra cứu tỷ lệ hoa hồng theo mã gói dịch vụ.
- **FR-21:** Hệ thống hiển thị giá trị hoa hồng ước tính.

## 4. Yêu cầu phi chức năng

### 4.1. Bảo mật

- **NFR-01:** Mật khẩu phải được băm bằng thuật toán phù hợp.
- **NFR-02:** Người dùng chỉ được truy cập chức năng phù hợp với quyền hạn.
- **NFR-03:** Các thao tác quan trọng phải có nhật ký kiểm tra.

### 4.2. Hiệu năng và khả dụng

- **NFR-04:** Trong điều kiện tải mục tiêu của MVP, 95% yêu cầu tìm kiếm thông thường phản hồi trong 3 giây.
- **NFR-05:** Giao diện phù hợp với màn hình máy tính và điện thoại.
- **NFR-06:** Lỗi dịch vụ bên ngoài phải được thông báo rõ ràng.

### 4.3. Tính toàn vẹn dữ liệu

- **NFR-07:** Mỗi tin đăng có mã định danh duy nhất.
- **NFR-08:** Giá thuê và tỷ lệ hoa hồng được lưu dưới dạng số.
- **NFR-09:** Thay đổi trạng thái đấu giá phải lưu thời gian và tài khoản thực hiện.

## 5. Dữ liệu và quy tắc nghiệp vụ

### 5.1. Các trường dữ liệu chính

| Tên trường | Ý nghĩa |
|---|---|
| Ma_NhaDat | Mã bất động sản |
| Loai_BDS | Loại bất động sản |
| Khu_Vuc | Khu vực |
| Gia_Thue_Thang | Giá thuê trước chiết khấu |
| Chiet_Khau_% | Tỷ lệ chiết khấu |
| Gia_Sau_CK | Giá thuê sau chiết khấu |
| Ma_Goi_HH | Mã gói hoa hồng |
| Ty_Le_HH | Tỷ lệ hoa hồng |
| Hoa_Hong_Uoc_Tinh | Giá trị hoa hồng ước tính |
| Trang_Thai | Trạng thái tin đăng |

### 5.2. Công thức tính giá thuê

**Giá thuê sau chiết khấu:**

Giá thuê sau chiết khấu = Giá thuê tháng × (1 − Tỷ lệ chiết khấu)

Ví dụ:

- Giá thuê ban đầu: 12.000.000 đồng/tháng.
- Tỷ lệ chiết khấu: 5%.
- Giá thuê sau chiết khấu: 11.400.000 đồng/tháng.

### 5.3. Công thức tính hoa hồng

Hoa hồng ước tính = Giá trị giao dịch × Tỷ lệ hoa hồng.

Lưu ý: Tỷ lệ và cơ sở tính hoa hồng thực tế phải được xác nhận theo hợp đồng và chính sách áp dụng.

### 5.4. Trạng thái tin đăng

- Nháp.
- Chờ duyệt.
- Đã duyệt.
- Từ chối.
- Tạm ẩn.
- Đã giao dịch.

## 6. Tiêu chí nghiệm thu

### 6.1. Kiểm thử chức năng

- **AT-01:** Bộ lọc trả về tin phù hợp.
- **AT-02:** Tin mới chưa duyệt không hiển thị công khai.
- **AT-03:** Người dùng không thể sửa tin của tài khoản khác.
- **AT-04:** Giá trả thấp hơn mức hợp lệ bị từ chối.
- **AT-05:** Hệ thống không nhận lượt trả giá sau khi phiên kết thúc.
- **AT-06:** Kết quả đấu giá được lưu và thông báo.
- **AT-07:** Giá thuê sau chiết khấu khớp công thức.
- **AT-08:** Mã hoa hồng hợp lệ trả về đúng tỷ lệ.
- **AT-09:** Mã hoa hồng không tồn tại hiển thị thông báo lỗi dễ hiểu.
- **AT-10:** Kéo công thức Excel xuống 500 dòng không làm trôi vùng tra cứu.

---

# PHẦN 3. THIẾT KẾ BẢNG EXCEL QUẢN LÝ NHÀ ĐẤT

## 1. Cấu trúc bảng NhaDat

| Ma_NhaDat | Loai_BDS | Khu_Vuc | Gia_Thue_Thang | Chiet_Khau_% | Gia_Sau_CK | Ma_Goi_HH | Ty_Le_HH | Hoa_Hong_Uoc_Tinh | Trang_Thai |
|---|---|---|---:|---:|---:|---|---:|---:|---|
| SH001 | Căn hộ | Cầu Giấy | 12000000 | 5% | 11400000 | HH01 | 3% | 360000 | Đang đăng |
| SH002 | Nhà phố | Thanh Xuân | 18000000 | 10% | 16200000 | HH02 | 4% | 720000 | Chờ duyệt |
| SH003 | Căn hộ | Nam Từ Liêm | 9500000 | 0% | 9500000 | HH01 | 3% | 285000 | Đang đăng |
| SH004 | Biệt thự | Tây Hồ | 45000000 | 8% | 41400000 | HH04 | 6% | 2700000 | Đang đăng |
| SH005 | Nhà phố | Hai Bà Trưng | 22000000 | 7% | 20460000 | HH03 | 5% | 1100000 | Đã cho thuê |

## 2. Bảng tra cứu hoa hồng BangHH

| Ma_Goi_HH | Ty_Le_HH | Ghi_Chu |
|---|---:|---|
| HH01 | 3% | Gói cơ bản |
| HH02 | 4% | Gói tiêu chuẩn |
| HH03 | 5% | Gói nâng cao |
| HH04 | 6% | Gói cao cấp |
| HH05 | 2.5% | Gói đất nền |

## 3. Công thức Excel

Giả sử:
- Cột D: Giá thuê tháng.
- Cột E: Chiết khấu.
- Cột F: Giá thuê sau chiết khấu.
- Cột G: Mã gói hoa hồng.
- Cột H: Tỷ lệ hoa hồng.
- Cột I: Hoa hồng ước tính.

### 3.1. Tính giá thuê sau chiết khấu

Nhập vào ô F2:

```excel
=D2*(1-E2)
```

Ví dụ: Giá thuê 12.000.000 đồng, chiết khấu 5% thì kết quả là 11.400.000 đồng.

### 3.2. Tra cứu tỷ lệ hoa hồng bằng VLOOKUP

Nhập vào ô H2:

```excel
=IFERROR(VLOOKUP(G2,BangHH!$A$2:$B$6,2,FALSE),"Kiểm tra mã")
```

Ý nghĩa:
- `G2`: Mã gói hoa hồng cần tra cứu.
- `BangHH!$A$2:$B$6`: Vùng dữ liệu tra cứu.
- `2`: Lấy kết quả ở cột thứ hai.
- `FALSE`: Tìm kiếm chính xác.
- `IFERROR`: Hiển thị thông báo nếu mã không tồn tại.

### 3.3. Tính hoa hồng ước tính

Nhập vào ô I2:

```excel
=IFERROR(D2*H2,"")
```

Kéo công thức xuống các hàng tiếp theo.

> Lưu ý: Công thức ví dụ dùng giá thuê tháng làm cơ sở tính hoa hồng. Nếu hợp đồng quy định hoa hồng tính theo giá trị giao dịch hoặc doanh thu khác, cần thay công thức tương ứng.

---

# PHẦN 4. KIỂM THỬ LỖI TRÔI VÙNG TRA CỨU VÀ DẤU $

## 4.1. Công thức sai

```excel
=VLOOKUP(G2,BangHH!A2:B6,2,FALSE)
```

Khi kéo công thức xuống, Excel có thể tự đổi vùng tra cứu:

- Hàng 2: `A2:B6`
- Hàng 3: `A3:B7`
- Hàng 4: `A4:B8`

Vùng tra cứu bị dịch chuyển, khiến công thức có thể trả về kết quả sai hoặc lỗi `#N/A`.

## 4.2. Công thức đúng

```excel
=IFERROR(VLOOKUP(G2,BangHH!$A$2:$B$6,2,FALSE),"Kiểm tra mã")
```

Dấu `$` khóa cột và hàng của vùng tra cứu.

| Tham chiếu | Ý nghĩa |
|---|---|
| `A2` | Cột và hàng đều có thể thay đổi |
| `$A$2` | Khóa cả cột A và hàng 2 |
| `$A2` | Khóa cột A, hàng có thể thay đổi |
| `A$2` | Cột có thể thay đổi, khóa hàng 2 |

## 4.3. Cách sử dụng phím F4

1. Chọn ô đang chứa công thức.
2. Nhấp vào thanh công thức.
3. Bôi chọn tham chiếu `A2:B6`.
4. Nhấn `F4` để chuyển thành `$A$2:$B$6`.
5. Nhấn Enter.
6. Kéo công thức xuống các dòng còn lại.
7. Kiểm tra xem vùng tra cứu có giữ nguyên hay không.

Trên một số laptop, cần nhấn `Fn + F4`.

## 4.4. Kiểm thử mã không hợp lệ

Ví dụ, nhập mã `HH99` vào cột `Ma_Goi_HH`.

Công thức:

```excel
=IFERROR(VLOOKUP(G2,BangHH!$A$2:$B$6,2,FALSE),"Kiểm tra mã")
```

Kết quả mong đợi:

`Kiểm tra mã`

Điều này giúp người dùng nhận biết mã không tồn tại thay vì để lỗi công thức hiển thị trực tiếp.

---

# PHẦN 5. PITCH DECK GỌI VỐN SMART-HOME

## 5.1. Nguyên tắc thiết kế

Bộ Pitch Deck tuân thủ Rule 10/20/30:

- Không quá 10 slide.
- Thời lượng thuyết trình khoảng 20 phút.
- Cỡ chữ tối thiểu khoảng 30 pt theo quy tắc kinh điển của Guy Kawasaki; có thể điều chỉnh hợp lý cho biểu đồ hoặc chú thích.

Mỗi slide chỉ tập trung vào một thông điệp chính.

Thiết kế cần:
- Có khoảng trắng (White Space).
- Không nhồi nhét nhiều đoạn văn.
- Dùng tối đa 3–4 ý chính trên mỗi slide.
- Dùng màu sắc thống nhất.
- Sử dụng biểu đồ khi giúp thông tin dễ hiểu hơn.

## 5.2. Kịch bản 8 slide

### Slide 1 — Smart-Home

**Thông điệp:** Đưa giao dịch nhà đất lên một nền tảng minh bạch.

Nội dung:
- Tìm kiếm nhà đất.
- Cho thuê trực tuyến.
- Đấu giá trực tuyến.

Thiết kế: Tiêu đề lớn, nền xanh đậm, điểm nhấn màu cam và nhiều khoảng trắng.

### Slide 2 — Vấn đề

**Thông điệp:** Thông tin phân tán khiến giao dịch khó tin cậy.

Nội dung:
- Tin đăng thiếu chuẩn hóa, khó so sánh.
- Trạng thái xác minh chưa rõ ràng.
- Quy trình hỏi thuê và đấu giá còn rời rạc.

### Slide 3 — Giải pháp

**Thông điệp:** Một quy trình số hóa từ tin đăng đến giao dịch.

Nội dung:
- Tin đăng có cấu trúc và trạng thái kiểm duyệt.
- Tìm kiếm theo khu vực, giá và loại bất động sản.
- Phiên đấu giá hiển thị quy tắc và thời gian rõ ràng.

### Slide 4 — Sản phẩm

**Thông điệp:** MVP tập trung vào ba luồng cốt lõi.

Nội dung:
- Tìm kiếm và lưu tin.
- Đăng tin, kiểm duyệt và liên hệ.
- Yêu cầu thuê và đấu giá có nhật ký.

### Slide 5 — Thị trường

**Thông điệp:** Bắt đầu tại một khu vực để kiểm chứng nhu cầu.

Nội dung:
- Thử nghiệm với một nhóm môi giới và chủ nhà.
- Đo số tin hợp lệ, lượt hỏi thuê và tỷ lệ phản hồi.
- Mở rộng sau khi đạt tiêu chí MVP.

Lưu ý: Cần bổ sung số liệu khảo sát thị trường thực tế trước khi gọi vốn.

### Slide 6 — Mô hình doanh thu

**Thông điệp:** Doanh thu đến từ các dịch vụ có giá trị rõ ràng.

Nội dung:
- Gói đăng tin nổi bật hoặc thuê bao môi giới.
- Phí dịch vụ theo giao dịch nếu phù hợp pháp lý.
- Dịch vụ xác minh hoặc đối tác tùy chọn.

Các nguồn thu này là giả thuyết cần kiểm chứng bằng thử nghiệm thực tế.

### Slide 7 — Lợi thế và kế hoạch

**Thông điệp:** Niềm tin là chỉ số sản phẩm cần xây dựng.

Nội dung:
- Chuẩn hóa dữ liệu và quy trình kiểm duyệt.
- Theo dõi tỷ lệ tin sai, thời gian phản hồi và chuyển đổi.
- Thu thập phản hồi và cải tiến theo chu kỳ.

### Slide 8 — Đề nghị đầu tư

**Thông điệp:** Nguồn lực đầu tư sẽ dùng để kiểm chứng ba giả thuyết.

Nội dung:
- Xây dựng MVP và bảo mật nền tảng.
- Thử nghiệm với đối tác môi giới và chủ nhà.
- Đo KPI trước khi chốt quy mô vốn và kế hoạch mở rộng.

Trước khi trình bày với nhà đầu tư, hãy bổ sung số vốn cần gọi, dự toán chi phí, tiến độ và kết quả thử nghiệm thực tế.

---

# PHẦN 6. KẾT LUẬN

Dự án Smart-Home giúp vận dụng đồng thời ba nhóm kỹ năng:

1. **Word:** Sử dụng Heading 1, Heading 2, Heading 3 để tạo tài liệu SRS có cấu trúc chuyên nghiệp.
2. **Excel:** Quản lý dữ liệu theo Field và Record, tính chiết khấu, tra cứu hoa hồng bằng VLOOKUP và khóa vùng bằng dấu `$`.
3. **PowerPoint:** Thiết kế Pitch Deck tối đa 10 slide, mỗi slide một thông điệp và có khoảng trắng hợp lý.



