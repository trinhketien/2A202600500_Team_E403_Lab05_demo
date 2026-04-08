# 🧠 Day 5: AI Product Thinking — Designing for Uncertainty

> **Day 5: AI Product Thinking**  
> AI chạy được chưa phải product. Hôm nay học cách thiết kế cho uncertainty — khi AI có thể sai, UI phải xử lý thế nào?

> **Sinh viên:** Trịnh Kế Tiến — **MSSV:** 2A202600500

![AI](https://img.shields.io/badge/AI-Product_Thinking-blue)
![UX](https://img.shields.io/badge/UX-4_Path_Framework-green)
![Canvas](https://img.shields.io/badge/Canvas-AI_Product-purple)
![SPEC](https://img.shields.io/badge/SPEC-Project_Delivery-orange)

---

## 📋 Tổng quan buổi học

```text
SÁNG — Lecture + Workshop                   CHIỀU — Lecture + Hackathon kickoff
┌──────────────────────────────┐            ┌──────────────────────────────┐
│ AI = probabilistic            │            │ Feedback loop + Data flywheel│
│ 3 trụ: Requirement · Eval · UX│     →      │ ROI 3 kịch bản               │
│ UX workshop (cá nhân)         │            │ Hackathon briefing           │
│ Canvas practice (nhóm)        │            │ Draft SPEC                   │
└──────────────────────────────┘            └──────────────────────────────┘
```

**Domino chain:**
```
AI = probabilistic (luôn có sai số)
  → Automation hay augmentation?
    → 3 trụ: Requirement / UX / Eval
      → Canvas (gộp 3 trụ vào 1 trang)
        → Feedback loop + Data flywheel
          → ROI 3 kịch bản
```

---

## 🗂️ Cấu trúc nộp bài

```
Day-05-AI-Product-Thinking/
├── presentation.html              # Slide thuyết trình (Reveal.js)
├── README.md                      # File này
│
├── canhan/
│   └── ux-exercise/
│       └── analysis.md            # ✅ Phân tích 4 paths + sketch as-is/to-be
│
└── NhomXX-Room/
    └── spec-draft.md              # 📄 SPEC draft nhóm (6 phần)
```

---

## 📝 Deliverables

| # | Deliverable | Loại | Deadline | Trạng thái |
|---|-------------|------|----------|------------|
| 1 | **Bài tập UX** — sketch + phân tích 4 paths | Cá nhân | Cuối UX workshop | ✅ Hoàn thành |
| 2 | **SPEC draft** — Canvas + hướng đi chính | Nhóm | 23h59 08/04/2026 | 📝 Template sẵn sàng |

---

## 📖 Nội dung đã thực hiện

### 1. Bài tập UX cá nhân (10 điểm)

**Sản phẩm phân tích:** MoMo — Trợ thủ AI Moni

| Tiêu chí | Điểm | Trạng thái |
|----------|------|------------|
| Phân tích 4 paths đủ + nhận xét path yếu nhất | 4 | ✅ |
| Sketch as-is + to-be rõ ràng | 4 | ✅ |
| Nhận xét gap marketing vs thực tế | 2 | ✅ |

**Kết quả phân tích:**
- Path tốt nhất: **Path 1** (AI đúng) — UX mượt mà
- Path yếu nhất: **Path 4** (User mất tin) — Không có exit/fallback
- Gap chính: Marketing hứa "tự động mọi giao dịch" nhưng accuracy ~70-80%, không có uncertainty indicator

→ Chi tiết: [`canhan/ux-exercise/analysis.md`](canhan/ux-exercise/analysis.md)

### 2. SPEC Draft nhóm (6 phần)

Template SPEC theo cấu trúc yêu cầu:
1. ✅ **AI Product Canvas** — Value / Trust / Feasibility
2. ✅ **User Stories** — Có 4 paths (đúng / không chắc / sai / user sửa)  
3. ✅ **Eval Metrics** — Model + User + Business metrics
4. ✅ **Failure Modes & Mitigation** — Bảng rủi ro 3 mức
5. ✅ **ROI 3 kịch bản** — Conservative / Realistic / Optimistic
6. ✅ **Mini AI Spec** — Input/Output/Model/Data pipeline/Infra

→ Template: [`NhomXX-Room/spec-draft.md`](NhomXX-Room/spec-draft.md)

---

## 🚀 Cách xem Presentation

Mở file `presentation.html` bằng trình duyệt web.

| Phím | Chức năng |
|------|-----------|
| → / Space | Slide tiếp theo |
| ← | Slide trước |
| Esc | Overview tất cả slide |
| F | Toàn màn hình |

---

## 📚 Framework chính

### 4 Paths — Khi AI output xong, chuyện gì xảy ra?

| Path | Câu hỏi thiết kế |
|------|-------------------|
| ✅ Happy — AI đúng | User thấy gì? Flow kết thúc ra sao? |
| 🔍 Low-confidence — AI không chắc | System báo bằng cách nào? User quyết thế nào? |
| ⚠️ Failure — AI sai | User biết sai bằng cách nào? Recover ra sao? |
| 🔧 Correction — user sửa | User sửa bằng cách nào? Data đó đi vào đâu? |

### Automation vs Augmentation

| | Automation | Augmentation |
|---|---|---|
| AI làm gì | Làm thay user | Gợi ý, user quyết |
| Khi AI sai | Thiệt hại đã xảy ra | User bỏ qua, không thiệt hại |
| Accuracy cần | Rất cao (99%+) | Chấp nhận thấp hơn (30%+) |
| Trust risk | Over-trust | Under-trust |

### Precision vs Recall

- **Precision:** AI nói "có" → đúng bao nhiêu? Ưu tiên khi sai nhầm = thiệt hại lớn
- **Recall:** trong số đúng thật → AI tìm được bao nhiêu? Ưu tiên khi bỏ sót = thiệt hại lớn
- PM chọn precision/recall = **product decision**, không phải technical decision

---

## 🏆 Hackathon Tracks

| Track | Lĩnh vực | Gợi ý bài toán |
|-------|----------|----------------|
| **A** | VinFast | AI chatbot hỗ trợ mua xe/bảo dưỡng, phân tích review |
| **B** | Vinmec | AI triage, hỏi triệu chứng → gợi ý chuyên khoa |
| **C** | VinUni/VinSchool | AI tutor, trợ lý học tập, Q&A nội bộ |
| **D** | Tự chọn | Tự chọn domain, phải justify |

---

*Bài thực hành Day 5 — AI Product Thinking: Designing for Uncertainty*  
*Sinh viên: Trịnh Kế Tiến — 2A202600500*
