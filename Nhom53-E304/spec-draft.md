# SPEC Draft — Hackathon AI Thực Chiến

> **Nhóm:** 30 (Phòng E403)  
> **Track:** D: Tự chọn (B2B Enterprise)  
> **Dự án:** Trợ lý Q&A Nội bộ (Internal HR/IT Helpdesk AI)  
> **Thành viên:**
> 1. Trịnh Kế Tiến — 2A202600500
> 2. [Điền Tên — MSSV]
> 3. [Điền Tên — MSSV]
> 4. [Điền Tên — MSSV]
> 5. [Điền Tên — MSSV]
>
> **Ngày nộp:** 08/04/2026

---

## 1. AI Product Canvas

### Problem Statement (1 câu)

> Nhân viên trong doanh nghiệp thường xuyên bị gián đoạn công việc và phải chờ đợi lâu khi hỏi các bộ phận HR/IT những câu hỏi lặp lại về chính sách, quy trình; **Trợ lý Q&A Nội bộ** có thể cung cấp câu trả lời chính xác ngay lập tức (24/7) dựa trên kho tài liệu nội bộ, giúp giải phóng thời gian cho cả hai bên.

### Canvas 3 cột

|   | Value | Trust | Feasibility |
|---|-------|-------|-------------|
| **Câu hỏi guide** | User nào? Pain gì? AI giải quyết gì mà cách hiện tại không giải được? | Khi AI sai thì user bị ảnh hưởng thế nào? User biết AI sai bằng cách nào? User sửa bằng cách nào? | Cost bao nhiêu/request? Latency bao lâu? Risk chính là gì? |
| **Trả lời** | **User:** Toàn bộ nhân viên công ty.<br>**Pain:** HR/IT mất quá nhiều thời gian trả lời câu hỏi lặt vặt (L1). Nhân viên chờ lâu.<br>**Value:** Tự động hóa giải đáp L1 tức thì dựa trên SOPs và Sổ tay nhân viên. | - AI tư vấn sai về lương/hợp đồng/bảo hiểm sẽ gây mâu thuẫn nhân sự lớn.<br>- User check lại bằng cách click vào link tài liệu gốc mà AI đính kèm.<br>- Sửa bằng nút "Escalate to HR" (Chuyển cho người thật). | - **Cost:** ~$0.001/query (chọn mô hình nhanh rẻ).<br>- **Latency:** <2s để tăng năng suất.<br>- **Risk:** Hallucination và bảo mật (Data leakage nếu quyền truy cập tài liệu không phân cấp rõ ràng). |

### Automation hay Augmentation?

- [ ] **Automation**
- [x] **Augmentation** — AI đóng vai trò như một người tra cứu tài liệu nhanh hộ nhân viên. Các quyết định hoặc xử lý cuối cùng (như duyệt nghỉ phép, ký giải ngân) vẫn luôn qua tay HR/Manager.

**Justify:** Các thông tin nội bộ mang tính bản quyền và nhạy cảm (Compliance). AI chỉ nên hỗ trợ tra cứu (Augment) thay vì tự động ra quyết định phê duyệt (Auto).

### Learning Signal

| # | Câu hỏi | Trả lời |
|---|---------|---------|
| 1 | User correction đi vào đâu? | Đi kèm với thẻ "Báo cáo nội dung lỗi", chuyển về cho bộ phận admin cập nhật lại cơ sở dữ liệu nội bộ. |
| 2 | Product thu signal gì để biết tốt lên hay tệ đi? | Implicit: Tỷ lệ "Deflection rate" (nhân viên đọc câu trả lời xong vòng đi luôn, không mở ticket hỏi HR nữa). |
| 3 | Data thuộc loại nào? | [x] Domain-specific (Tài liệu lưu hành nội bộ, tuyệt mật không có trên mạng). |

**Có marginal value không?** 
Có giá trị cận biên khổng lồ. Kho quy chế của mỗi công ty là duy nhất (Moat). Các chatbot AI ngoài thị trường (ChatGPT) không thể trả lời quy chế riêng của công ty được nếu không được cấy RAG.

---

## 2. User Stories (4 Paths)

### Story 1: Tính năng "Tra cứu chính sách HR"

> **Với tư cách là** nhân viên mới, **tôi muốn** hỏi AI về chính sách nghỉ thai sản và bảo hiểm, **để** không phải làm phiền HR.

| Path | Kịch bản | UX Response |
|------|----------|-------------|
| ✅ AI đúng | Hỏi: "Năm nay nghỉ Tết mấy ngày?" | Trả lời: "9 ngày (từ 28 âm đến mùng 6 Âm lịch). [Trích dẫn: Thông báo Lịch nghỉ Tết số 04]". |
| 🔍 AI không chắc | Viết một tràng bệnh lý dài hỏi: "Trường hợp này BHXH cty chi trả bao nhiêu?" | AI phản hồi: "Bảo hiểm chi trả từ 70-100% tuỳ ca bệnh. Do trường hợp của bạn phức tạp, hệ thống đã giúp bạn mở [Ticket #102] gửi tới cBảo hiểm HR. Vui lòng đợi." |
| ⚠️ AI sai | AI lấy nhầm chính sách thai sản của năm 2022 áp cho 2026. | User phàn nàn và bấm nút [Báo Lỗi] hoặc [Escalate lên Human HR]. |
| 🔧 User sửa | HR nhận được báo lỗi từ user và phát hiện data bị cũ. | HR xoá file PDF 2022 khỏi Vector DB, cập nhật file mới tinh. Lần sau AI trả lời đúng chuẩn. |

---

## 3. Evaluation Metrics

### Model Metrics

