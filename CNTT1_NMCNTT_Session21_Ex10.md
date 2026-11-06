# VOLTCHARGE – PHÂN TÍCH QUY TRÌNH TROUBLESHOOTING

## PHẦN 1. BẢNG SO SÁNH TRADE-OFF TOÀN DIỆN

### 1.1. So sánh hai phương án

| Tiêu chí | Phương án 1: Hỗ trợ cảm tính / Nhóm Chat | Phương án 2: Troubleshooting 4 Chặng |
|---|---|---|
| **1. Thời gian xử lý sự cố (Downtime)** | Kéo dài vì KTV phải chờ Senior Dev phản hồi. Trạm sạc có thể ngừng hoạt động trong thời gian dài. | Rút ngắn thời gian xử lý nhờ KTV chủ động tìm kiếm và khắc phục lỗi trong 5–10 phút đầu. |
| **2. Áp lực và chi phí cho Senior Dev** | Rất cao vì Senior Dev liên tục bị làm phiền bởi những lỗi cơ bản và câu hỏi lặp lại. | Tối ưu vì Senior Dev chỉ tiếp nhận các lỗi phức tạp đã có Bug Report đầy đủ. |
| **3. Năng lực và tính tự chủ của KTV** | Thụ động, phụ thuộc vào người khác, thiếu kỹ năng phân tích và xử lý sự cố. | Chủ động, nâng cao khả năng phân tích, tra cứu và tự khắc phục lỗi. |
| **4. Khả năng lưu trữ tri thức (Knowledge Base)** | Thấp. Thông tin sửa lỗi bị trôi trong nhóm Zalo/Telegram, khó tìm lại khi gặp lỗi cũ. | Cao. Các lỗi và cách khắc phục được lưu trữ tập trung thành tài liệu Wiki nội bộ. |

### 1.2. Kết luận lựa chọn

Ban Giám đốc VoltCharge bắt buộc nên chọn **Phương án 2 – Troubleshooting 4 Chặng Chuẩn hóa** nếu muốn mở rộng từ 100 lên 1.000 trạm sạc.

Lý do:

- **Giảm thiệt hại kinh tế:** Mỗi giờ một trụ sạc ngừng hoạt động gây thiệt hại 500.000 VNĐ. Xử lý sự cố nhanh giúp giảm Downtime và tiết kiệm chi phí.
- **Giảm áp lực cho Senior Dev:** Kỹ sư cấp cao có thêm thời gian phát triển tính năng mới thay vì xử lý các lỗi cơ bản lặp lại.
- **Nâng cao năng lực KTV:** Kỹ thuật viên có khả năng tự phân tích và xử lý sự cố, không phụ thuộc hoàn toàn vào tổng bộ.
- **Xây dựng Knowledge Base:** Các lỗi đã xử lý được lưu lại để những kỹ thuật viên khác có thể tham khảo và áp dụng.

**Kết luận:** Phương án 1 có thể giải quyết nhanh một số tình huống trước mắt nhưng không phù hợp khi mở rộng quy mô. Phương án 2 giúp VoltCharge xây dựng đội ngũ kỹ thuật tự chủ, giảm chi phí vận hành và duy trì hoạt động ổn định khi phát triển lên 1.000 trạm sạc.

---

## PHẦN 2. THIẾT KẾ SƠ ĐỒ LUỒNG RA QUYẾT ĐỊNH (DECISION FLOWCHART)

### 2.1. Sơ đồ xử lý sự cố

```text
          [KIOSK XUẤT HIỆN ERROR POP-UP]
                         |
                         v
       +-----------------------------------+
       | CHẶNG 1: BÓC TÁCH TỪ KHÓA         |
       | - Ghi lại mã lỗi                  |
       | - Tìm kiếm bằng Google Operators  |
       | - Sử dụng site:, dấu ngoặc kép, - |
       +-----------------------------------+
                         |
                         v
       +-----------------------------------+
       | CHẶNG 2: KIỂM TRA KẾT QUẢ         |
       | - Tìm StackOverflow/GitHub Issues |
       | - Đọc lướt trong 30 giây          |
       | - Kiểm tra Upvote và dấu ✓        |
       +-----------------------------------+
                         |
                  Có hướng dẫn?
                    /       \
                  Có         Không
                  |            |
                  v            v
        [Thử giải pháp]  [Chuyển sang Chặng 3]
                  |            |
                  v            |
           Đã sửa được?        |
             /    \            |
           Có      Không       |
           |         |         |
           v         +---------+
        [Kết thúc]             |
                              v
       +-----------------------------------+
       | CHẶNG 3: HỎI TRỢ LÝ AI             |
       | Prompt gồm 3 thành phần:          |
       | 1. Ngữ cảnh                       |
       | 2. Mã lỗi nguyên văn              |
       | 3. Yêu cầu giải thích và sửa lỗi  |
       +-----------------------------------+
                         |
                         v
       +-----------------------------------+
       | Thử tối đa 2 giải pháp AI đề xuất |
       +-----------------------------------+
                         |
                  Đã sửa được?
                    /       \
                  Có         Không
                  |            |
                  v            v
              [Kết thúc]  [Kiểm tra thời gian]
                               |
                               v
                    Đã quá 15 phút?
                       /       \
                     Chưa       Rồi
                      |          |
                      v          v
                Tiếp tục thử  CHẶNG 4
                trong giới hạn     |
                                   v
       +-----------------------------------+
       | LẬP BUG REPORT GỬI IT HELPDESK    |
       | - Mô tả lỗi                       |
       | - Các bước tái hiện               |
       | - Kết quả đã thử                  |
       | - Ảnh chụp và thông tin hệ thống  |
       +-----------------------------------+
                         |
                         v
                [SENIOR / IT TIẾP NHẬN]
                         |
                         v
                  [XỬ LÝ SỰ CỐ]
                         |
                         v
               [CẬP NHẬT WIKI NỘI BỘ]
