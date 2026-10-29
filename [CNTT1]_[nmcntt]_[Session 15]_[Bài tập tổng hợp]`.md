

# PHẦN 1. THIẾT LẬP HYBRID WORKFLOW

### Câu 1. Laptop hỏng ổ cứng có làm mất file mới nhất không?

Nếu nhóm đã thiết lập đúng Hybrid Workflow và bật Auto Sync từ đầu, file đã được đồng bộ thành công lên Cloud thì vẫn có thể khôi phục dù laptop bị hỏng ổ cứng.

Tuy nhiên, nếu file chưa kịp đồng bộ lên Cloud thì vẫn có nguy cơ bị mất. Vì vậy, nhóm cần kiểm tra trạng thái đồng bộ thường xuyên.

### Câu 2. Ba bước thiết lập Auto Sync

**Bước 1:** Cài đặt Google Drive for desktop hoặc ứng dụng Cloud tương ứng trên máy tính.

**Bước 2:** Đăng nhập tài khoản, chọn thư mục dự án SmartCampus và bật tính năng đồng bộ tự động.

**Bước 3:** Đưa các file dự án vào thư mục đã đồng bộ, kiểm tra trạng thái đồng bộ và bảo đảm file đã được tải lên Cloud thành công.

### Câu 3. Khôi phục 2 trang bị xóa nhầm

1. Mở file `BaoCao_CuoiKy_SmartCampus.docx` bằng Google Docs.
2. Chọn **File → Version history → See version history**.
3. Trong bảng lịch sử phiên bản bên phải, chọn phiên bản được lưu trước thời điểm xóa nhầm 2 trang.
4. Nhấn **Restore this version** để khôi phục phiên bản đó.
5. Kiểm tra lại nội dung báo cáo sau khi khôi phục.

**Lưu ý:** Nếu chỉ muốn lấy lại 2 trang bị xóa mà không làm mất những chỉnh sửa khác được thực hiện sau đó, hãy mở phiên bản cũ, sao chép 2 trang cần lấy rồi dán vào phiên bản hiện tại. Cách này giúp giữ lại các chỉnh sửa mới hơn.

### Câu 4. Hai sai lầm khi đồng bộ Cloud

**Sai lầm 1: Đồng bộ thư mục `node_modules`.**

- Vấn đề: Có hàng nghìn file nhỏ, làm quá trình đồng bộ chậm và tốn dung lượng.
- Cách xử lý: Không đồng bộ thư mục này; thêm `node_modules/` vào file `.gitignore` và tạo lại bằng lệnh `npm install` khi cần.

**Sai lầm 2: Đồng bộ các file phim 4K không liên quan đến dự án.**

- Vấn đề: Chiếm nhiều dung lượng Cloud và làm chậm quá trình đồng bộ.
- Cách xử lý: Chuyển các file phim ra khỏi thư mục dự án và chỉ đồng bộ những tài liệu thực sự cần thiết.

---

# PHẦN 2. PHÂN QUYỀN CHIA SẺ AN TOÀN

### Câu 1. Bảng phân quyền cho từng file

| File | Mức quyền | Phạm vi chia sẻ | Giải thích |
|---|---|---|---|
| `BaoCao_CuoiKy_SmartCampus.docx` | Viewer | Restricted | Giảng viên chỉ xem và chấm điểm, không chỉnh sửa nội dung. |
| `Slide_BaoCao.pptx` | Editor | Restricted | Cả 5 thành viên được chỉnh sửa, nhưng chỉ những người được cấp quyền mới truy cập. |
| `GopY_BanNhap.docx` | Commenter | Restricted | Anh khóa trên có thể nhận xét mà không sửa trực tiếp nội dung. |
| `ThongTin_CaNhan_NhomVien.xlsx` | Viewer | Restricted | Chỉ người được ủy quyền xem thông tin cần thiết; không chia sẻ công khai dữ liệu cá nhân. |

**Lưu ý:** Với file chứa CCCD và số điện thoại, chỉ cấp quyền cho những người thực sự cần xử lý thủ tục. Không cấp quyền rộng cho cả nhóm nếu không cần thiết.

### Câu 2. Quy tắc Cờ Đỏ Bảo mật

Quy tắc Cờ Đỏ Bảo mật: Khi tài liệu chứa thông tin nhạy cảm như CCCD, số điện thoại, mật khẩu hoặc khóa API, phải kiểm tra kỹ người nhận và phạm vi chia sẻ trước khi cấp quyền.

Tuyệt đối không kết hợp `Anyone with the link` và `Editor` cho file `ThongTin_CaNhan_NhomVien.xlsx` vì bất kỳ ai có liên kết đều có thể truy cập và chỉnh sửa dữ liệu nếu không có giới hạn bổ sung. Điều này có thể dẫn đến rò rỉ, sửa đổi hoặc sử dụng sai mục đích thông tin cá nhân.

### Câu 3. Hai thao tác trong Settings cho file Slide

Trong cửa sổ Settings của Google Drive, thực hiện:

1. **Tắt “Editors can change permissions and share”** nếu tùy chọn này xuất hiện, nhằm hạn chế Editor tự thay đổi quyền và chia sẻ file cho người khác.
2. **Kiểm tra danh sách người có quyền truy cập và các thông báo hoạt động** để phát hiện những thay đổi chia sẻ bất thường.

Lưu ý: Tên tùy chọn có thể khác nhau tùy ứng dụng và loại tài khoản.

---

# PHẦN 3. TỔ CHỨC GIAO TIẾP NHÓM CHUẨN DOANH NGHIỆP

### Câu 1. Ba vấn đề trong hội thoại Zalo

**Vấn đề 1: No-Hello**

Lan nhắn “có ai rảnh không” mà chưa nói rõ mục đích, khiến người nhận phải hỏi lại mới hiểu vấn đề.

**Vấn đề 2: Tin nhắn không đủ ngữ cảnh**

Các câu như “ơi gì đấy” và “giúp em cái này được không ạ” không nêu rõ công việc, nội dung cần hỗ trợ hoặc thời hạn phản hồi.

**Vấn đề 3: Spam thông báo và giao tiếp thiếu phân luồng**

Tin nhắn `@all` lúc 23:47 gây phiền cho cả nhóm vào giờ khuya. Ảnh mèo và tin nhắn trò chuyện cũng xen lẫn thông tin công việc, khiến việc theo dõi deadline khó khăn.

### Câu 2. Đề xuất các Channel/Topic

- `#thong-bao`: Thông báo deadline, lịch họp và các thông tin quan trọng.
- `#bao-cao`: Trao đổi nội dung báo cáo và tiến độ hoàn thành.
- `#slide-thuyet-trinh`: Chỉnh sửa slide, hình ảnh và nội dung thuyết trình.
- `#giao-luu`: Trò chuyện và chia sẻ nội dung ngoài công việc.

