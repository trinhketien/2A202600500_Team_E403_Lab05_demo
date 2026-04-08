---
theme: default
class: text-center
highlighter: shiki
lineNumbers: false
---

# 🤖 Trợ lý Nhân sự Nội bộ (HR/IT Helpdesk AI)
### Giải pháp tự động hóa Q&A cho Doanh nghiệp
**Nhóm 30 (Phòng E403)**

---

# 1. Nỗi đau của Doanh nghiệp (The Pain)

- **Vấn đề:** Phòng HR/IT luôn trong tình trạng quá tải vì phải trả lời lặp đi lặp lại những câu hỏi cơ bản của nhân viên (Ví dụ: "Nghỉ thai sản mấy tháng?", "Thưởng Tết bao nhiêu?", "Reset pass ở đâu?").
- **Hệ lụy:** Nhân viên phải chờ đợi lâu để được giải đáp, gây ức chế. HR/IT mất quá nhiều thì giờ (hàng trăm giờ mỗi tháng) thay vì làm việc chiến lược.

---

# 2. Giải pháp: Internal RAG Chatbot (The Value)

- 💡 **Sản phẩm:** Chatbot túc trực 24/7 tích hợp thẳng vào Slack/Teams nội bộ.
- 💡 **Cách thức:** Nhân viên hỏi -> AI truy xuất Sổ tay Nhân sự (PDF) -> AI trả lời ngay lập tức.
- 💡 **Tốc độ:** Từ việc "Chờ HR duyệt 2 tiếng", nay chỉ mất **2 giây** để có câu trả lời.
- 💡 **Ưu điểm Cốt lõi (Moat):** Data hoàn toàn bảo mật nội bộ, ChatGPT ngoài kia không thể biết chính sách riêng của công ty chúng ta.

---

# 3. Phân tích Rủi ro & Giải pháp (Designing for Uncertainty)

Vì đây là môi trường doanh nghiệp (bảo mật/lương thưởng), hậu quả của việc **AI tư vấn sai (Hallucination)** là cực kỳ nghiêm trọng (nhân viên biểu tình, kiện cáo).

<div class="grid grid-cols-2 gap-4">
<div>

**Rủi ro AI (Failure Modes)**
- ❌ **Path 3 (Hallucination):** AI bịa ra mức thưởng Tết gấp đôi.
- ❌ **Path 4 (Tức giận):** AI từ chối trả lời khiến user bực mình.
- ❌ **Data Leakage:** Lộ bảng lương của sếp khi trả lời NV.

</div>
<div>

**Mitigation (Bảo vệ người dùng)**
- ✅ Bắt buộc hiển thị **Thẻ Trích dẫn (Citation)** cho mọi phản hồi để user tự check lại.
- ✅ Khi AI không hiểu, nhường quyền (Escalate) tạo Ticket tới thẳng người thật (Human-in-the-loop).
- ✅ Luôn có dòng Cảnh báo miễn trừ trách nhiệm (Disclaimer).

</div>
</div>

---

# 4. Metrics & Lợi ích Kinh tế (The ROI)

AI sinh ra để kiếm tiền hoặc tiết kiệm tiền! (Quy mô 1000 nhân viên)

- **Chi phí (Cost):** ~$500/tháng (Tiền API OpenAI + Server lưu trữ Vector Qdrant).
- **Lợi ích (Benefit):** Chặn đứng 300 câu hỏi mỗi ngày. Tiết kiệm 750 giờ làm việc hỗ trợ của HR/IT -> Tương đương mức lương của 4.5 nhân viên full-time ($3000/tháng).
- 💰 **Lãi ròng (Net ROI):** +$2500 / tháng!

*(Bức tranh Tài chính quá rõ ràng để Thuyết phục Ban Giám khảo!)*

---

# 5. Kết luận (The Vision)

Chúng tôi thiết kế AI theo mô hình **Augmentation** (Trợ lý hỗ trợ tra cứu) chứ không phải Automation toàn vẹn. Nhờ đó, HR vẫn làm chủ những quyết định nhân sự cuối cùng, trong khi cởi trói được toàn bộ áp lực L1 Trợ giúp.

**Xin cám ơn Ban giám khảo! Khởi chạy Bản Demo tại `Nhom30-E403/prototype.html`!**
