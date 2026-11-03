# PHÂN TÍCH VÀ CHẨN ĐOÁN LỖI DNS

## PHẦN 1. PHÂN TÍCH

### 1. Input và Output của DNS

- **Input:** Tên miền website, ví dụ: `phong-dieu-phoi.greenlog.vn`.
- **Output:** Địa chỉ IP của máy chủ chứa website.

DNS (Domain Name System) được ví như cuốn danh bạ Internet, giúp chuyển đổi tên miền thành địa chỉ IP để trình duyệt tìm được máy chủ.

### 2. Tiến trình DNS Lookup

Khi Nam nhập tên miền vào trình duyệt, quá trình diễn ra như sau:

1. **Kiểm tra bộ nhớ Cache:** Trình duyệt và hệ điều hành kiểm tra xem địa chỉ IP của tên miền đã được lưu trước đó chưa.
2. **DNS Resolver:** Nếu chưa có kết quả, máy tính gửi yêu cầu đến DNS Resolver của nhà cung cấp mạng hoặc DNS đã cấu hình.
3. **Root DNS Server:** Resolver hỏi máy chủ DNS gốc để tìm máy chủ quản lý tên miền cấp cao nhất `.vn`.
4. **TLD DNS Server:** Máy chủ `.vn` hướng dẫn Resolver đến máy chủ DNS có thẩm quyền quản lý `greenlog.vn`.
5. **Authoritative DNS Server:** Máy chủ DNS có thẩm quyền kiểm tra bản ghi của tên miền và trả về địa chỉ IP nếu tên miền tồn tại.
6. **Kết nối máy chủ:** Resolver trả IP về máy tính. Trình duyệt sử dụng IP đó để kết nối đến máy chủ website.

### 3. Sơ đồ luồng dữ liệu DNS

```text
Nam nhập tên miền
        |
        v
Kiểm tra DNS Cache
        |
        v
DNS Resolver
        |
        v
Root DNS Server
        |
        v
TLD DNS Server (.vn)
        |
        v
Authoritative DNS Server
        |
        v
Trả về địa chỉ IP
        |
        v
Trình duyệt kết nối máy chủ
```
### 4. Hậu quả khi nhập sai tên miền

Nam nhập nhầm:
`phong-dieu-phoi.grenlog.vn`
Thay vì:
`phong-dieu-phoi.greenlog.vn`

Do thiếu chữ `e` trong tên miền `greenlog`, DNS sẽ tìm kiếm một tên miền khác là `grenlog.vn`.

Nếu tên miền này không tồn tại hoặc không có bản ghi DNS phù hợp, quá trình phân giải sẽ thất bại và trình duyệt báo lỗi:

`DNS_PROBE_FINISHED_NXDOMAIN`

Lỗi này có nghĩa là DNS không tìm thấy tên miền, không chứng minh máy chủ công ty bị sập nguồn.
## Phần 2. Triển Khai
### Phân biệt lỗi DNS và lỗi 500
|Tiêu chí|Lỗi DNS|Lỗi 500 internal server error
|-|-|-
Bản chất|Không phân giải được tên miền thành IP|Máy chủ gặp lỗi khi xử lý yêu cầu
|Vị trí lỗi|Trước khi kết nối đến máy chủ website|Phía Server
|Nguyên nhân|Sai tên miền, DNS không có bản ghi phù hợp|Lỗi code Backend, cơ sở dữ liệu hoặc cấu hình Server
|Kết quả|Trình duyệt không tìm được địa chỉ IP|Máy chủ đã nhận yêu cầu nhưng không xử lý thành công
### 2. Quy trình kiểm tra HTTP Status Code

Để xác định yêu cầu đã đến được máy chủ hay chưa, Nam thực hiện:
1.  Sửa lại tên miền cho chính xác.    
2.  Mở website và nhấn `F12`.    
3.  Chọn tab Network.    
4.  Tải lại trang bằng `F5`.    
5.  Chọn yêu cầu chính hoặc yêu cầu API cần kiểm tra.  
6.  Quan sát cột Status để xem mã trạng thái HTTP.
## PHẦN 3. KIỂM THỬ

### 1. Trường hợp sửa đúng tên miền nhưng nhận lỗi 404
Nếu Nam sửa đúng tên miền `phong-dieu-phoi.greenlog.vn` nhưng vẫn nhận mã `404 Not Found`, điều đó có nghĩa là trình duyệt đã kết nối và gửi yêu cầu HTTP đến máy chủ hoặc máy chủ trung gian, nhưng tài nguyên được yêu cầu không được tìm thấy.
Nguyên nhân có thể:
-   Đường dẫn trang quản trị bị sai.    
-   Trang quản trị đã bị xóa hoặc đổi địa chỉ.    
-   API hoặc tài nguyên được yêu cầu không tồn tại.    
-   Cấu hình định tuyến trên máy chủ chưa chính xác.    

### 2. Cách xử lý

-   Kiểm tra lại URL và đường dẫn truy cập.    
-   Xác nhận trang quản trị có tồn tại hay không.    
-   Kiểm tra cấu hình Route và API.    
-   Liên hệ bộ phận kỹ thuật nếu đường dẫn chính xác nhưng vẫn bị lỗi.
