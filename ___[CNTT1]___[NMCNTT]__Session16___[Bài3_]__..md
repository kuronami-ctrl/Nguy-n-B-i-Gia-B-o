# PHẦN 1. BÁO CÁO PHÂN TÍCH (I/O)
## 1. Vấn đề
Trong giao diện PTIT-LMS, khung Nội dung bài học đang bị chồng lên khung Danh sách video. Khi kiểm tra bằng F12, các thông số CSS chưa được phân biệt rõ ràng giữa Content, Padding, Border và Margin.
=>> Điều này khiến việc xác định nguyên nhân gây chồng lấn gặp khó khăn
## 2. Yêu cầu

Sử dụng Inspect Element và tab Computed trong DevTools để kiểm tra 4 thành phần của CSS Box Model:
-   Content: Vùng chứa nội dung bên trong phần tử.
-   Padding: Khoảng cách từ nội dung đến đường viền.
-   Border: Đường viền bao quanh phần tử.   
-   Margin: Khoảng cách bên ngoài đường viền, dùng để tạo khoảng cách với phần tử khác.
## 3. Cách làm

Bước 1: Mở DevTools
-   Truy cập giao diện PTIT-LMS.    
-   Nhấn `F12` hoặc `Ctrl + Shift + I`.    
-   Chọn công cụ Inspect Element.    
-   Nhấp vào khung Nội dung bài học.
- 
Bước 2: Kiểm tra tab Computed
-   Chọn tab Computed. 
-   Kéo xuống phần Box Model.    
-   Quan sát các thông số Content, Padding, Border và Margin.   
-   Thực hiện tương tự với khung Danh sách video.    
Sơ đồ CSS Box Model:

          MARGIN                  
          BORDER             
          PADDING          
          CONTENT       
          Nội dung phần tử  
# PHẦN 2. THIẾT KẾ GIẢI PHÁP

## 1. Nguyên nhân có thể gây chồng lấn

Một số nguyên nhân thường gặp:
-   Margin quá nhỏ hoặc bị đặt giá trị âm.    
-   Padding quá lớn làm phần tử chiếm thêm không gian.    
-   Chiều rộng hai khung vượt quá chiều rộng vùng chứa.    
-   Phần tử sử dụng `position: absolute` khiến nó không còn chiếm vị trí thông thường trong bố cục.    
-   Thuộc tính `box-sizing` chưa phù hợp.

Nếu Padding đang quá lớn, chỉ tăng Margin có thể làm khoảng cách giữa hai khung lớn hơn nhưng không giải quyết nguyên nhân gốc. Tổng kích thước phần tử vẫn có thể vượt quá vùng chứa, khiến giao diện bị lệch hoặc xuất hiện thanh cuộn.
## 2. Đề xuất thông số CSS
Thêm màu cho sặc sỡ 





