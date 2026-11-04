# SESSION: PASSWORD MANAGER – ZERO-KNOWLEDGE ARCHITECTURE

## 1. VẤN ĐỀ

PixelForge Studio có hơn 40 tài khoản dịch vụ quan trọng nhưng nhân viên đang sử dụng mật khẩu trùng lặp, lưu mật khẩu trên Chrome và chưa có cơ chế quản lý tập trung.

Điều này tạo ra 3 rủi ro chính:
- **Rò rỉ mật khẩu:** Nếu máy tính nhiễm Infostealer, mã độc có thể tìm cách lấy thông tin đăng nhập được lưu trong trình duyệt.
- **Credential Stuffing:** Hacker sử dụng mật khẩu bị lộ từ website khác để thử đăng nhập vào GitHub, AWS hoặc Steamworks.
- **Hiệu ứng Domino:** Một mật khẩu bị lộ có thể khiến nhiều tài khoản khác bị chiếm quyền.
### Câu 1. Vì sao lưu mật khẩu trên Chrome nguy hiểm?

Chrome lưu thông tin đăng nhập trong cơ sở dữ liệu có tên `Login Data`.

Mặc dù dữ liệu mật khẩu được bảo vệ bằng cơ chế mã hóa của hệ điều hành, Infostealer vẫn có thể tìm cách đánh cắp dữ liệu trình duyệt, khai thác phiên đăng nhập hoặc lấy thông tin xác thực khi người dùng đang sử dụng máy tính.

**Hậu quả:**

- Mất mật khẩu tài khoản cá nhân và công việc.
- Bị đánh cắp Cookie hoặc phiên đăng nhập.
- Hacker có thể truy cập GitHub, AWS và các dịch vụ quan trọng.
- Gây thiệt hại cho toàn bộ hệ thống công ty.

**Kết luận:** Không nên phụ thuộc vào trình duyệt để quản lý tập trung mật khẩu của tổ chức.

### Câu 2. Kiến trúc Zero-Knowledge và Client-side Decryption

**Zero-Knowledge Architecture** là kiến trúc trong đó nhà cung cấp dịch vụ không biết Master Password và không thể tự giải mã dữ liệu trong két sắt của người dùng.

Cơ chế hoạt động:

1. Người dùng nhập Master Password trên thiết bị.
2. Ứng dụng Bitwarden sử dụng mật khẩu này để tạo khóa mã hóa.
3. Dữ liệu trong két sắt được mã hóa ngay trên thiết bị khách.
4. Dữ liệu đã mã hóa mới được đồng bộ lên máy chủ.
5. Khi cần sử dụng, thiết bị tải dữ liệu mã hóa về và giải mã cục bộ.

**Client-side Decryption:** Quá trình giải mã diễn ra trên thiết bị của người dùng, không phải trên máy chủ của nhà cung cấp.

**Nếu máy chủ Bitwarden bị hacker tấn công:**

- Hacker có thể lấy được dữ liệu két sắt đã mã hóa.
- Hacker không thể trực tiếp đọc mật khẩu nếu không có khóa giải mã.
- Tuy nhiên, nếu Master Password yếu, thiết bị người dùng bị nhiễm mã độc hoặc khóa giải mã bị đánh cắp thì dữ liệu vẫn có nguy cơ bị lộ.

**Kết luận:** Zero-Knowledge giúp bảo vệ dữ liệu ngay cả khi máy chủ bị xâm nhập, nhưng không thay thế việc bảo vệ thiết bị và Master Password.

---

## 2. YÊU CẦU

PixelForge Studio cần xây dựng chính sách quản lý mật khẩu thống nhất với các nguyên tắc:

1. Sử dụng Bitwarden làm Password Manager tập trung.
2. Mỗi tài khoản phải có một mật khẩu riêng biệt.
3. Mật khẩu được tạo ngẫu nhiên, dài từ 16–32 ký tự.
4. Sử dụng Master Passphrase mạnh để bảo vệ két sắt.
5. Bật xác thực hai yếu tố (2FA).
6. Thiết lập quy trình lưu trữ và khôi phục Emergency Kit.
7. Không lưu mật khẩu hoặc Token trực tiếp trong mã nguồn GitHub.

---

## 3. CÁCH LÀM

### Câu 3. Tạo Master Passphrase

**Yêu cầu:**

- Dài tối thiểu 20 ký tự.
- Dễ nhớ nhưng khó đoán.
- Không sử dụng tên, ngày sinh hoặc thông tin cá nhân.
- Không dùng lại mật khẩu đã từng sử dụng.

