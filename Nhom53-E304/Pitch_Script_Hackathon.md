# 🚀 Tổng Kết & Kịch Bản Thuyết Trình: HR Copilot (Nhóm 30)

Tài liệu này giúp bạn nắm vững toàn bộ những gì mình đã làm trong đêm nay và cung cấp một kịch bản "sát thủ" để bạn tự tin thuyết trình trước các Mentor hoặc Ban Giám khảo.

---

## 1. Bạn Đã Làm Được Những Gì Hôm Nay? (Thành Quả Suy Niệm)

Chỉ trong một buổi tối thực chiến (Day 5), bạn đã hoàn thành xuất sắc **vượt chỉ tiêu** 3 hạng mục lớn:

1.  **Bài Tập Cá Nhân (UX Analysis):** Phân tích thiết kế UX (Trải nghiệm người dùng) của các app lớn bằng ma trận 4-Paths để học cách họ xử lý rủi ro khi AI trả lời sai (Design for Uncertainty).
2.  **Thiết kế Sản phẩm Nhóm (Product SPEC):** Xây dựng một tài liệu chuẩn Enterprise (`spec-draft.md`) với tư duy cực kỳ sắc bén:
    *   **Nỗi đau (Pain):** Nhân sự/IT tốn thời gian trả lời lặp đi lặp lại các quy chế bằng tay. Mỗi tháng mất hàng trăm giờ đồng hồ giải quyết chuyện vặt.
    *   **Tính khả thi (Feasibility):** Sử dụng RAG (Retrieval-Augmented Generation) để AI tự đọc Sổ tay công ty một cách bảo mật tuyệt đối.
    *   **Chỉ số ROI:** Lập mô hình tài chính chứng minh AI tiết kiệm được từ $800 - $8700/tháng cho cty qua việc tự động giải quyết các ticket (Hỗ trợ tuyến 1).
3.  **💪 Prototype Tuyệt Đỉnh (Hackathon MVP):** Không chỉ nói suông trên giấy, bạn đã trực tiếp lập trình ra một ứng dụng **Fullstack Next.js + FastAPI + ChromaDB**, chứng minh rằng Spec của bạn là chạy được thật! Tính năng Dark Mode, trích dẫn tài liệu gốc (Citation Viewer) và bắt lỗi Ngoại luồng (Red Fallback) là công nghệ của riêng Nhóm 30 mà rất hiếm nhóm nào có.

---

## 2. Thông Điệp Cốt Lõi (Giá Trị Mang Lại)

Khi ai đó (Giám khảo) hỏi: *"Sản phẩm của em khác gì việc anh lên ChatGPT để hỏi về cách xin nghỉ phép?"*

**👉 Hãy Trả lời:** *"Dạ thưa, ChatGPT ở ngoài kia KHÔNG HỀ biết số ngày nghỉ phép của công ty mình là bao nhiêu, vì Sổ tay Nhân sự là tối mật. Trợ lý **HR Copilot** của nhóm em giải quyết được lỗ hổng đó bằng kỹ thuật AI RAG cục bộ (bơm cơ sở dữ liệu nội bộ vào bộ não AI). Hơn thế nữa, điểm ăn tiền nhất của ứng dụng này nằm ở **Tính Minh Bạch**. Thay vì cho AI có cơ hội trả lời linh tinh, tụi em ép AI phải Trích Dẫn (Citation). AI cứ nói một câu thì phải kèm theo văn bản chứng minh, và tụi em hỗ trợ người dùng MỞ file gốc ngay trên màn hình để kiểm chứng! Tránh tuyệt đối kiện tụng nội bộ do tin mù quáng vào AI!"*

---

## 3. Kịch Bản Thuyết Trình Bài Tập (Pitching 3 Phút)

Đừng đọc slide, hãy dùng kịch bản này, bạn có thể vừa kết hợp nói, vừa chia sẻ tab trình duyệt (mở sẵn localhost:3000) để Live Demo biểu diễn tính năng:

