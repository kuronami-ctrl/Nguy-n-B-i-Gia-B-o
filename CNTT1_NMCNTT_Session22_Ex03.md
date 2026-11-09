
## 1. YÊU CẦU

- Phân tích tình huống theo mô hình IPO gồm Input, Process và Output.
- Biết cách kiểm tra câu lệnh do AI cung cấp bằng Google.
- Sử dụng trang StackOverflow hoặc trang chủ Python để kiểm tra thông tin.
- Viết một câu hỏi yêu cầu AI giải thích độ an toàn của câu lệnh trước khi thực hiện.

## 2. VẤN ĐỀ

Khi cài đặt Python, máy tính xuất hiện lỗi "Path not found".

Tôi hỏi AI cách khắc phục và nhận được một câu lệnh để dán vào Terminal. Tuy nhiên, câu lệnh này trông lạ và có thể làm thay đổi cài đặt của máy tính.

AI đôi khi có thể đưa ra thông tin sai hoặc câu lệnh không phù hợp với phiên bản Windows đang sử dụng. Hiện tượng này được gọi là AI Hallucination (AI đưa ra thông tin không chính xác nhưng có vẻ hợp lý).

## 3. CÁCH LÀM

### a. Phân tích theo mô hình IPO

**Input (Đầu vào):**
- Lỗi "Path not found" khi cài đặt Python.
- Câu lệnh do AI đề xuất để sửa lỗi.

**Process (Xử lý):**
- Đọc kỹ câu lệnh AI đưa ra.
- Tìm kiếm câu lệnh trên Google bằng cách sử dụng:

`site:stackoverflow.com "tên câu lệnh"`

- Kiểm tra thêm trên trang chủ Python: https://www.python.org/
- So sánh hướng dẫn tìm được với phiên bản Windows và Python đang sử dụng.
- Không chạy câu lệnh nếu chưa hiểu tác dụng hoặc không tìm được nguồn đáng tin cậy.

**Output (Đầu ra):**

Sau khi kiểm tra, đưa ra một trong hai kết luận:

- **An toàn:** Câu lệnh có nguồn đáng tin cậy, đúng với phiên bản đang sử dụng và đã hiểu rõ tác dụng.
- **Không an toàn hoặc chưa xác định:** Không tìm được nguồn xác nhận, câu lệnh có thể ảnh hưởng đến hệ thống hoặc chưa hiểu rõ cách hoạt động. Không thực hiện câu lệnh đó.

### b. Thiết kế câu hỏi hỏi ngược lại AI (Prompt)

Tôi sẽ sử dụng câu hỏi sau để yêu cầu AI giải thích trước khi thực hiện:

"Bạn vừa đưa ra câu lệnh để sửa lỗi Path not found khi cài đặt Python. Hãy giải thích rõ:

1. Câu lệnh này có tác dụng gì?
2. Câu lệnh có làm thay đổi hoặc xóa dữ liệu trên máy tính không?
3. Câu lệnh có phù hợp với Windows 11 và phiên bản Python tôi đang sử dụng không?
4. Có cách sửa lỗi nào đơn giản và an toàn hơn không?
5. Hãy cung cấp nguồn hướng dẫn chính thức để tôi kiểm tra.

Tôi là sinh viên mới học lập trình, hãy giải thích bằng từ ngữ đơn giản và không yêu cầu tôi chạy lệnh khi chưa hiểu rõ tác dụng."

### c. Nguyên tắc thực hiện

- Không sao chép và chạy ngay câu lệnh do AI cung cấp.
- Kiểm tra thông tin từ trang chủ phần mềm hoặc nguồn đáng tin cậy.
- Không chạy lệnh lạ với quyền quản trị viên khi chưa hiểu rõ.
- Sao lưu dữ liệu quan trọng trước khi thực hiện những thay đổi lớn.