| Metric | Target | Cách đo |
|--------|--------|---------|
| Accuracy (Tìm đúng văn bản) | >98% | Lấy tập 100 câu hỏi test của HR đối chiếu tay |
| Knowledge freshness | < 1 ngày | Thời gian từ lúc HR upload file mới đến lúc AI update index |
| Hallucination rate | 🔴 **< 1%** | Do câu hỏi nội bộ nhạy cảm, tỷ lệ bịa đặt phải cực kỳ thấp |

### User Metrics

| Metric | Target | Cách đo |
|--------|--------|---------|
| First-Contact Resolution Rate | >80% | Tỷ lệ user hỏi xong không cần mở support ticket nữa. |
| User satisfaction (CSAT) | >4.5/5 | Thumbs up / Thumbs down sau câu trả lời |

### Business Metrics

| Metric | Target | Cách đo |
|--------|--------|---------|
| Support Ticket Reduction (L1) | **-50%** | So sánh tổng lượng ticket mở ra cho HR/IT trước và sau triển khai. |
| Onboarding time reduction | **-30%** | Thời gian đào tạo rút ngắn do nhân viên mới tự hỏi AI. |

**Precision hay Recall ưu tiên?**  
**Precision!** Đã trả lời chính sách công ty là phải chính xác tuyệt đối từng con số (vd: thưởng Tết mấy tháng lương). Thà AI nói "Không tìm thấy quy chế này" (bỏ sót dở - low recall) để nhân viên tự ra hỏi HR, còn hơn là AI nói nổ "Thưởng Tết 3 tháng lương" (sai Precision) làm nhân viên biểu tình!

---

## 4. Failure Modes & Mitigation

| # | Failure Mode | Severity | Impact | Mitigation (Khắc phục cực hay) |
|---|-------------|----------|--------|------------|
| 1 | Hallucination (Hư cấu chính sách) | 🔴 Cao | Nhân viên hiểu sai thưởng/phạt -> Kiện tụng | **Bắt buộc đính kèm UI Trích dẫn (Citation). AI nói câu nào phải link dòng đó ra đúng trang PDF nội bộ.** |
| 2 | Data Leakage (Rò rỉ lương giám đốc) | 🔴 Cao | Lộ bí mật cty | Cơ chế phân quyền cấp bậc. Query đi kèm User Token. NV thường không được RAG vào văn bản cấp C-Level. |
| 3 | AI chửi lộn với user | 🟡 TB | Uy tín | Gắn Guardrails chặn từ khóa khi nhân viên chửi thề với AI vì bực mình chính sách. |

---

## 5. ROI — 3 Kịch bản

| | Conservative (Dè dặt) | Realistic (Thực tế) | Optimistic (Kỳ vọng cao) |
|---|---|---|---|
| **Assumption** | Công ty 500 mạng. 100 câu/ngày | Công ty 1000 mạng. 300 câu/ngày | Công ty 3000 mạng. 1000 câu/ngày |
| **Cost (monthly)** | $100 LLM API + $100 Server = $200 | $300 + $200 = $500 | $1000 + $300 = $1300 |
| **Benefit (monthly)** | 1 câu tốn HR 5p -> Tiết kiệm 250h/tháng. Bằng 1.5 nhân sự = $1000. | Tiết kiệm 750h/tháng. Bằng 4.5 nhân sự = $3000. | Tiết kiệm 2500h/tháng. Bằng 15 nhân sự = $10,000. |
| **Net** | **+$800/tháng** | **+$2500/tháng** | **+$8700/tháng** |

**Bình luận ROI:** Mô hình Internal Bot mang lại giá trị hoàn vốn RÕ RÀNG NHẤT trong số tất cả AI App vì đo được thẳng bằng lương giờ làm của bộ phận Back-office.
**Kill criteria:** Dừng dự án nếu chi phí vận hành AI > lương thuê 1 nhân viên Helpdesk part-time.

---

## 6. Mini AI Spec

| Hạng mục | Chi tiết |
|----------|----------|
| **Input** | Dịch vụ Chat đa nền tảng (Tích hợp Slack / Microsoft Teams của cty). |
| **Output** | Text có markdown, highlight kèm Link tài liệu PDF (mở trực tiếp đúng trang). |
| **Model** | LLM: OpenAI GPT-4o-mini hoặc Claude 3.5 Haiku (Siêu nhanh, rẻ, RAG tốt). |
| **Technique** | **GraphRAG / Standard RAG:** Xử lý hàng nghìn trang PDF (SOP, Payroll, IT manual), chunking và vector hóa. |
| **Data pipeline** | Slack Webhook → Middleware check quyền (Auth) → Qdrant Vector Search → LLM tổng hợp → Trả về Slack. |
| **Bảo mật** | Chạy LLM trên Azure/Private Server để đảm bảo Compliance (Không dùng data để train model). |

---

## Phân công (Chia Việc)

| Thành viên | Phần phụ trách | Yêu cầu bổ sung để nộp |
|-----------|---------------|----------|
| Trịnh Kế Tiến | Canvas + ROI | Nộp nguyên file này là đủ điểm. |
| [Tên 2] | User Stories | Cùng review lại mục 2. |
| [Tên 3] | Eval Metrics | Kiểm tra lại các con số Target ở mục 3. |
| [Tên 4] | Failure Modes | Đọc lại mục Rò rỉ bảo mật (Data Leakage) ở mục 4 để có backup đi bảo vệ trước Mentor. |
| [Tên 5] | Vẽ Sketch Giao diện | Vẽ 1 cái UI chatbot trong app Slack có đính kèm file báo cáo HR. |

---
*SPEC Draft — Day 5 — AI Thực Chiến · VinUni A20 · 2026*
