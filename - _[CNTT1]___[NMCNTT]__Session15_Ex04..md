# BÀI TẬP: FILES ON-DEMAND VÀ QUẢN LÝ DỮ LIỆU CLOUD

## 1. VẤN ĐỀ

Nhóm có 500GB dữ liệu video giám sát campus nhưng mỗi laptop chỉ có ổ SSD 256GB. Nếu đồng bộ toàn bộ dữ liệu từ Cloud về máy tính, ổ cứng sẽ không đủ dung lượng, khiến máy chậm và phần mềm đồng bộ có thể gặp lỗi.

Ngoài ra, video có dung lượng lớn nên nếu tải lên cùng lúc sẽ chiếm nhiều băng thông Internet. Khi gập laptop hoặc mất kết nối, quá trình đồng bộ có thể bị gián đoạn.

## 2. YÊU CẦU

- Sử dụng Files On-Demand để xem danh sách file trên Cloud mà không cần tải toàn bộ về máy.
- Chỉ tải video xuống khi thực sự cần mở hoặc xử lý.
- Kiểm soát tốc độ đồng bộ để không ảnh hưởng đến Internet của mọi người.
- Đảm bảo quá trình đồng bộ có thể tiếp tục sau khi laptop kết nối mạng trở lại.

## 3. CÁCH LÀM

### A. Giải pháp kỹ thuật

Sử dụng dịch vụ lưu trữ Cloud có hỗ trợ Files On-Demand, ví dụ OneDrive.

**Các bước thực hiện:**

1. Cài đặt OneDrive và đăng nhập tài khoản.
2. Bật tính năng Files On-Demand trong phần Settings của OneDrive.
3. Đồng bộ thư mục video giám sát với Cloud.
4. Chọn chế độ **Free up space** để giữ file trên Cloud và giải phóng dung lượng trên máy.
5. Khi cần xem video, mở file để tải nội dung xuống thiết bị.

**Các trạng thái file cần phân biệt:**

| Trạng thái | Ý nghĩa |
|---|---|
| Online-only | Chỉ lưu trên Cloud, không chiếm đáng kể dung lượng SSD. |
| Locally available | Đã tải xuống máy, có thể sử dụng khi không có Internet. |
| Always keep on this device | Luôn giữ bản tải xuống trên máy, chiếm dung lượng SSD. |

**Giải quyết vấn đề đường truyền và gập laptop:**

- Thiết lập giới hạn tốc độ upload/download trong OneDrive nếu phiên bản hỗ trợ.
- Chia dữ liệu thành từng đợt đồng bộ, tránh tải toàn bộ 500GB cùng lúc.
- Ưu tiên đồng bộ vào thời gian ít người sử dụng Internet.
- Khi gập laptop, quá trình đồng bộ có thể tạm dừng nếu máy chuyển sang chế độ Sleep. Khi mở máy và có mạng trở lại, OneDrive sẽ tiếp tục đồng bộ các dữ liệu chưa hoàn tất.

### B. Báo cáo dung lượng

Giả sử nhóm có 500GB dữ liệu video và laptop có SSD 256GB.

| Tiêu chí | Đồng bộ toàn bộ | Sử dụng Files On-Demand |
|---|---:|---:|
| Dung lượng Cloud | 500GB | 500GB |
| Dung lượng SSD cần dùng | 500GB | Chỉ dùng cho file đã tải xuống và dữ liệu ứng dụng |
| Khả năng lưu trữ | Không đủ | Có thể quản lý được |
| Nguy cơ đầy SSD | Rất cao | Thấp hơn đáng kể |

**Ví dụ tính toán:**

Giả sử nhóm chỉ cần tải 20GB video thường xuyên sử dụng xuống laptop.

- Tổng dữ liệu Cloud: 500GB.
- Dữ liệu tải xuống máy: 20GB.
- Dung lượng tiết kiệm được:

  `500 - 20 = 480GB`

- Tỷ lệ giảm dung lượng cần lưu trên máy:

  `(480 / 500) x 100% = 96%`




