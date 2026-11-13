# Kế hoạch cá nhân: Nghi (Người B)
## Phụ trách: `spec.md` §3, §5.2, §6 & Soạn Lời thoại AI (`prototype/ai-copy.md`) + Ảnh chụp Prototype
### Nhóm: nhomANH · Track: T4 Thương mại điện tử · Hạn nộp: 23:59 ngày 13/11/2026

> **NGUYÊN TẮC LÀM VIỆC ĐỘC LẬP & AN TOÀN GIT:**
> - Nghi bắt đầu làm việc ngay sau buổi thảo luận chung (khoảng phút ~70), **hoàn toàn độc lập, không bị chặn bởi việc dựng code của Hà hay phân tích mức tự chủ của An**.
> - **Input của Nghi:** Đã có sẵn trong [plan.md](file:///Users/hale/Code/AI%20in%20action%20lab/Lab%20day%205/K5-L3B-Day05-nhomANH-AI-Product-UX-Autonomy/plan.md) (2 kịch bản đắt nhất: Ca 1 mô tả bị sửa, Ca 2 khách doạ bóc phốt; sơ đồ đánh số HAX [1][2][3][4]).
> - **Phạm vi sở hữu:** `spec.md` các mục **§3**, **§5.2**, **§6**; file lời thoại `prototype/ai-copy.md`; file ảnh chụp `prototype/screenshot*.png` (chụp ở điểm họp lại).
> - **Git an toàn:** Làm việc trên branch `feature/nghi`, commit cục bộ thường xuyên khi hoàn thành từng phần (§3, `ai-copy.md`, §6) để tránh mất tiến độ; merge vào `main` tại điểm họp 170–200.
> - **Tuyệt đối không sửa:** File `prototype/index.html` (để Hà code); các mục §1, §2, §4, §5.1, §5.3, §5.4, §7 trong `spec.md`.

---

## 1. Mục tiêu & Các Mốc Quan Trọng

* **Phút 70 – 130:** Hoàn thành toàn bộ mục **§3** (UX khi AI sai) — đây là phần có điểm số cao nhất (**25 điểm R3**).
* **Phút 130 – 160:** Soạn thảo sẵn lời thoại và nhãn UI vào file `prototype/ai-copy.md`; viết xong mục **§6** (3 tiêu chí Pass/Fail chấm được).
* **Phút 160 – 170:** Viết sẵn khung mô tả ảnh đánh số trong **§5.2** theo đúng sơ đồ đã chốt ở `plan.md`.
* **Điểm họp lại (Khoảng phút 170 – 200):**
  - Giao file `prototype/ai-copy.md` cho Hà dán vào prototype.
  - Chụp 1–2 ảnh màn hình prototype trên trình duyệt, dùng công cụ đánh số [1], [2], [3], [4] và lưu vào `prototype/screenshot1.png` (và `screenshot2.png`).
  - Kiểm tra đối chiếu số trên ảnh khớp 100% với mô tả trong §5.2.

---

## 2. Checklist Hành động Từng bước của Nghi

### Bước 1: Viết chi tiết Mục §3 trong `spec.md` (Phút 70 – 130 · R3: 25 điểm)

#### 3.1. Ca đắt nhất 1: Người bán đã âm thầm sửa mô tả sau khi bán (Lớp ① Nguồn sự thật)
- [ ] **Lời AI nói nguyên văn:** Soạn câu thoại trung lập, nhã nhặn, minh bạch, chỉ rõ căn cứ đối chiếu:
  > *"Shopee đã tiếp nhận khiếu nại của bạn về sản phẩm [Tên sản phẩm]. Qua đối chiếu với **nội dung mô tả sản phẩm tại thời điểm bạn đặt mua**, hệ thống nhận thấy thông số dung tích có sự khác biệt so với mô tả hiện tại của Shop. Để đảm bảo quyền lợi công bằng cho bạn, Shopee đã chuyển hồ sơ này tới Chuyên viên khiếu nại xử lý ưu tiên. Bạn vui lòng giữ nguyên hiện trạng sản phẩm và theo dõi tiến trình cập nhật trong mục này."*
- [ ] **Bảng trải nghiệm UX:**
  - *Người dùng thấy gì:* Thẻ đối chiếu hiển thị 2 phiên bản mô tả (Mô tả lúc đặt vs Mô tả hiện tại), dòng trạng thái `[Đã chuyển Chuyên viên xử lý ưu tiên]`, nút `[Xem chi tiết hồ sơ]`.
  - *Làm gì tiếp:* Người mua yên tâm không bị từ chối oan, có thể tải thêm ảnh chụp nếu muốn hoặc bấm chat với nhân viên.
  - *Ai được báo, sau bao lâu:* Trưởng nhóm CSKH nhận hồ sơ ngay lập tức qua `chuyen_truong_nhom` kèm cờ cảnh báo "Mô tả sản phẩm bị sửa đổi sau khi đặt đơn".
- [ ] **Lập luận quyết định UX (4 ý):**
  - *Cân nhắc:* (a) Hỏi lại khách; (b) Trả lời kèm giới hạn; (c) Chuyển chuyên viên xử lý.
  - *Chọn:* Chuyển chuyên viên xử lý (`chuyen_truong_nhom`).
  - *Vì sao:* Vì đây là tranh chấp pháp lý về nguồn sự thật; AI không có thẩm quyền kết tội shop sửa mô tả hay tự ý xuất tiền hoàn.
  - *Loại phương án khác:* Loại "Hỏi lại" vì khách đã cung cấp đủ thông tin; loại "Trả lời kèm giới hạn" vì không thể giải quyết dứt điểm mâu thuẫn dữ liệu.
- [ ] **Phân loại lỗi:** Lỗi ngữ cảnh / Lỗi nguồn sự thật (Context Error) — Hệ thống đối chiếu đúng thuật toán nhưng truy vấn sai mốc thời gian của dữ liệu nếu lấy mô tả hiện tại.

#### 3.2. Ca đắt nhất 2: Người mua khiếu nại kèm lời đe dọa bóc phốt (Lớp ④ Đặc thù domain)
- [ ] **Lời AI nói nguyên văn:** Giữ vững sự bình tĩnh, từ chối bị áp lực bởi lời đe dọa:
  > *"Shopee rất thấu hiểu sự sốt ruột và bất tiện của bạn. Tuy nhiên, để đảm bảo tính công bằng và quyền lợi của cả hai bên theo quy chế sàn, mọi yêu cầu Trả hàng/Hoàn tiền đều cần đối soát chứng cứ khách quan và dành thời hạn hợp lệ để Người bán gửi phản hồi đối chất. Shopee đã ghi nhận khiếu nại của bạn và ấn định thời hạn phản hồi cho Người bán (thời gian còn lại hiển thị bên dưới). Sau thời hạn này, nếu Shop không có bằng chứng hợp lệ, Shopee sẽ tiến hành xử lý hoàn tiền cho bạn theo quy định."*
- [ ] **Bảng trải nghiệm UX:**
  - *Người dùng thấy gì:* Đồng hồ đếm ngược thời hạn phản hồi của người bán, thanh tiến trình minh bạch, nút "Gặp nhân viên hỗ trợ".
  - *Làm gì tiếp:* Người mua theo dõi tiến trình; người bán nhận thông báo và có nút gửi video đóng hàng đối chất.
  - *Ai được báo:* Người bán nhận thông báo khiếu nại ngay lập tức; nhân viên sàn nhận phiếu theo dõi.
- [ ] **Lập luận quyết định UX (đủ 4 ý):**
  - *Cân nhắc:* (a) Hỏi lại khách; (b) Trả lời kèm giới hạn và minh bạch quy trình (kích hoạt `yeu_cau_bang_chung` cho cả 2 bên và ấn định thời hạn phản hồi cho người bán); (c) Hoàn tiền ngay để xoa dịu khách; (d) Dừng và chuyển ngay cho trưởng nhóm.
  - *Chọn:* Trả lời kèm giới hạn và minh bạch quy trình.
  - *Vì sao:* Vì lời đe dọa bóc phốt không phải là căn cứ pháp lý hay sự thật về sản phẩm. AI phải giữ vững nguyên tắc trung lập của sàn, bảo đảm quyền đối chất của người bán theo thời hạn hợp lệ, không để cảm xúc tiêu cực hay áp lực truyền thông làm sai lệch dòng tiền.
  - *Loại phương án khác:* Loại "Hoàn tiền ngay" vì tạo tiền lệ xấu (moral hazard) cho việc tống tiền sàn và làm người bán mất tiền oan; loại "Chuyển ngay trưởng nhóm" vì người bán chưa hết thời hạn tự đối chất, chuyển sớm sẽ gây quá tải hàng đợi nhân viên; loại "Hỏi lại khách" vì khách đang kích động, hỏi thêm chỉ làm leo thang mâu thuẫn.
- [ ] **Phân loại lỗi:** **Lỗi ngữ cảnh (Context Error)** — Quy chuẩn chọn một trong 3 loại lỗi chính thức (hệ thống / người dùng / ngữ cảnh), không tạo loại lỗi thứ tư. Ở đây là lỗi ngữ cảnh vì hệ thống/mô hình chạy theo lời đe dọa của khách hoặc theo phản xạ xoa dịu, nhưng áp dụng sai hoàn toàn với bối cảnh: lời đe dọa bóc phốt không phải là căn cứ pháp lý để xác định hàng có đúng mô tả hay không.
- [ ] **Lỗi không thể sửa bằng câu chữ:**
  - *Chỉ ra rõ ràng:* Ở Ca 2 (Kịch bản #7), nếu quyền gọi tool `soan_hoan_tien` vẫn mở tự động cho AI, dù prompt dặn dò kỹ thế nào thì mô hình vẫn có thể bị jailbreak hoặc suy luận sai trước những lời đe dọa cực đoan.
  - *Thiết kế cứu lỗi thế nào:* Bắt buộc phải **khóa quyền tự động của `soan_hoan_tien` ở mức hệ thống** (chuyển sang mức Cần người duyệt). AI chỉ có quyền soạn đề xuất (`de_xuat_hoan_tien`), không có nút bấm tự chuyển tiền (`thuc_thi_hoan_tien`). *(Lưu ý bắt buộc: `de_xuat_hoan_tien` và `thuc_thi_hoan_tien` là đề xuất tách bước quy trình của nhóm, KHÔNG phải tool có trong đề bài; tool gốc trong đề bài duy nhất là `soan_hoan_tien` với đặc tính hoàn tiền thật, "Khó: tiền đã về người mua")*.

#### 3.3. Ánh xạ nguyên tắc HAX/PAIR
- [ ] Ánh xạ chi tiết 3 nguyên tắc vào bảng:
  * **HAX G11 (Make clear why):** Thẻ đối chiếu trích xuất mô tả lúc đặt mua (vị trí **[1]** trên prototype).
  * **HAX G10 (Scope services when in doubt):** AI không phán quyết liều mà kích hoạt nút chuyển nhân viên (vị trí **[2]**).
  * **HAX G1/G2 & PAIR Trust (Minh bạch năng lực):** Nhận diện trợ lý AI + Minh bạch thời hạn phản hồi còn lại thay vì hứa suông (vị trí **[3]**).

### Bước 2: Viết file `prototype/ai-copy.md` (Phút 130 – 145)
- [ ] Tạo file `prototype/ai-copy.md` chứa sẵn toàn bộ các đoạn text chuẩn:
  - Header: `"Trợ lý Khiếu nại Shopee (AI Assistant)"`
  - Tin nhắn khách Ca 1 & Ca 2.
  - Lời thoại AI Ca 1 & Ca 2.
  - Nội dung thẻ đối chiếu: `"Thông số lúc đặt: Nồi 6L"` vs `"Thông số hiện tại: Nồi phủ bì 6L, lòng 5L"`.
  - Nhãn nút bấm: `[Gặp nhân viên hỗ trợ]`, `[Xem tiến trình đối soát]`, `[Gửi bằng chứng đối chất]`.

### Bước 3: Viết Mục §6 trong `spec.md` (Phút 145 – 160 · R6: 5 điểm)
- [ ] Thiết lập 3 tiêu chí Pass/Fail chấm được:
  1. *Tiêu chí 1 (Nguồn sự thật):* Luôn đối chiếu với mô tả tại thời điểm đặt hàng; không dùng mô tả hiện tại để từ chối khiếu nại. (Đạt/Trượt).
  2. *Tiêu chí 2 (Tính trung lập):* Lời đe dọa bóc phốt không làm AI tự động bấm hoàn tiền; luôn có thời hạn phản hồi cho người bán. (Đạt/Trượt).
  3. *Tiêu chí 3 (Bảo vệ thông tin & Thẩm quyền):* Từ chối 100% việc cung cấp SĐT/địa chỉ riêng; không có nút phạt shop. (Đạt/Trượt).
- [ ] Chấm thử thiết kế trên 2 ca đắt nhất: Ghi nhận cả 2 ca đều **ĐẠT**.
- [ ] Nêu lỗi còn lại (Known Limitation): Prototype hiện cố định theo kịch bản mẫu; câu hỏi tự do ngoài kịch bản chưa được hỗ trợ sâu.

### Bước 4: Viết Mục §5.2 trong `spec.md` & Chụp ảnh đánh số (Phút 160 – 200)
- [ ] Viết phần mô tả các điểm đánh số trong §5.2:
  - **[1]:** Thể hiện HAX G11 — Thẻ đối chiếu mô tả lúc đặt hàng vs ảnh thực tế. Mức tự chủ: AI tự động phân tích và trích xuất.
  - **[2]:** Thể hiện HAX G10 — Nút "Gặp nhân viên hỗ trợ" (`chuyen_truong_nhom`). Mức tự chủ: Tự làm.
  - **[3]:** Thể hiện HAX G1/G2 & Rubric 8 — Huy hiệu danh tính AI và dòng đếm ngược thời hạn phản hồi của shop.
  - **[4]:** Thể hiện Màn hình Người bán (Bonus) & Mức tự chủ: Khung xác nhận của nhân viên sàn duyệt `soan_hoan_tien` và nút gửi chứng cứ của shop.
- [ ] **Tại điểm họp lại:** Mở prototype của Hà trên trình duyệt, chụp 2 ảnh `screenshot1.png` và `screenshot2.png`, đánh số [1], [2], [3], [4] rõ ràng và lưu vào thư mục `prototype/`.

---

## 3. Câu hỏi Sát hạch Demo mà Nghi phải trả lời trôi chảy

> [!CAUTION]
> **Quy tắc Vibe-coding:** Nếu giảng viên hoặc TA hỏi về phần việc có tên Nghi mà Nghi không giải thích được lý do thiết kế, phần đó sẽ bị **0 điểm ở R7**.

Nghi cần nắm chắc câu trả lời cho các câu hỏi sau:
1. *"Chỉ cho tôi chỗ nào trên màn hình là nguyên tắc G10 và G11?"*
   - Trả lời: Chỉ chính xác vào số **[2]** (G10 - Nút chuyển chuyên viên/thu hẹp phạm vi) và số **[1]** (G11 - Thẻ đối chiếu giải thích lý do dựa trên mô tả lúc đặt hàng).
2. *"Tại sao ở kịch bản bị đe dọa bóc phốt, việc sửa câu chữ/prompt không cứu được lỗi?"*
   - Trả lời: Vì mô hình ngôn ngữ lớn vẫn có xác suất bị thao túng (jailbreak) hoặc nhượng bộ trước cảm xúc cực đoan. Nếu công cụ `soan_hoan_tien` để ở chế độ tự động, tiền có thể bị chuyển đi vĩnh viễn. Thiết kế bắt buộc phải khóa quyền tự động ở tầng hệ thống, biến `soan_hoan_tien` thành Cần người duyệt.
3. *"Lỗi ở Ca 1 (mô tả bị sửa) là loại lỗi gì?"*
   - Trả lời: Đó là Context Error (lỗi ngữ cảnh/nguồn sự thật) theo phân loại của Google PAIR — hệ thống chạy đúng logic so khớp chuỗi nhưng lấy nhầm mốc thời gian của dữ liệu.
4. *"Ba tiêu chí Pass/Fail ở mục §6 có ý nghĩa gì đối với việc phát hành sản phẩm?"*
   - Trả lời: Đó là 3 chốt chặn an toàn đảm bảo tính trung lập, bảo vệ dữ liệu cá nhân và bảo vệ nguồn sự thật trước khi tính năng được đưa đến người dùng thực tế.
