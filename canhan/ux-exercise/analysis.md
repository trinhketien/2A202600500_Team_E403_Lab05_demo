# Bài tập UX: Phân tích sản phẩm AI thật

> **Sinh viên:** Trịnh Kế Tiến — **MSSV:** 2A202600500  
> **Sản phẩm phân tích:** MoMo — Trợ thủ AI Moni  
> **Ngày:** 08/04/2026

---

## 1. Phân tích 4 Paths (Hành trình người dùng)

### ✅ Luồng Đúng (Happy Path)
* **User:** *"thg trck toi dung tiene vao viec gi"* (Cố tình gõ sai chính tả/viết tắt).
* **Moni:** Hiểu đúng 100% là hỏi chi tiêu tháng trước. Trả lời đầy đủ số tiền, số giao dịch.
* **$\rightarrow$ Kết luận:** Xử lý ngôn ngữ tự nhiên (NLP) cực tốt, chịu được nhiễu.

### 🔍 Luồng Không chắc (Clarify) — ĐIỂM YẾU
* **User:** *"Tôi vừa chuyển 500k"*.
* **Moni:** Tự động gán luôn vào mục "Ăn uống" mà không hỏi lại.
* **$\rightarrow$ Kết luận:** Lỗi UX nghiêm trọng. Thiếu bước xác nhận (Clarify) dẫn đến sai lệch dữ liệu tài chính.

### ⚠️ Luồng Sai (Error/Fix)
* **User:** Nhập ký tự rác *"idjdbdjkwbx"*.
* **Moni:** *"Moni chưa hiểu ý bạn..."* và liệt kê các nút tính năng có sẵn để điều hướng user quay lại đúng luồng.
* **$\rightarrow$ Kết luận:** Xử lý lỗi (Error Handling) tốt, không để user bị "treo".

### ❌ Luồng Mất tin (Exit/Fallback)
* **User:** *"Dự đoán giá vàng ngày mai"*.
* **Moni:** Từ chối vì không có công cụ dự báo, chỉ gợi ý nguồn uy tín (SJC, DOJI) và khuyên người dùng tỉnh táo.
* **$\rightarrow$ Kết luận:** Chặn rủi ro kiểm soát thông tin mù mờ và bảo vệ uy tín thương hiệu rất tốt.

---

## 2. Sketch cải thiện (To-be) cho luồng Clarify

*(Phần này tham chiếu đến hình vẽ 2 khung hình điện thoại mặt đối mặt trên giấy)*

| As-Is (Hiện tại) | To-Be (Đề xuất cải thiện) |
|------------------|---------------------------|
| **User:** *"Tôi vừa chuyển 500k"* | **User:** *"Tôi vừa chuyển 500k"* |
| **Moni:** *"Đã ghi nhận 500.000đ vào mục Ăn uống"* | **Moni:** *"Moni đã nhận tin. Khoản này thuộc mục nào vậy?"* |
| *(Mũi tên chỉ vào chữ "Ăn uống")* | *(3 nút bấm (Chips) dưới câu trả lời của Bot):* <br> `[Ăn uống]` `[Tiền nhà]` `[Mục khác...]` |
| **Ghi chú:** ❌ AI tự ý đoán mò, gây sai lệch data. | **Ghi chú:** ✅ **Quick-Tagging.** AI dự đoán nhưng để user chọn bằng 1 chạm thay vì tự quyết định. |

---

## 3. Kết luận cuối cùng

> "Giải pháp cải thiện tập trung vào việc bổ sung luồng Clarify (Xác nhận) thông qua các nút gợi ý nhanh (Quick-reply chips). Điều này giúp AI Moni vừa giữ được sự thông minh, vừa đảm bảo tính chính xác tuyệt đối cho dữ liệu tài chính của người dùng."

---

## 4. Minh chứng (Screenshots)

 Dưới đây là bản vẽ sketch (compare) và các hình ảnh chụp lại quá trình thử nghiệm thực tế với tính năng Trợ thủ AI Moni trên ứng dụng MoMo:

![Bản vẽ Compare (As-Is vs To-Be)](file:///d:/Antigravity/AI_thucchien/Day-05-AI-Product-Thinking/canhan/ux-exercise/screenshots/compare.jpg)
![Test Screenshot 1](file:///d:/Antigravity/AI_thucchien/Day-05-AI-Product-Thinking/canhan/ux-exercise/screenshots/momo_analysis_1.jpg)
![Test Screenshot 2](file:///d:/Antigravity/AI_thucchien/Day-05-AI-Product-Thinking/canhan/ux-exercise/screenshots/momo_analysis_2.jpg)
![Test Screenshot 3](file:///d:/Antigravity/AI_thucchien/Day-05-AI-Product-Thinking/canhan/ux-exercise/screenshots/momo_analysis_3.jpg)
![Test Screenshot 5](file:///d:/Antigravity/AI_thucchien/Day-05-AI-Product-Thinking/canhan/ux-exercise/screenshots/momo_analysis_5.jpg)

---
*Môn học: AI Thực Chiến — Day 5*
