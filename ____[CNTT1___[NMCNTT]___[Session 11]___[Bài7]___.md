
## Phần 1. Phân tích lỗi

### 1. Vì sao định dạng thủ công khiến Auto TOC không hoạt động?

Nguyên nhân chính: Các tiêu đề chỉ được định dạng về hình thức như in đậm, đổi cỡ chữ, tô màu, nhưng chưa được gán đúng kiểu tiêu đề Heading 1, Heading 2 hoặc Heading 3.

Word phân biệt hai loại định dạng:

-   Manual Formatting (định dạng thủ công): Chỉ thay đổi hình thức bên ngoài như cỡ chữ, màu chữ, in đậm, tô vàng.
    
-   Heading Styles (kiểu tiêu đề): Gán nhãn cấu trúc cho đoạn văn, giúp Word nhận biết đâu là chương, mục con và chi tiết nhỏ hơn.
    

Khi tạo mục lục tự động, Word dựa vào các cấp Heading được thiết lập để tìm và sắp xếp tiêu đề. Vì vậy, một dòng chữ dù in đậm, cỡ 16 và tô vàng nhưng vẫn mang kiểu `Normal` thì thông thường sẽ không được nhận diện là tiêu đề trong mục lục.

### Phân tích lỗi của cả 7 dòng tiêu đề
|Dòng tiêu đề|Lỗi hiện tại|Cấp đúng cần gán
|-|-|-
|1. Thông tin chung hội nghị|Chỉ định dạng thủ công|Heading 1
|1.1. Tên hội nghị|Normal + in đậm + cỡ 14|Heading 2
|1.2. Thời gian & địa điểm|1.2. Thời gian & địa điểm|Heading 2
|2. Cơ cấu ban tổ chức|Chỉ định dạng thủ công|Heading 1
|2.1. Ban Nội dung|Normal + cỡ 13 + màu xanh|Heading 2
|2.1.1. Tiểu ban Kỹ thuật|Đang gán Heading 3, cần kiểm tra cấp theo yêu cầu|Heading 3
|3. Lịch trình sự kiện|Normal, chưa có kiểu tiêu đề|Heading 1


### Cơ chế Word quét tiêu đề

Các đoạn văn trong tài liệu Word
<center>↓</center>
Word kiểm tra nhãn Heading 1, Heading 2, Heading 3
<center>↓</center>
Sắp xếp theo cấp tiêu đề và lấy số trang
<center>↓</center>
Tạo mục lục tự động (Auto TOC)
<center>↓</center>

### 2. Vì sao gán sai cấp Heading làm mục lục thụt đầu dòng sai?

Word sử dụng cấp Heading để thể hiện quan hệ giữa tiêu đề chính và tiêu đề con.

-   Heading 1: Cấp chương, thường nằm sát lề trái.
    
-   Heading 2: Cấp mục con, thụt vào sâu hơn Heading 1.
    
-   Heading 3: Cấp chi tiết, thụt vào sâu hơn Heading 2.
    

Ví dụ:

Mục lục đúng:

1. Thông tin chung hội nghị
1.1. Tên hội nghị
1.2. Thời gian & địa điểm
2. Cơ cấu ban tổ chức
2.1. Ban Nội dung
2.1.1. Tiểu ban Kỹ thuật
3. Lịch trình sự kiện


## Phần 2. Sửa lỗi và nghiệm thu

### 3. Các bước sửa đúng cấu trúc Heading cho 7 dòng

Bước 1: Xác định dòng tiêu đề cần sửa

Mở file Word, tìm lần lượt 7 dòng tiêu đề trong bảng đề bài.

Bước 2: Gán Heading đúng cấp

|Dòng tiêu đề|Phím tắt|Kiểu sau khi sửa
|-|-|-
|1. Thông tin chung hội nghị|Ctrl + Alt + 1|Heading 1
|1.1. Tên hội nghị|Ctrl + Alt + 2|Heading 2
|1.2. Thời gian & địa điểm|Ctrl + Alt + 2|Heading 2
|2. Cơ cấu ban tổ chức	|Ctrl + Alt + 1|Heading 1
|2.1. Ban Nội dung|Ctrl + Alt + 2|Heading 2
|2.1.1. Tiểu ban Kỹ thuật|Ctrl + Alt + 3|Heading 3
|3. Lịch trình sự kiện|Ctrl + Alt + 1|Heading 1
Bước 3: Kiểm tra kiểu tiêu đề
-   Chọn từng dòng tiêu đề.
   
-   Vào tab Home → Styles.
 
-   Kiểm tra dòng chính hiển thị `Heading 1`, `Heading 2` hoặc `Heading 3` đúng yêu cầu.
    
-   Không sử dụng `Ctrl + Shift + N` trên các tiêu đề đã sửa, vì phím tắt này đưa đoạn văn về kiểu `Normal`.
    

Bước 4: Chèn mục lục tự động

1.  Đặt con trỏ tại vị trí muốn tạo mục lục ở trang đầu.
    
2.  Mở tab References.
    
3.  Chọn Table of Contents.
    
4.  Chọn một mẫu Automatic Table.
    

Nếu cần hiển thị đủ ba cấp, vào References → Table of Contents → Custom Table of Contents, đặt `Show levels` thành `3`, sau đó nhấn OK.

### Kết quả nghiệm thu

Mục lục phải có đủ các cấp sau:

-   Cấp 1: 1. Thông tin chung hội nghị; 2. Cơ cấu ban tổ chức; 3. Lịch trình sự kiện.
    
-   Cấp 2: 1.1. Tên hội nghị; 1.2. Thời gian & địa điểm; 2.1. Ban Nội dung.
    
-   Cấp 3: 2.1.1. Tiểu ban Kỹ thuật.
    

Các tiêu đề cần được thụt đầu dòng theo đúng cấp và có số trang tương ứng.

### 4. Bẫy dữ liệu: Tiêu đề chuyển từ trang 2 sang trang 4

Không, mục lục có thể vẫn hiển thị số trang cũ nếu bạn chưa cập nhật mục lục sau khi nội dung thay đổi.

Cách sửa:

1.  Nhấp chuột vào vùng mục lục.
    
2.  Nhấn phím `F9`.
    
3.  Khi Word hiện hộp thoại cập nhật, chọn một trong hai lựa chọn:
    
    -   Update page numbers only: Chỉ cập nhật số trang.
        
    -   Update entire table: Cập nhật toàn bộ mục lục, gồm tiêu đề, cấp Heading và số trang.
        
    
4.  Nhấn OK.
    

Trong trường hợp chỉ chuyển trang mà không thay đổi tiêu đề, chọn Update page numbers only là đủ. Nếu vừa thêm, xóa hoặc đổi tên tiêu đề, nên chọn Update entire table.
