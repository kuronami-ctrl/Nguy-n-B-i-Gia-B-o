# SỬA LỖI CHỒNG LẤN GIAO DIỆN BẰNG CSS BOX MODEL

## PHẦN 1. PHÂN TÍCH

### 1. Định vị phần tử bị lỗi bằng Inspect Element

Thực hiện các bước:

1. Mở giao diện "Theo dõi lộ trình xe".
2. Nhấn `F12` để mở Developer Tools.
3. Chọn tab **Elements**.
4. Nhấn biểu tượng Inspect Element.
5. Click vào khung "Thông tin tài xế" đang bị chồng lấn.
6. Quan sát thẻ HTML tương ứng trong cây DOM Tree.
7. Kiểm tra các thuộc tính CSS trong tab **Styles** và **Computed**.

Mục đích: Xác định chính xác phần tử gây ra lỗi chồng lấn giữa hai khung.

### 2. Phân tích CSS Box Model

CSS Box Model gồm 4 lớp:

- **Content:** Vùng chứa nội dung bên trong phần tử.
- **Padding:** Khoảng cách giữa nội dung và đường viền.
- **Border:** Đường viền bao quanh phần tử.
- **Margin:** Khoảng cách bên ngoài đường viền, giúp tách phần tử với các thành phần khác.

Sơ đồ Box Model:

```text
+--------------------------------------+
|               MARGIN                 |
|  +--------------------------------+  |
|  |             BORDER             |  |
|  |  +--------------------------+  |  |
|  |  |         PADDING          |  |  |
|  |  |  +--------------------+  |  |  |
|  |  |  |      CONTENT       |  |  |  |
|  |  |  +--------------------+  |  |  |
|  |  +--------------------------+  |  |
|  +--------------------------------+  |
+--------------------------------------+
```
### 3. Sơ đồ lỗi hiện tại

Giả sử phần tử "Thông tin tài xế" đang có Margin âm khiến hai khung bị chồng lấn:
+-------------------------+
|   THÔNG TIN TÀI XẾ      |
+-------------------------+
          |
          | Margin âm
          v
+-------------------------+
|   DANH SÁCH TRẠM        |
+-------------------------+
Khi kiểm tra tab Computed, cần quan sát các thông số:
-   Width và Height.   
-   Padding.    
-   Border.    
-   Margin. 
-   Box-sizing.  
-   Position và các thuộc tính liên quan.
- ## PHẦN 2. TRIỂN KHAI

### 1. Đề xuất thông số CSS mới

em không rõ phần này ạ
### 3. Cách áp dụng trong DevTools

1.  Chọn phần tử trong tab Elements.
    
2.  Mở tab Styles.
    
3.  Thêm hoặc chỉnh sửa các thuộc tính CSS.
    
4.  Quan sát giao diện sau mỗi lần thay đổi.
    
5.  Kiểm tra lại khoảng cách giữa hai khung.
## PHẦN 3. KIỂM THỬ

### 1. Tình huống

Đã thay đổi Margin nhưng phần tử vẫn không di chuyển.

### 2. Nguyên nhân cần kiểm tra

Có thể thuộc tính CSS đang bị ghi đè bởi:

-   Quy tắc CSS khác có độ ưu tiên cao hơn.
    
-   Thuộc tính `!important`.
    
-   Thuộc tính `position: absolute` hoặc `position: fixed`.
    
-   Thuộc tính `transform` đang dịch chuyển phần tử.
    
-   Quy tắc CSS của Browser hoặc User Agent Stylesheet.
    

### 3. Cách kiểm tra và xử lý

1.  Mở tab Styles.
    
2.  Tìm thuộc tính `margin` đang áp dụng.
    
3.  Quan sát xem thuộc tính có bị gạch ngang hay không.
    
4.  Nếu bị gạch ngang, kiểm tra quy tắc CSS nào đang ghi đè.
    
5.  Kiểm tra thêm `position`, `top`, `left`, `transform` và `!important`.
    
6.  Thử bỏ chọn thuộc tính gây xung đột hoặc chỉnh sửa trực tiếp trong Styles.