### Câu 3. Viết lại tin nhắn của Lan theo tư duy Asynchronous

> Chào mọi người, mình đang hoàn thiện phần nội dung chương 2 của báo cáo SmartCampus và cần hỗ trợ kiểm tra lỗi trình bày cùng cách diễn đạt. Bạn nào có thể hỗ trợ thì xem giúp file `BaoCao_CuoiKy_SmartCampus.docx` trong thư mục dự án và phản hồi những chỗ cần sửa trước 20:00 ngày mai nhé. Nếu chưa tiện, mọi người có thể phản hồi sau khi đọc được tin nhắn. Cảm ơn mọi người!

Tin nhắn đã nêu rõ mục đích, công việc, tài liệu cần xem và thời hạn nên người nhận có thể trả lời ngay cả khi đọc tin nhắn muộn.

### Câu 4. Viết lại tin nhắn Schedule Send

**Thời gian đặt lịch gửi:** 08:00 sáng hôm sau.

> Chào Nam và Hoa, hiện phần nội dung báo cáo và slide của hai bạn vẫn chưa hoàn thành theo tiến độ nhóm đã thống nhất. Nam vui lòng hoàn thiện phần nội dung báo cáo còn thiếu; Hoa vui lòng hoàn thiện các slide còn thiếu. Hai bạn cập nhật trực tiếp vào thư mục SmartCampus trên Cloud và phản hồi tiến độ trước 10:00 sáng nay để nhóm kịp tổng hợp bản cuối. Nếu có khó khăn, hãy nêu rõ phần đang vướng và thời gian dự kiến hoàn thành nhé.

**Lưu ý:** Chỉ tag Nam và Hoa nếu đã xác nhận hai bạn thực sự còn thiếu phần việc. Lên lịch gửi lúc 08:00 giúp tránh làm phiền thành viên vào ban đêm.

---

# PHẦN 4. THÔNG BÁO TỔNG HỢP TRÊN KÊNH #THONG-BAO

> Chào mọi người, mình đã thiết lập Auto Sync cho thư mục dự án SmartCampus và kiểm tra trạng thái đồng bộ để các thành viên có thể cập nhật file trên Cloud. File `BaoCao_CuoiKy_SmartCampus.docx` đã được chia sẻ cho giảng viên với quyền **Viewer** và phạm vi **Restricted**, bảo đảm giảng viên có thể xem mà không chỉnh sửa trực tiếp. Nam, bạn vui lòng hoàn thiện phần nội dung báo cáo còn thiếu; Hoa, bạn vui lòng hoàn thiện các slide còn thiếu và cập nhật trước 10:00 sáng nay. Nếu gặp khó khăn, hai bạn hãy phản hồi cụ thể trong kênh `#bao-cao` để nhóm phối hợp xử lý. Mọi người trao đổi đúng kênh, trả lời theo thread khi phù hợp và kiểm tra lịch sử phiên bản trước khi khôi phục hoặc thay đổi nội dung nhé. Cảm ơn mọi người!

