
# BÁO CÁO PHÂN TÍCH (IPO)

## 1. VẤN ĐỀ

Khi sử dụng Git, người dùng gặp thông báo lỗi:

`fatal: not a git repository (or any of the parent directories): .git`

Người dùng chưa hiểu ý nghĩa của lỗi và chưa biết cách khắc phục.

## 2. YÊU CẦU
Sử dụng mô hình IPO để thiết kế Prompt gửi cho ChatGPT/Gemini, giúp AI giải thích lỗi và hướng dẫn sửa lỗi bằng tiếng Việt.

### Phân tích mô hình IPO
| Thành phần | Nội dung |
|---|---|
| **Input (Đầu vào)** | Ngữ cảnh: Người dùng đang sử dụng Git nhưng chưa biết cách xử lý lỗi. Mã lỗi: `fatal: not a git repository (or any of the parent directories): .git` |
| **Process (Xử lý)** | AI phân tích mã lỗi, xác định nguyên nhân, dịch thông báo sang tiếng Việt và đưa ra các bước khắc phục phù hợp cho người mới học Git. |
| **Output (Đầu ra)** | Bản dịch lỗi và 3 bước hướng dẫn sửa lỗi cụ thể bằng tiếng Việt. |

## 3. CÁCH LÀM

### 3.1. Prompt hoàn chỉnh

Sử dụng công thức: **Ngữ cảnh → Mã lỗi → Yêu cầu**

```text
Ngữ cảnh:
Tôi là người mới học lập trình và đang sử dụng Git trên máy tính.
Tôi chưa có nhiều kiến thức về các lệnh Git.

Mã lỗi:
Khi thực hiện lệnh Git, tôi nhận được thông báo:
"fatal: not a git repository (or any of the parent directories): .git"

Yêu cầu:
1. Dịch thông báo lỗi trên sang tiếng Việt và giải thích ý nghĩa dễ hiểu.
2. Xác định nguyên nhân gây ra lỗi.
3. Hướng dẫn tôi 3 bước sửa lỗi cụ thể, theo thứ tự từ dễ đến khó.
4. Đưa ra câu lệnh Git cần sử dụng và giải thích tác dụng của từng lệnh.
5. Trình bày ngắn gọn, dễ hiểu, phù hợp với người mới học.
```
