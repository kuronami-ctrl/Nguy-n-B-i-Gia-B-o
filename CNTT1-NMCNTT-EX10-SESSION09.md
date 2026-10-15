
## Phần 1. Phân tích và đề xuất

### 1. Phân tích yêu cầu theo mô hình Input – Output

|Thành phần|Nội dung
|-|-|-
|Input (đầu vào)|Câu hỏi về khái niệm Markdown Parser; người hỏi là sinh viên năm nhất PTIT, chưa có nền tảng lập trình
|Yêu cầu xử lý|AI cần hiểu trình độ, xác định độ sâu giải thích, lựa chọn ngôn ngữ phù hợp và đưa ra ví dụ minh họa
|Output (đầu ra)|Một lời giải thích dễ hiểu, đúng khái niệm, phù hợp người mới và có mức độ chi tiết theo yêu cầu
### 2. Ưu điểm và nhược điểm của hai chiến lược
Chiến lược A — Văn xuôi thuần túy
Ưu điểm:
-   Viết nhanh, tự nhiên như trò chuyện thông thường
-   Prompt ngắn, thường tiêu thụ ít token hơn
-   Dễ sử dụng ngay cả với người chưa biết Markdown
Nhược điểm:
-   Các yêu cầu và giới hạn chưa được tách riêng
-   AI có thể hiểu chưa chính xác mức độ chi tiết mong muốn
-   Khó chuẩn hóa để sử dụng lặp lại cho nhiều khái niệm khác nhau

Chiến lược B — Cấu trúc Markdown 3 phần
Ưu điểm:
-   Chia rõ bối cảnh, khái niệm và yêu cầu
-   Giúp AI dễ xác định trình độ người học và định dạng câu trả lời mong muốn
-   Có thể tái sử dụng bằng cách thay tên khái niệm hoặc điều chỉnh yêu cầu
Nhược điểm:
-   Prompt dài hơn, tốn công viết và có thể sử dụng nhiều token hơn
-   Người mới cần học cách tổ chức tiêu đề và nội dung
-   Nếu phân loại thông tin sai phần, yêu cầu có thể trở nên mơ hồ hoặc khó theo dõi
## Phần 2. So sánh và lựa chọn

### 3. Bảng so sánh theo 4 tiêu chí nghiệp vụ
|Tiêu chí|Chiến lược A: Văn xuôi|Chiến lược B: Markdown
|-|-|-
|Độ chính xác|Khá tốt nếu câu hỏi rõ ràng; yêu cầu có thể bị hiểu thiếu|Tốt hơn khi có nhiều yêu cầu cụ thể, được phân chia rõ ràng
|Tiêu thụ Token|Thường ít hơn|Thường nhiều hơn do có tiêu đề và cấu trúc
|Khả năng tái sử dụng|Trung bình, thường phải sửa lại câu hỏi|Cao, dễ thay nội dung trong từng phần
|Dễ học cho người mới|Rất dễ, không cần biết cú pháp|Cần làm quen với tiêu đề `##` và cách phân chia nội dung
### 4. Chốt lựa chọn: Khi nào dùng A, khi nào dùng B?
```
Chọn chiến lược A khi cần hỏi nhanh
Ví dụ: “Token trong AI là gì? Giải thích đơn giản giúp mình.”
Phù hợp khi câu hỏi đơn giản, chỉ cần giải thích ngắn hoặc trao đổi liên tục với AI. Cách này tiết kiệm thời gian viết Prompt.
```
```
Chọn chiến lược B khi cần câu trả lời có tiêu chuẩn rõ ràng
Ví dụ: Ôn thi nhiều khái niệm IT-101, yêu cầu mỗi khái niệm phải có định nghĩa, ví dụ thực tế và giới hạn độ dài.
Phù hợp khi cần câu trả lời nhất quán, có nhiều điều kiện hoặc muốn tái sử dụng Prompt cho nhiều bài học.
```
Đề xuất: Theo em, với sinh viên năm nhất đang học IT , nên ưu tiên chiến lược B khi ôn tập có hệ thống. Tuy nhiên, với câu hỏi đơn giản, chiến lược A vẫn hiệu quả và nhanh hơn.
## Phần 3. Thiết kế và triển khai

### 5. Viết Prompt mẫu để hỏi về khái niệm Token
## Bối cảnh

Tôi là sinh viên năm nhất PTIT, chưa có nền tảng lập trình và đang học môn IT

## Khái niệm cần giải thích
Token trong lĩnh vực AI.
## Yêu cầu

-   Giải thích bằng ngôn ngữ đời thường, dễ hiểu
-   So sánh Token với một vật dụng quen thuộc trong cuộc sống    
-   Nêu một ví dụ cụ thể để minh họa cách một câu văn được chia thành các Token    
-   Trình bày khoảng 100–150 từ    
-   Kết thúc bằng một câu tóm tắt giúp tôi dễ ghi nhớ.    
## Không cần
-   Thuật ngữ kỹ thuật phức tạp.    
-   Công thức toán học hoặc kiến thức lập trình nâng cao.