### ☀️ Mở bài (Thu hút: 45 giây)
> *"Xin kính chào các anh chị Mentor và Giám khảo. Nhóm 30 chúng em lựa chọn Track Doanh nghiệp (Enterprise). Chúng em nhìn thấy một thực trạng vô cùng lãng phí hiện nay: Ở các công ty quy mô lớn, mỗi ngày có hàng trăm nhân viên nhắn tin làm phiền HR/IT về những câu giống y hệt nhau như 'Xin nghỉ phép thì điền xin ở đâu chị?', 'Tiền lương bị chậm thì làm sao?'. HR thì ngập chìm trong tin nhắn lặp lại, còn nhân viên thì bực dọc và phải chờ rất lâu mới có câu trả lời."*

### 🔥 Thân bài (Trình bày Giải pháp & Demo Live: 1 Phút 30s)
> *"Giải pháp mang tính cách mạng của nhóm em là **HR Copilot** - một Trợ lý Q&A nội bộ tự động trực 24/7. Nhóm em không chỉ làm Spec thiết kế, mà xin phép biểu diễn trực tiếp bằng ứng dụng Fullstack tự code xong đêm qua!*
>
> *(Bạn thao tác gõ vào Web chữ 'Xin chào') Mọi người có thể thấy bot được thiết kế rất tự nhiên như con người.*
>
> *(Bạn gõ 'Tôi được nghỉ phép mấy ngày?') Và đây là giá trị quan trọng nhất: **Design for Trust (Thiết kế vì niềm tin)**. Thay vì để AI trả lời vô thưởng vô phạt, hệ thống ép AI phải khai báo nguồn gốc! Anh/Chị có thể nhìn xuống dưới, AI trả về dòng Citation 'Mật: chinh-sach-nghi.md'. Vậy lỡ AI nói sai một con số thì sao? Em đã tích hợp hộp thoại kiểm chứng (Bạn click vào biểu tượng Citation để hiện Popup đọc tài liệu). Bất kỳ nhân viên nào cũng xem được ngay văn bản gốc để đối chiếu, phá vỡ hoàn toàn rào cản sợ hãi bị AI lừa dối trong doanh nghiệp!"*
>
> *(Bạn tiếp tục gõ chữ 'Giá vàng hôm nay bao nhiêu?') Cuối cùng, nói về quản trị rủi ro Uncertainty. Khi người dùng cố tình hỏi một câu ngoài nghiệp vụ, phần lớn chatbot sẽ bịa chuyện. Ứng dụng của em KHÔNG cố gắng thoái thác chung chung, mà sẽ khoanh đỏ, thông báo trung thực là chưa có dữ liệu và ghi nhận lại yêu cầu để chuyển cho Người thật (Human HR) xử lý!"*

### 🎯 Kết bài (Khẳng định giá trị: 45 giây)
> *"Theo bảng Phân tích ROI tụi em đã tính toán trong file SPEC, với một quy mô công ty khoảng 1000 người, HR Copilot sẽ giúp tiết kiệm 750 giờ làm việc thừa thãi mỗi tháng, tương đương chặn đứng rò rỉ ngân sách gần 2,500 Đô La mỗi tháng. Sự tin cậy, chính xác, và tiết kiệm chi phí là lý do **HR Copilot của Nhóm 30** chính là vũ khí mỗi doanh nghiệp cần. Xin cảm ơn ạ!"*

---

## 💡 Lời Khuyên Bí Quyết
1. Bạn hãy mở Web App Localhost ra và tự bấm nút, tự gõ theo Bài diễn thuyết ở mục 3 trên từ 2-3 lần cho thật trơn tru.
2. Hãy tự hào và ngẩng cao đầu vì bạn mang đến sân khấu một **Sản phẩm thật (Working MVP)**. Hầu hết các thí sinh khác hôm nay chỉ có slide lý thuyết trên Canva. Việc bạn chạy một con ChatGPT nội bộ thật với Giao diện xịn xò sẽ là một cú nổ! Chúc bạn và nhóm thành công!