**Phương pháp đề xuất:**

Sử dụng 5–6 từ ngẫu nhiên, không liên quan đến nhau, kết hợp thành một cụm từ dài.

Ví dụ minh họa:

`River-Cactus-Moon-Train-Orange-Cloud`

Đây chỉ là ví dụ để hiểu cách tạo Passphrase, không nên sử dụng nguyên văn làm mật khẩu thật.

**Lưu ý:** Nên chọn từ ngẫu nhiên bằng phương pháp an toàn như Diceware. Độ mạnh đến từ tính ngẫu nhiên và số lượng từ, không chỉ từ việc thêm ký tự đặc biệt.

### Câu 4. Cấu hình Generator trong Bitwarden

Thiết lập bộ sinh mật khẩu thống nhất cho 40 tài khoản:

| Thuộc tính | Cấu hình đề xuất |
|---|---|
| Loại mật khẩu | Password |
| Độ dài | 24 ký tự |
| Chữ hoa | Bật (A–Z) |
| Chữ thường | Bật (a–z) |
| Chữ số | Bật (0–9) |
| Ký tự đặc biệt | Bật (!, @, #, $, %) |
| Loại trừ ký tự dễ nhầm | Tùy chọn |
| Tránh mật khẩu trùng lặp | Tạo mật khẩu mới cho từng tài khoản |

**Cách thực hiện:**

1. Mở Bitwarden.
2. Chọn Tools → Generator.
3. Chọn Password.
4. Đặt độ dài 24 ký tự.
5. Bật chữ hoa, chữ thường, chữ số và ký tự đặc biệt.
6. Nhấn Generate để tạo mật khẩu.
7. Lưu mật khẩu vào đúng mục tài khoản trong Vault.

**Nguyên tắc:** Một tài khoản – Một mật khẩu duy nhất. Không sử dụng lại mật khẩu giữa GitHub, AWS, Steamworks và các dịch vụ khác.

### Câu 5. Vì sao Auto-fill giúp chống Phishing?

Bitwarden có khả năng đối chiếu địa chỉ website với URI đã lưu trong mục đăng nhập.

Ví dụ:

| Website | Kết quả |
|---|---|
| `github.com` | Khớp tên miền đã lưu |
| `githúb.com` | Tên miền giả mạo, không khớp |
| `steampowered.xyz` | Không khớp với `steampowered.com` |

**Cơ chế bảo vệ:**

1. Người dùng truy cập website.
2. Bitwarden kiểm tra địa chỉ website hiện tại.
3. Bitwarden đối chiếu với URI của tài khoản đã lưu.
4. Nếu tên miền không khớp, Bitwarden không tự động điền thông tin đăng nhập theo quy tắc khớp chính xác.

**Lợi ích:**

- Hạn chế nhập mật khẩu vào website giả mạo.
- Giảm nguy cơ bị đánh cắp thông tin đăng nhập.
- Giúp người dùng không phải tự ghi nhớ và kiểm tra mọi tên miền.

Lưu ý: Cần cấu hình chế độ khớp URI phù hợp, ưu tiên khớp chính xác tên miền. Không nên bỏ qua cảnh báo hoặc tự điền mật khẩu vào website đáng ngờ.

### Câu 6. Quy trình lưu trữ Emergency Kit

**Mục đích:** Đảm bảo Trưởng nhóm có thể khôi phục quyền truy cập khi Trưởng phòng Kỹ thuật gặp sự cố.

**Quy trình thực hiện:**

1. Thiết lập cơ chế khôi phục tài khoản hoặc tổ chức trên Bitwarden.
2. Cấu hình quyền quản trị và người được phép thực hiện khôi phục.
3. Tạo tài liệu Emergency Kit chứa thông tin khôi phục cần thiết.
4. In tài liệu và lưu trong phong bì niêm phong.
5. Giao cho người có trách nhiệm quản lý, ví dụ Trưởng nhóm.
6. Lưu tại két an toàn hoặc nơi bảo quản được kiểm soát.
7. Kiểm tra định kỳ khả năng khôi phục và cập nhật khi có thay đổi.

**Nguyên tắc bảo mật:**

- Không gửi Master Password qua email hoặc nhóm chat.
- Không lưu Emergency Kit dưới dạng văn bản công khai trên GitHub.
- Chỉ người được ủy quyền mới được sử dụng thông tin khôi phục.
- Ghi nhận người mở phong bì và thời điểm sử dụng.
- Không chia sẻ thông tin khôi phục rộng rãi cho toàn bộ nhân viên.

