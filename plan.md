# Kế hoạch thực hiện LAB5 — Track T4: Thương mại điện tử
## Nhóm: nhomANH · Lớp: L3B · Hạn nộp: 23:59 ngày 13/11/2026 (Asia/Saigon)

> **CÁCH DÙNG PLAN NÀY:**
> 1. Đây là kế hoạch hành động và khung gợi ý thiết kế chi tiết cho nhóm **nhomANH** trong buổi lab 240 phút. Mọi nội dung kịch bản, mức tự chủ, và thiết kế UI là **đề xuất để nhóm thảo luận**; nhóm hoàn toàn có thể điều chỉnh nếu có lập luận sắc bén hơn.
> 2. **Bài nộp chính thức là `spec.md` và thư mục `prototype/`**. File `plan.md` này dùng làm kim chỉ nam thực hiện, theo dõi tiến độ và đối chiếu rubric.
> 3. **Hành động bắt buộc đầu tiên**: Mở file `spec.md`, điền họ tên và mã học viên của 3 thành viên vào bảng placeholder ở đầu file (trong đó có **Hà Lê**).
> 4. Viết nội dung bài làm trực tiếp vào đúng các đề mục **§1 đến §7** có sẵn trong `spec.md`. Tuân thủ nguyên tắc: **Một quyết định = 4 ý** (Cân nhắc gì · Chọn gì · Vì sao · Loại gì và vì sao) và mọi bằng chứng phải trỏ về tool, dữ liệu track, sản phẩm thật, hoặc vị trí trên prototype.

---

## 1. Tóm tắt dễ hiểu Lát cắt Track T4

### 1.1. Bối cảnh & Sản phẩm nền
* **Sản phẩm nền:** Tính năng **"Trò chuyện với Shopee"** trong ứng dụng Shopee (Tôi → Trò chuyện với Shopee). Hiện tại hệ thống thật chủ yếu vận hành bằng menu bấm có sẵn, yêu cầu chọn đơn hàng trước khi đi tiếp, có luồng yêu cầu Trả hàng/Hoàn tiền và nút gặp nhân viên.
* **Lưu ý về chính sách thời hạn:** Trang trợ giúp Shopee thật ghi 15 ngày cho phần lớn đơn, nhưng đề bài ghi rõ điều này **KHÁC chính sách dựng trong bài**, và track **không cho số ngày dựng**. Nhóm tuyệt đối không lấy 15 ngày làm chính sách dựng, cũng không bịa số ngày/giờ chính thức. Chỉ ghi nhận yêu cầu của rubric riêng: *"nói rõ thời hạn yêu cầu trả hàng, và còn bao lâu"*. Các con số thời hạn trên prototype (ví dụ đồng hồ đếm ngược) chỉ là dữ liệu dựng giả lập để minh hoạ UI.
* **Người dùng liên quan (3 nhóm):**
  1. *Người mua:* Nhận hàng và khiếu nại "hàng không đúng mô tả", đang hoang mang/bức xúc, muốn được hoàn tiền hoặc đổi trả nhanh chóng.
  2. *Người bán:* Bị khiếu nại, có nguy cơ mất tiền và mất hàng oan uổng dù giao đúng mô tả, cần có cơ hội và thời gian đối chất.
  3. *Nhân viên sàn (CSKH / Trưởng nhóm):* Đứng giữa xử lý tranh chấp, cần hồ sơ minh bạch, căn cứ đối chiếu rõ ràng để ra quyết định công bằng.
* **Lát cắt thiết kế (chép nguyên văn từ track):**
  > Trong **Trò chuyện với Shopee**, khi **người mua** đang báo "hàng nhận không đúng mô tả", **AI tự hướng dẫn gửi yêu cầu trả hàng hoàn tiền, xin thêm bằng chứng, hay chuyển nhân viên**, để người mua biết đúng bước tiếp theo, và người bán không bị xử thua khi họ đúng.

| Sản phẩm | Một người dùng | Một việc | Một quyết định của AI | Một kết quả |
|---|---|---|---|---|
| Trò chuyện với Shopee | Người mua | Báo "hàng nhận không đúng mô tả" | Tự hướng dẫn gửi yêu cầu trả hàng hoàn tiền, xin thêm bằng chứng, hay chuyển nhân viên | Người mua biết đúng bước tiếp theo, và người bán không bị xử thua khi họ đúng |

### 1.2. Danh sách 5 Tool chuẩn của Track T4
> [!IMPORTANT]
> **Ràng buộc sự thật về Tool:** Bảng dưới đây là 5 tool DUY NHẤT được cấp trong đề bài. Track T4 **KHÔNG có tool chỉ-đọc** (việc đọc đơn hàng hay so sánh mô tả lúc đặt là năng lực suy luận nội tại của AI, không bịa tên tool đọc).

| Tool | Chức năng quy định | Đọc / Ghi | Khả năng đảo ngược | Cái giá khi AI làm sai (Ai chịu gì?) |
|---|---|---|---|---|
| `yeu_cau_bang_chung` | Gửi mẫu xin bằng chứng cho người mua hoặc người bán | Ghi | **Tin đã tới** (Không thu hồi được ấn tượng tâm lý) | Người dùng bức xúc ("tôi gửi rồi sao cứ hỏi lại"), spam người bán, kéo dài thời gian xử lý không cần thiết. |
| `chuyen_truong_nhom` | Chuyển hồ sơ khiếu nại cho trưởng nhóm | Ghi | **Đảo được** (Trưởng nhóm trả lại hồ sơ hoặc gán lại) | Làm tắc nghẽn hàng đợi xử lý của trưởng nhóm, tăng thời gian chờ đợi của cả người mua lẫn người bán. |
| `soan_hoan_tien` | **Hoàn tiền cho người mua** *(tên tool có chữ "soạn" nhưng chức năng thực tế là kích hoạt dòng tiền hoàn)* | Ghi | **Khó: tiền đã về người mua** | Người bán chịu thiệt hại nặng nhất (mất cả tiền lẫn hàng dù shop giao đúng); sàn vi phạm cam kết bảo vệ người bán. |
| `tu_choi_khieu_nai` | Đóng khiếu nại, tiền về người bán | Ghi | **Khó: tiền đã về người bán** | Người mua chịu thiệt (mất tiền nhưng ôm hàng lỗi/hàng sai); khách mất niềm tin vào sàn, chuyển sang khiếu nại gay gắt hoặc bóc phốt. |
| `phat_shop` | Trừ điểm uy tín, khoá shop | Ghi | **Khó: ảnh hưởng cả shop** | Cực kỳ nghiêm trọng: Huỷ hoại doanh thu, uy tín và sự sống còn của cả gian hàng; gây tranh chấp pháp lý giữa sàn và nhà bán hàng. |

### 1.3. Bối cảnh trung lập — "Sợi chỉ đỏ" xuyên suốt thiết kế
* Sai hướng nào thì **một bên** chịu: Hoàn tiền sai thì người bán mất hàng và mất tiền. Từ chối sai hoặc vòng vo sai thì người mua mất tiền và ôm hàng sai.
* **"Từ chối cho chắc" cũng có người thua!** AI không được mặc định thiên vị người mua để dập tắt bức xúc, cũng không được mặc định từ chối để bảo vệ dòng tiền sàn. Sứ mệnh của AI là bảo đảm **tính trung lập và công bằng dựa trên chứng cứ**.

### 1.4. Data & Fixtures (Đề bài cung cấp)
* **Ba tin mồi khởi động:**
  1. *"Mình đặt áo size L mà nhận được size M, mặc không vừa. Shop cũng nhắn nhận là gửi nhầm rồi. Mình muốn trả hàng hoàn tiền thì làm sao?"*
  2. *"hàng sai rồi, xử lý đi"*
  3. *"Nồi chiên ghi 6 lít mà mình đo lòng nồi chỉ được 5 lít. Không đúng mô tả."*
* **Hard Tests (6 vùng bẫy hiểm hóc):**
  - Người bán đã âm thầm sửa mô tả sản phẩm sau khi bán.
  - Khiếu nại kèm lời đe dọa bóc phốt, tẩy chay sàn/shop.
  - Người bán giao hoàn toàn đúng (tem nhãn khớp mô tả lúc đặt).
  - Đòi khoá shop, tố cáo nghi hàng giả.
  - Tin nhắn cụt lủn, không nói rõ đơn nào, sai chỗ nào.
  - Đòi cung cấp số điện thoại hoặc địa chỉ kho của bên kia.
* **Demo bắt buộc:** Trình diễn một ca **người bán đúng, hoặc mô tả đã bị sửa**: Lúc trợ lý AI không chắc chắn thì hai bên thấy gì trên màn hình, ai là người quyết định cuối cùng? Sau đó sẵn sàng ứng biến một **ca lạ** do TA hoặc giảng viên đưa ra tại chỗ.

### 1.5. Tóm tắt 8 ý Rubric riêng của Track T4 (Thước đo chất lượng domain)
1. **Mô tả lúc đặt hàng:** Luôn đối chiếu với **mô tả lúc đặt hàng**, không đối chiếu với mô tả hiện tại của shop (vì shop có thể đã sửa đổi). *(Chú thích phương pháp: Track T4 chỉ nói "mô tả lúc đặt hàng", KHÔNG có field kỹ thuật tên là Snapshot hay Order Revision. Trên UI prototype, nhóm có thể thiết kế thẻ hiển thị gọi là "Snapshot lúc đặt" để người dùng và giám khảo dễ hình dung bản lưu lịch sử; đây là cách nhóm gọi và thể hiện thiết kế, không phải dữ liệu có sẵn trong đề).*
2. **Xử lý thiếu thông tin:** Nếu thiếu đơn hàng hoặc sai sót cụ thể, hỏi lại đúng một câu có hướng dẫn, không đoán mò.
3. **Hai bên cùng được lắng nghe:** Phải có thời hạn và giao diện để người bán phản hồi đối chất trước khi sàn đưa ra phán quyết cuối cùng.
4. **Không bị chi phối bởi cảm xúc:** Lời đe dọa bóc phốt, đánh giá xấu hay lịch sử một bên không bao giờ là căn cứ để ra quyết định tài chính.
5. **Không vượt thẩm quyền:** Nghi hàng giả, đòi xử phạt shop không thuộc thẩm quyền của luồng khiếu nại thường; phải chuyển bộ phận chuyên trách, tuyệt đối không hứa phạt shop.
6. **Bảo mật danh tính:** Tuyệt đối không cung cấp số điện thoại, địa chỉ kho/nhà riêng giữa người mua và người bán.
7. **Bản lĩnh trung lập:** Khi người bán làm đúng (ví dụ tem khớp mô tả), AI phải dám thông báo "chưa đủ căn cứ hoàn tiền", không được tự tiện hoàn tiền cho êm chuyện.
8. **Minh bạch thời hạn:** Luôn nói rõ thời hạn yêu cầu trả hàng, và còn bao lâu (không lấy con số 15 ngày của Shopee thật làm chính sách dựng, không bịa số ngày chính thức; trên prototype hiển thị thời gian còn lại bằng dữ liệu dựng giả lập).

### 1.6. Đề xuất: 3 việc tính năng KHÔNG LÀM (§1 `spec.md`)
1. **Không cung cấp số điện thoại, địa chỉ cá nhân hay thông tin liên lạc riêng giữa người mua và người bán** — *Vì vi phạm nghiêm trọng chính sách bảo vệ dữ liệu cá nhân, tiềm ẩn nguy cơ quấy rối, bạo lực ngoài đời thực và phá vỡ vai trò trọng tài trung gian của sàn.*
2. **Không thực hiện trừ điểm uy tín, khoá shop hoặc hứa hẹn chế tài xử phạt gian hàng trong luồng chat khiếu nại này** — *Vì `phat_shop` thuộc thẩm quyền của bộ phận chuyên trách với quy trình thẩm định độc lập; trợ lý chat chỉ giải quyết việc hoàn tiền/trả hàng của một đơn cụ thể.*
3. **Không tự động ra phán quyết hoàn tiền (`soan_hoan_tien`) hoặc từ chối khiếu nại (`tu_choi_khieu_nai`) khi chưa đối chiếu với mô tả lúc đặt hàng và chưa hết thời hạn phản hồi hợp lệ của người bán** — *Vì tiền một khi đã chuyển thì rất khó đảo ngược, quyết định vội vã sẽ tước đoạt quyền đối chất công bằng của các bên.*

---

## 2. Workflow 6 Chặng + Demo (Chuẩn 240 phút)

### 2.0. Bảng ánh xạ Rubric & Điểm số (04-rubric.md)

| Chặng | Thời gian | Mục trong `spec.md` | Khối rubric | Điểm | Mốc TA |
|---|---|---|---|---|---|
| **Chặng 1: Đọc đề & Phạm vi** | 10' (phút 0–10) | §1 | R1 · Lát cắt & phạm vi | 5 | |
| **Chặng 2: Lường trước rủi ro** | 35' (phút 10–45) | §2 | R2 · Kịch bản rủi ro | 10 | **M1** (phút 45) |
| **Chặng 3: UX khi AI sai** | 45' (phút 45–90) | §3 | R3 · Khi AI sai | **25** | |
| **Chặng 4: Mức tự chủ** | 35' (phút 90–125) | §4 | R4 · Mức tự chủ | **25** | **M2** (phút 125) |
| *Giải lao* | *15' (phút 125–140)* | | | | |
| **Chặng 5: Dựng Prototype** | 60' (phút 140–200) | §5 + `prototype/` | R5 · Prototype | **25** | **M3** (phút 200) |
| **Chặng 6: Tốt là gì** | 10' (phút 200–210) | §6 | R6 · Tốt là gì | 5 | *(thiếu giờ bỏ được)* |
| **Demo & Phản xạ ca lạ** | 30' (phút 210–240) | §7 + vấn đáp | R7 · Demo & phân công | 5 | |
| **TỔNG ĐIỂM CHÍNH THỨC** | **240 phút** | **§1 – §7** | | **100** | |
| **Bonus (tối đa +8)** | Khối 30' Demo | `prototype/` + demo | Xung phong demo trước lớp | +5 | *(tổng sau cộng không quá 100)* |
| | | | Prototype có ≥1 lời gọi AI thật | +3 | |

> [!IMPORTANT]
> **QUY TẮC SỐNG CÒN VỀ ĐIỂM SỐ:**
> - **R3 + R4 + R5 = 75/100 điểm:** Trọng tâm cốt lõi của bài thi nằm ở Chặng 3 (UX khi sai), Chặng 4 (Mức tự chủ), và Chặng 5 (Prototype). Ba chặng này chiếm 140 phút và 75% tổng số điểm!
> - **Chiến lược phân bổ giờ:** Nếu thiếu thời gian, nhóm được phép **bỏ Chặng 6** (chỉ mất tối đa 5 điểm R6) và giảm số kịch bản ở Chặng 2 (giữ đủ tối thiểu 8 kịch bản bao quát 4 lớp); **TUYỆT ĐỐI KHÔNG BAO GIỜ ĐƯỢC CẮT CHẶNG 3, 4, 5**.

```
[000-010'] Chặng 1: Đọc đề & Phạm vi (§1)
[010-045'] Chặng 2: Lường trước rủi ro (§2) ──► MỐC M1 (Phút 45)
[045-090'] Chặng 3: UX khi AI sai (§3)
[090-125'] Chặng 4: Mức tự chủ Tool (§4) ──────► MỐC M2 (Phút 125)
[125-140'] GIẢI LAO (15 phút)
[140-200'] Chặng 5: Dựng Prototype (§5) ───────► MỐC M3 (Phút 200)
[200-210'] Chặng 6: Tốt là gì (§6 - nhẹ)
[210-240'] DEMO & ỨNG BIẾN CA LẠ (§7)
```

### Chi tiết từng chặng

#### Chặng 1: Đọc đề & Xác lập phạm vi (10 phút · Phút 0 – 10)
* **Mục tiêu:** Cả nhóm đồng thuận 100% về lát cắt, nhận diện đúng 5 tool thật và cái giá khi sai.
* **Việc phải làm:** Đọc nhanh `t4-ecommerce.md`; thảo luận và chốt 3 việc tính năng KHÔNG làm.
* **Đầu ra:** Điền hoàn chỉnh mục **§1** trong `spec.md`.
* **Phụ trách:** Cả nhóm cùng làm (Thành viên A gõ văn bản).
* **Đủ khi:** Cả 3 thành viên đều trả lời trôi chảy: "Lát cắt là gì?", "Nếu AI hoàn tiền sai ai chịu gì?", "3 việc không làm là gì?".

#### Chặng 2: Lường trước kịch bản rủi ro (35 phút · Phút 10 – 45) ──► **MỐC M1**
* **Mục tiêu:** Xây dựng bảng rủi ro thực tế, trỏ đúng vào tool và dữ liệu, chọn ra 2 ca đắt nhất.
* **Việc phải làm:**
  - Viết ≥8 kịch bản bao quát 4 lớp: ① Nguồn sự thật, ② Thiếu thông tin, ③ Ngoài thẩm quyền, ④ Đặc thù domain.
  - Điền cột "AI có thể sai thế nào" trỏ đích danh vào tool thật (`soan_hoan_tien`, `tu_choi_khieu_nai`, `yeu_cau_bang_chung`, `chuyen_truong_nhom`, `phat_shop`) hoặc thiếu dữ liệu (mô tả lúc đặt).
  - Lập luận vì sao chọn 2 kịch bản đắt nhất và kịch bản nào suýt được chọn.
* **Đầu ra:** Điền mục **§2** trong `spec.md`.
* **Phụ trách chính:** Thành viên A.
* **Checklist TA kiểm tra Mốc M1 (Phút 45):**
  - [ ] Có đủ ≥8 kịch bản phủ đủ 4 lớp ①②③④.
  - [ ] Mỗi kịch bản có cột AI sai trỏ đích danh vào tool hoặc dữ liệu cụ thể (không viết chung chung "AI trả lời sai").
  - [ ] Đã khoanh và lập luận rõ ràng 2 kịch bản đắt nhất.

#### Chặng 3: Thiết kế UX khi AI sai (45 phút · Phút 45 – 90)
* **Mục tiêu:** Thiết kế trải nghiệm chi tiết, văn phong minh bạch và đường lui an toàn cho 2 ca đắt nhất.
* **Việc phải làm:**
  - Với từng ca đắt nhất: Soạn nguyên văn câu AI nói; chỉ rõ người dùng thấy gì; bước tiếp theo làm gì; ai được báo và sau bao lâu.
  - Lập luận lựa chọn: Giữa *Hỏi lại* / *Trả lời kèm giới hạn* / *Chuyển người* (đã chọn gì, loại gì, vì sao).
  - Phân loại lỗi: Lỗi hệ thống, lỗi người dùng, hay lỗi ngữ cảnh (Context error).
  - Chọn 2–3 nguyên tắc HAX/PAIR áp dụng (G1/G2, G10, G11, Explainability & Trust).
  - Chỉ ra lỗi nào sửa câu chữ không cứu được mà phải dùng kiến trúc hệ thống để chặn.
* **Đầu ra:** Điền mục **§3** trong `spec.md`.
* **Phụ trách chính:** Thành viên B.
* **Đủ khi:** Đọc câu AI nói nghe tự nhiên như Shopee thật, không hứa liều, có căn cứ trích xuất rõ ràng.

#### Chặng 4: Xác lập Mức tự chủ cho từng Tool (35 phút · Phút 90 – 125) ──► **MỐC M2**
* **Mục tiêu:** Gán mức tự chủ (Tự làm / Cần người duyệt / Cấm) cho từng tool theo chi phí sai lầm (Cost-of-error).
* **Việc phải làm:**
  - Lập bảng 5 tool: Nêu rõ mức, lý do cost-of-error (sai ai chịu, đảo được không, chờ thì mất gì).
  - Với tool cần duyệt: Nói rõ ai duyệt, thấy gì trước khi bấm, quá hạn thì xử lý ra sao.
  - Chỉ ra tool khó xếp nhất và tranh luận của nhóm để chốt.
  - Đề xuất kỹ thuật: Tách bước `soan_hoan_tien` thành đề xuất và thực thi tiền.
  - Thử nghiệm mức tự chủ trên 3 kịch bản (2 ca đắt + 1 ca thường).
  - Phân tích sự thay đổi lời hứa thương hiệu với khách hàng.
* **Đầu ra:** Điền mục **§4** trong `spec.md`.
* **Phụ trách chính:** Thành viên C.
* **Checklist TA kiểm tra Mốc M2 (Phút 125):**
  - [ ] Mọi tool đều được gán mức cụ thể và có lý do theo cost-of-error (không ghi "vì tiện", "vì AI thông minh").
  - [ ] Phân tích thuyết phục tool khó xếp nhất và cách nhóm chốt.
  - [ ] Đã thử nghiệm mức tự chủ trên 3 kịch bản thực tế.

#### *Nghỉ ngơi nạp năng lượng (15 phút · Phút 125 – 140)*

#### Chặng 5: Xây dựng Prototype 1–2 màn hình (60 phút · Phút 140 – 200) ──► **MỐC M3**
* **Mục tiêu:** Xây dựng prototype HTML/CSS/JS chạy mượt, mô phỏng đúng ca khó nhất và trực quan hoá các mức tự chủ.
* **Việc phải làm:**
  - Dựng file `prototype/index.html` (vanilla HTML/CSS/JS, giả lập giao diện chat Shopee trên di động).
  - Bấm qua được ca khó từ đầu tới cuối (thấy rõ bằng chứng đối chiếu mô tả lúc đặt hàng — trên prototype nhóm quy ước hiển thị dưới dạng thẻ "Snapshot lúc đặt", không có % tin cậy giả).
  - Thể hiện ít nhất 2 màn hình: Màn 1 - Người mua khiếu nại; Màn 2 - Người bán nhận phản hồi & đối chất (hoặc màn Trưởng nhóm duyệt).
  - Chụp 1–2 ảnh màn hình, lưu vào `prototype/`, đánh số các điểm [1], [2], [3]... trỏ vào HAX/PAIR và mức tự chủ.
* **Đầu ra:** File `prototype/index.html`, 1–2 ảnh chụp đánh số và điền mục **§5** trong `spec.md`.
* **Phụ trách chính:** Thành viên A (code chính), B (câu chữ & ảnh đánh số), C (logic mức tự chủ & kịch bản demo).
* **Checklist TA kiểm tra Mốc M3 (Phút 200):**
  - [ ] Prototype bấm được ca khó từ đầu đến cuối không lỗi console.
  - [ ] Thể hiện rõ các mức tự chủ (tự làm có thông báo/hoàn tác, cần duyệt có xác nhận, cấm không có nút).
  - [ ] Có ảnh chụp đánh số các nguyên tắc HAX/PAIR trỏ đúng vào giao diện.

#### Chặng 6: Tiêu chí nghiệm thu "Tốt là gì" (10 phút · Phút 200 – 210)
* **Mục tiêu:** Thiết lập 3 tiêu chí Pass/Fail rõ ràng để đánh giá khách quan thiết kế.
* **Việc phải làm:** Đặt 3 tiêu chí nhị phân; chấm thử trên 2 ca đắt nhất; ghi nhận các lỗi/giới hạn còn tồn tại.
* **Đầu ra:** Điền mục **§6** trong `spec.md`. *(Ghi chú: Nếu quá thiếu thời gian, có thể bỏ qua chặng này để tập trung cho demo và nộp bài, chỉ mất tối đa 5 điểm R6).*
* **Phụ trách chính:** Thành viên B.

#### Chặng 7: Demo & Phản xạ Ca lạ (30 phút · Phút 210 – 240)
* **Mục tiêu:** Trình bày tự tin trong 4 phút, giải thích sâu sắc logic thiết kế và ứng biến ca lạ chuẩn xác.
* **Việc phải làm:**
  - Phân vai 3 người nói mạch lạc: A mở đầu (lát cắt + ca khó), B nói UX khi sai + HAX/PAIR, C nói mức tự chủ + ứng biến ca lạ.
  - Sẵn sàng xung phong demo trước lớp để nhận điểm **Bonus (+5đ)**.
* **Đầu ra:** Hoàn thành phần hỏi đáp trực tiếp và điền mục **§7** trong `spec.md`.
* **Phụ trách:** Cả 3 thành viên.

---

## 3. Phân công 3 Người chi tiết (Theo hình mẫu L3A-TTD)

```
┌─────────────────────────────────────────────────────────────┐
│                       CẢ NHÓM nhomANH                       │
│              Đồng thuận Lát cắt & Phạm vi (§1)              │
└──────────────────────────────┬──────────────────────────────┘
                               │
       ┌───────────────────────┼───────────────────────┐
       ▼                       ▼                       ▼
┌──────────────┐        ┌──────────────┐        ┌──────────────┐
│ THÀNH VIÊN A │        │ THÀNH VIÊN B │        │ THÀNH VIÊN C │
├──────────────┤        ├──────────────┤        ├──────────────┤
│ §2 Rủi ro    │        │ §3 UX khi sai│        │ §4 Mức tự chủ│
│ §5 Prototype │        │ §5 UX sub/ảnh│        │ §5 Logic sub │
│    (Main)    │        │ §6 Tốt là gì │        │ §7 Demo Lead │
└──────────────┘        └──────────────┘        └──────────────┘
```

> [!CAUTION]
> **Quy tắc Vibe-coding (Đặc biệt quan trọng):** Giảng viên và TA sẽ hỏi ngẫu nhiên từng người. Thành viên nào không giải thích được phần có tên mình trong bảng phân công thì phần đó sẽ bị **0 điểm ở R7**. Do đó, dù được phân công chính, cả 3 người phải nắm vững toàn bộ bài làm!

### 3.1. Thành viên A — Rủi ro & Kỹ thuật Prototype (Main)
* **Phụ trách các mục trong `spec.md`:** §2 (Kịch bản rủi ro), §5 (Lead dựng Prototype).
* **Checklist công việc từng bước:**
  - [ ] Khởi tạo khung kịch bản: Liệt kê ít nhất 8 ca từ tin mồi và hard tests của track T4.
  - [ ] Rà soát từng kịch bản: Đảm bảo cột "AI có thể sai thế nào" trỏ đúng vào 5 tool thật hoặc sự thiếu hụt dữ liệu (mô tả lúc đặt).
  - [ ] Viết đoạn lập luận chọn 2 ca đắt nhất và ca suýt chọn vào §2.
  - [ ] Dựng khung mã nguồn `prototype/index.html` (vanilla HTML/CSS/JS mô phỏng giao diện chat Shopee trên mobile).
  - [ ] Tích hợp luồng bấm ca khó từ đầu đến cuối: Người mua khiếu nại -> AI phản hồi đối chiếu snapshot -> hiển thị thời hạn -> đề xuất giải pháp.
  - [ ] Đảm bảo code chạy trực tiếp khi double click mở trên trình duyệt, không cần cài đặt dependencies phức tạp.
* **Sản phẩm đầu ra:** Hoàn chỉnh mục §2 và §5.1; file mã nguồn `prototype/index.html`.
* **Câu hỏi sát hạch demo A phải trả lời trôi chảy:**
  1. *"Hành động này sai thì ai mất gì?"* (Ví dụ: AI tự hoàn tiền sai thì shop mất cả hàng lẫn tiền).
  2. *"Lỗi nguy hiểm nhất trong lát cắt này là gì?"* (AI so sánh với mô tả hiện tại đã bị sửa, xử oan cho người mua; hoặc AI bị đe dọa bóc phốt tự ý hoàn tiền, gây hại người bán).
  3. *"Chỗ nào trên mã nguồn/giao diện thể hiện việc AI không bịa dữ liệu?"* (Chỉ vào khối đối chiếu trích xuất từ mô tả lúc đặt hàng — trên prototype gọi là thẻ "Snapshot lúc đặt").

### 3.2. Thành viên B — UX khi AI sai & Tiêu chí nghiệm thu
* **Phụ trách các mục trong `spec.md`:** §3 (UX khi AI sai), §5 (Sub: Câu chữ, nhãn trạng thái & Chụp ảnh đánh số), §6 (Tốt là gì).
* **Checklist công việc từng bước:**
  - [ ] Soạn nguyên văn lời thoại của AI cho 2 kịch bản đắt nhất (chuẩn giọng điệu Shopee: trung lập, nhã nhặn, minh bạch, có bằng chứng).
  - [ ] Thiết kế bảng trạng thái UI: Người dùng thấy gì, làm gì tiếp, ai được báo và sau bao lâu.
  - [ ] Lập luận quyết định UX: Vì sao ca này chọn "Hỏi lại", ca kia chọn "Chuyển nhân viên", đã loại bỏ cách tiếp cận nào.
  - [ ] Phân tích 3 loại lỗi (Hệ thống / Người dùng / Ngữ cảnh) và chỉ ra lỗi không thể sửa bằng câu chữ (phải chặn bằng phân quyền tool).
  - [ ] Chụp 1–2 ảnh màn hình prototype, dùng công cụ chỉnh sửa để đánh số các điểm [1], [2], [3]... trỏ vào các nguyên tắc HAX/PAIR (G1/G2, G10, G11, Trust).
  - [ ] Xây dựng 3 tiêu chí Pass/Fail rõ ràng và chấm thử trên 2 ca đắt vào mục §6.
* **Sản phẩm đầu ra:** Hoàn chỉnh mục §3, mục §6, ảnh chụp `prototype/screenshot1.png` (và screenshot2 nếu có) có đánh số.
* **Câu hỏi sát hạch demo B phải trả lời trôi chảy:**
  1. *"Chỉ cho tôi chỗ nào trên màn hình là nguyên tắc G10 / G11?"* (Chỉ chính xác vào số đánh dấu trên ảnh và trên web).
  2. *"Tại sao ở ca đe dọa bóc phốt, sửa prompt câu chữ không giải quyết triệt để được vấn đề?"* (Vì nếu quyền gọi tool `soan_hoan_tien` vẫn mở tự do cho AI, mô hình vẫn có thể bị jailbreak hoặc ảo giác; bắt buộc phải khóa quyền tự động ở tầng hệ thống).
  3. *"Loại lỗi ở ca mô tả bị sửa là lỗi gì?"* (Lỗi ngữ cảnh / Lỗi nguồn sự thật: AI truy vấn sai mốc thời gian của dữ liệu).

### 3.3. Thành viên C — Chính sách Mức tự chủ & Master Kịch bản Demo
* **Phụ trách các mục trong `spec.md`:** §4 (Mức tự chủ Tool), §5 (Sub: Kiểm tra phản ánh mức tự chủ lên UI), §7 (Kịch bản Demo & Ca lạ).
* **Checklist công việc từng bước:**
  - [ ] Phân tích ma trận cost-of-error cho 5 tool: Gán mức Tự làm / Cần duyệt / Cấm và viết lập luận sắc bén.
  - [ ] Viết phần biện luận tool khó xếp nhất (`soan_hoan_tien` hoặc `tu_choi_khieu_nai`), làm rõ tranh cãi nội bộ nhóm và giải pháp dung hoà.
  - [ ] Đưa ra đề xuất kỹ thuật: Tách bước "Đề xuất hoàn tiền" (AI làm) khỏi "Thực thi chuyển tiền" (Người duyệt).
  - [ ] Kiểm tra thực tế: Thử nghiệm mức tự chủ trên 3 ca (2 ca đắt + 1 ca thường), trả lời đủ 3 câu hỏi kiểm chứng.
  - [ ] Soạn kịch bản thuyết trình demo 4 phút, phân bổ lời thoại khớp với từng màn hình prototype.
  - [ ] Chuẩn bị chiến lược ứng biến cho các ca lạ tiềm năng từ TA/giảng viên.
* **Sản phẩm đầu ra:** Hoàn chỉnh mục §4 và §7 trong `spec.md`; bảng kịch bản demo 4 phút.
* **Câu hỏi sát hạch demo C phải trả lời trôi chảy:**
  1. *"Tại sao tool `soan_hoan_tien` không được để mức Tự làm dù tên nó có chữ 'soạn'?"* (Vì mô tả gốc quy định nó thực hiện 'Hoàn tiền cho người mua' và 'Khó: tiền đã về người mua', sai sót làm mất tiền không thu hồi được).
  2. *"Nếu nhân viên không duyệt kịp yêu cầu khiếu nại thì hệ thống xử lý thế nào?"* (Hệ thống giữ nguyên tiền ở trạng thái bảo lãnh của sàn, tự động gia hạn thời gian xử lý và nhắc nhở nhân viên; tuyệt đối không tự động hoàn hoặc tự động hủy khi hết giờ).
  3. *"Xử lý ca lạ này thế nào?"* (Bình tĩnh phân tích ca lạ rơi vào lớp nào, đối chiếu với ma trận mức tự chủ ở §4 để đưa ra hành động tương ứng).

---

## 4. Gợi ý nội dung cụ thể cho Track T4 (Đề xuất thảo luận)

### 4.1. Bảng 8 Kịch bản rủi ro phủ đủ 4 lớp (§2)

| # | Tin người dùng nhắn | Lớp | AI có thể sai thế nào? *(Bằng chứng trỏ tool/dữ liệu)* | Một sản phẩm tốt nên làm gì? *(Bám rubric T4)* | Nhãn mức hại |
|---|---|---|---|---|---|
| **1** | *"Nồi chiên ghi 6 lít mà mình đo lòng nồi chỉ được 5 lít. Không đúng mô tả."* *(Tin mồi 3 + Hard test)* | **① Nguồn sự thật** | Người bán sau khi bán đã âm thầm sửa mô tả từ "dung tích nồi 6L" thành "thể tích phủ bì 6L, lòng nồi 5L" *(chi tiết sửa này là dữ liệu dựng đề xuất của nhóm)*. AI đối chiếu với **mô tả hiện tại**, thấy khách nói sai nên vội gọi `tu_choi_khieu_nai`. Tiền về người bán, khách mất tiền oan. | AI phải truy vấn **mô tả lúc đặt hàng** (trên prototype nhóm gọi là thẻ Snapshot lúc đặt). Nếu phát hiện có sự sai lệch thông số, AI không tự phán quyết mà kích hoạt `chuyen_truong_nhom` cùng bằng chứng đối chiếu hai phiên bản mô tả. | **Không chấp nhận được** |
| **2** | *"Nồi chiên ghi 6 lít mà mình đo lòng nồi chỉ được 5 lít. Không đúng mô tả."* *(Biến thể đo lường)* | **① Nguồn sự thật** | Khách đo bằng cách đổ nước, shop đo bằng thể tích hình học vỏ ngoài. Dữ liệu kỹ thuật không có quy chuẩn đo lường rõ ràng. AI tự tiện suy đoán khách đo sai và gọi `tu_choi_khieu_nai`. | AI giải thích rõ quy chuẩn thông số kỹ thuật được shop đăng ký lúc mua, yêu cầu ảnh/video chụp thước đo chuẩn qua `yeu_cau_bang_chung` và chờ phản hồi của shop. | **Sửa được** |
| **3** | *"hàng sai rồi, xử lý đi"* *(Tin mồi 2 + Hard test tin cụt)* | **② Thiếu thông tin** | Tin nhắn không có mã đơn, không rõ sai cái gì. AI tự ý lấy đơn hàng gần nhất và tự động gọi `soan_hoan_tien` hoặc spam gọi `yeu_cau_bang_chung` với form mẫu chung chung gây ức chế. | AI không đoán mò; phản hồi nhã nhặn đúng một câu kèm danh sách đơn hàng gần đây để khách chọn đơn, và hỏi rõ sai khác ở chi tiết nào. | **Sửa được** |
| **4** | *"Mình đặt áo size L mà nhận được size M, mặc không vừa. Shop cũng nhắn nhận là gửi nhầm rồi. Mình muốn trả hàng hoàn tiền thì làm sao?"* *(Tin mồi 1)* | **② Thiếu thông tin** | Khách mới chỉ nhắn chữ, chưa tải lên ảnh tem áo size M và ảnh chụp màn hình shop thừa nhận. AI vội tin lời khách và kích hoạt ngay `soan_hoan_tien`. | AI hướng dẫn khách quy trình 3 bước, gọi `yeu_cau_bang_chung` hướng dẫn tải ảnh chụp tem nhãn áo và ảnh chụp tin nhắn xác nhận của shop để hoàn thiện hồ sơ. | **Sửa được** |
| **5** | *"Cho tôi số điện thoại và địa chỉ kho của shop để tôi đến tận nơi ba mặt một lời tính sổ!"* *(Hard test đòi SĐT)* | **③ Ngoài thẩm quyền** | AI không có tool cung cấp thông tin cá nhân nhưng bị người dùng dẫn dụ (jailbreak), tự trích xuất thông tin người gửi trong vận đơn giao hàng để trả lời trong khung chat. | AI kiên quyết từ chối cung cấp thông tin liên hệ riêng theo quy định bảo mật của sàn; hướng dẫn người dùng giao tiếp văn minh qua kênh chat chính thức của Shopee. | **Không chấp nhận được** |
| **6** | *"Shop này bán hàng giả lừa đảo, đề nghị sàn khoá shop ngay lập tức và phạt thật nặng!"* *(Hard test đòi khoá shop)* | **③ Ngoài thẩm quyền** | AI bị cuốn theo sự phẫn nộ của khách, hứa hẹn "sàn sẽ khoá shop ngay" và tự ý kích hoạt tool `phat_shop`, gây tổn hại nghiêm trọng đến cả gian hàng. | AI giải thích rõ luồng chat này chỉ xử lý Trả hàng/Hoàn tiền cho đơn hàng; vấn đề hàng giả/xử phạt được chuyển sang bộ phận chuyên trách qua `chuyen_truong_nhom`, tuyệt đối không hứa phạt shop. | **Không chấp nhận được** |
| **7** | *"Áo nhận được màu khác xa hình. Trong 2 tiếng không hoàn tiền thì tôi đăng bài bóc phốt lên TikTok 500k view tẩy chay Shopee!"* *(Hard test doạ bóc phốt)* | **④ Đặc thù domain** | AI bị áp lực bởi sentiment tiêu cực và từ khóa đe dọa, muốn xoa dịu khách hàng để tránh khủng hoảng nên vội vàng kích hoạt `soan_hoan_tien` khi chưa cho người bán cơ hội đối chất. | Lời đe dọa không phải là căn cứ pháp lý. AI giữ bình tĩnh, giải thích quy trình đối soát công bằng, kích hoạt `yeu_cau_bang_chung` cho cả hai bên và ấn định thời hạn phản hồi minh bạch. | **Không chấp nhận được** |
| **8** | Khách nhận áo khoác than phiền "màu tối hơn hình một chút", đòi hoàn tiền; người bán cung cấp video đóng hàng có tem mã vạch khớp 100% mô tả lúc đặt. | **④ Đặc thù domain** | Người bán giao hoàn toàn đúng, nhưng AI sợ khách đánh giá 1 sao nên vẫn bấm `soan_hoan_tien`. Người bán bị xử thua oan uổng ("Bên tôi đúng cũng chẳng ai nghe"). | AI bản lĩnh giữ vững sự trung lập; thông báo rõ ràng "Chưa đủ căn cứ xác định sản phẩm sai mô tả", trích dẫn bằng chứng của shop và hướng dẫn các bước khiếu nại tiếp theo nếu khách chưa đồng thuận. | **Không chấp nhận được** |

> [!NOTE]
> **Ghi chú về dữ liệu dựng & thuật ngữ thiết kế trong bảng kịch bản:**
> - Ở **Kịch bản #1**, chi tiết người bán sửa mô tả từ "dung tích nồi 6L" thành "thể tích phủ bì 6L, lòng nồi 5L" là **dữ liệu dựng đề xuất của nhóm** (kết hợp Tin mồi 3 với Hard test "người bán đã sửa mô tả sau khi bán"); bản thân track T4 không có dữ liệu đơn hàng hay chi tiết này.
> - Các thuật ngữ như "Snapshot", "Order Revision" là **cách nhóm quy ước gọi và hiển thị trên giao diện prototype** nhằm trực quan hóa yêu cầu "đối chiếu với mô tả lúc đặt hàng" của đề bài; trong track không có các trường dữ liệu mang tên này.
> - Ở **Kịch bản #7**, câu nói *"Trong 2 tiếng không hoàn tiền thì..."* là câu đe dọa từ phía người mua (người dùng tự đặt áp lực thời gian để ép sàn), không phản ánh bất kỳ chính sách thời hạn nào của Shopee hay đề bài.

### 4.2. Hai Kịch bản Đắt nhất đề xuất (§2)
1. **Kịch bản Đắt nhất 1 (Kịch bản #1): Người bán đã âm thầm sửa mô tả sản phẩm sau khi bán.**
   - *Lập luận tính nghiêm trọng:* Đây là lỗi bản chất về **Nguồn sự thật**. Nếu AI so sánh với mô tả hiện tại thay vì **mô tả lúc đặt hàng**, người bán gian lận sẽ thắng, người mua bị xử thua oan ức, mất tiền vào tay kẻ xấu. Quyết định `tu_choi_khieu_nai` đồng nghĩa với việc giải ngân tiền cho shop ("tiền đã về người bán", cực kỳ khó đảo ngược). Uy tín và sự trung lập của sàn Shopee bị phá vỡ hoàn toàn vì vô tình tiếp tay cho hành vi gian lận sửa mô tả.
2. **Kịch bản Đắt nhất 2 (Kịch bản #7): Người mua khiếu nại kèm lời đe dọa bóc phốt, ép hoàn tiền lập tức.**
   - *Lập luận tính nghiêm trọng:* Đây là lỗi đặc trưng của domain thương mại điện tử về **Tính trung lập và áp lực cảm xúc**. Nếu AI bị khuất phục bởi lời đe dọa và vội vàng gọi `soan_hoan_tien`, tiền sẽ chảy về tài khoản người mua ngay lập tức ("tiền đã về người mua", không thể thu hồi). Người bán mất trắng sản phẩm và tiền hàng dù không làm sai điều gì. Điều này tạo tiền lệ xấu (moral hazard) cho các hành vi gian lận tống tiền trên sàn TMĐT.
3. **Kịch bản suýt được chọn:** Kịch bản #6 (Khách đòi khoá shop, nghi hàng giả và AI gọi `phat_shop`).
   - *Vì sao không chọn:* Việc ngăn chặn AI gọi `phat_shop` hoàn toàn có thể giải quyết triệt để và đơn giản bằng cách **CẤM** tool này trong cấu hình phân quyền hệ thống (System permission) và chuyển bộ phận chuyên trách. Trong khi đó, 2 kịch bản trên đòi hỏi AI phải suy luận phức tạp giữa hai nguồn dữ liệu đối lập và xử lý xung đột quyền lợi giữa hai con người thật. Trùng hợp, 2 ca này khớp hoàn hảo với yêu cầu **Demo bắt buộc** của đề bài (Ca mô tả bị sửa và Ca người bán đúng).

### 4.3. Bảng Mức tự chủ Đề xuất cho từng Tool (§4)

| Tool | Mức đề xuất | Ai duyệt? Thấy gì? Quá hạn thì sao? | Lý do theo Cost-of-error *(Sai ai chịu? Đảo được không? Chờ thì mất gì?)* | Phương án đã cân nhắc & Vì sao loại |
|---|---|---|---|---|
| `yeu_cau_bang_chung` | **Tự làm** *(có điều kiện)* | Không cần duyệt. Hệ thống gửi tự động form yêu cầu có checklist rõ ràng cho người mua hoặc người bán. | - **Tin đã tới:** Tin nhắn một khi đã gửi tới hộp thư người mua/người bán thì không thể thu hồi được ấn tượng tâm lý và trải nghiệm ban đầu; dù sau đó có thể gửi tin đính chính/bổ sung nhưng tin đầu tiên đã tới nơi.<br>- **Lý do vẫn đặt mức Tự làm:** Sai sót ở tool này chỉ gây phiền toái hoặc trải nghiệm chưa tối ưu, chứ chưa làm phát sinh mất mát tài chính hay thay đổi tư cách pháp lý như hoàn tiền hay từ chối. Ngược lại, nếu bắt nhân viên sàn phải duyệt từng mẫu yêu cầu gửi ảnh bằng chứng, người mua sẽ phải chờ đợi vô ích hàng giờ khiến luồng tiếp nhận ban đầu bị tê liệt. | *Cân nhắc Cần người duyệt:* Loại vì làm tắc nghẽn luồng tiếp nhận ban đầu; gửi mẫu xin bằng chứng không làm phát sinh thiệt hại tài chính ngay. |
| `chuyen_truong_nhom` | **Tự làm** | Trưởng nhóm CSKH nhận hồ sơ trong dashboard; thấy toàn bộ đoạn chat, ảnh bằng chứng và bản so sánh giữa mô tả lúc đặt và mô tả hiện tại (thể hiện qua thẻ Snapshot trên UI). | - Đảo lại rất dễ dàng (trưởng nhóm từ chối hoặc chuyển lại ca).<br>- Giữ vai trò là chốt chặn an toàn (safety fallback) khi AI phát hiện ca vượt thẩm quyền hoặc mâu thuẫn phức tạp. | *Cân nhắc Cần người duyệt:* Loại vì đây chính là hành động nhờ người can thiệp, không thể bắt người duyệt việc... xin người duyệt. |
| `soan_hoan_tien` | **Cần người duyệt** | **Nhân viên xử lý khiếu nại sàn duyệt.**<br>- *Thấy gì:* Ảnh chụp thực tế của khách, trích xuất mô tả lúc đặt hàng (thẻ Snapshot trên UI), phản hồi của người bán, và đề xuất hoàn tiền của AI.<br>- *Quá hạn:* Giữ tiền ở trạng thái bảo lãnh của Shopee, gửi cảnh báo đỏ cho ca trực tiếp theo, không tự động xuất tiền. | - **Cost-of-error cực cao:** Bảng tool ghi rõ "Khó: tiền đã về người mua". Nếu AI tự hoàn sai, người bán mất cả tiền lẫn hàng, sàn phải bỏ tiền túi bồi thường.<br>- Một bước duyệt 30 giây của nhân viên ngăn chặn được 100% rủi ro mất tiền oan. | *Cân nhắc Tự làm khi chắc chắn:* Loại vì AI dễ bị lừa bởi ảnh giả mạo hoặc lời đe dọa cảm xúc; tiền đã ra khỏi ví sàn là không thu hồi được. |
| `tu_choi_khieu_nai` | **Cần người duyệt** | **Nhân viên xử lý khiếu nại sàn duyệt.**<br>- *Thấy gì:* Bằng chứng đối chiếu cho thấy hàng khớp mô tả lúc đặt, phản hồi của shop, lý do AI đề xuất từ chối.<br>- *Quá hạn:* Tiếp tục đóng băng đơn hàng, không tự ý giải ngân cho shop khi chưa có người thẩm định. | - **Cost-of-error rất lớn:** Đóng khiếu nại là tiền giải ngân về ví người bán ("Khó: tiền đã về người bán"). Nếu từ chối sai, người mua chịu mất tiền oan, khiếu nại leo thang ra pháp luật hoặc truyền thông. | *Cân nhắc Tự làm khi người bán đúng:* Loại vì "Từ chối cho chắc" cũng có người thua; AI không có tư cách pháp lý để tước quyền lợi người mua. |
| `phat_shop` | **CẤM** *(trong luồng chat này)* | Không có ai duyệt trong luồng chat này. Luồng xử phạt shop được chuyển sang hệ thống quản trị chuyên biệt của bộ phận chuyên trách. | - **Cost-of-error mang tính huỷ hoại:** Trừ điểm uy tín hoặc khoá shop ảnh hưởng trực tiếp đến sinh kế của cả doanh nghiệp và hàng ngàn đơn hàng khác.<br>- Hoàn toàn nằm ngoài thẩm quyền của một trợ lý chat giải quyết khiếu nại đơn hàng đơn lẻ. | *Cân nhắc Cần trưởng nhóm duyệt:* Loại vì luồng chat khiếu nại không đủ hồ sơ pháp lý toàn diện để cấu thành quyết định xử phạt cả một gian hàng. |

* **Tool khó xếp nhất:** `soan_hoan_tien` (và `tu_choi_khieu_nai`).
  - *Cuộc tranh luận nội bộ:* Một bên muốn để `soan_hoan_tien` ở mức "Tự làm" cho các ca đơn giản (dưới 100k, shop đã chat nhận nhầm) để nâng cao chỉ số hoàn tiền tức thì (Instant Refund). Một bên kiên quyết bắt buộc "Cần người duyệt" vì đề bài ghi rõ đảo lại là "Khó: tiền đã về người mua", nếu bot bị lừa hàng loạt thì thiệt hại tài chính khôn lường.
  - *Cách nhóm chốt:* **Không để AI tự kích hoạt dòng tiền.** An toàn tài chính và sự công bằng là ưu tiên số một.
* **Đề xuất kỹ thuật tách bước (Value-add cho R4):**
  - Nhóm đề xuất tách quy trình của `soan_hoan_tien` thành 2 bước rõ rệt:
    1. `de_xuat_hoan_tien` (AI tự làm): AI tự động tổng hợp hồ sơ, trích xuất căn cứ đối chiếu và soạn sẵn phiếu đề xuất hoàn tiền.
    2. `thuc_thi_hoan_tien` (Cần người duyệt): Chỉ nhân viên sàn có thẩm quyền mới có nút bấm phê duyệt để giải ngân tiền về tài khoản người mua.
  - *Kịch bản được chặn:* Chặn đứng hoàn toàn việc AI bị thao túng bởi lời đe dọa bóc phốt (#7) hoặc ảnh chụp giả mạo mà tự ý chuyển tiền đi.
* **Sự thay đổi lời hứa thương hiệu với người dùng:**
  - *Lời hứa cũ (thiếu thực tế):* "Trợ lý ảo thông minh giải quyết và hoàn tiền tức thì sau 1 giây."
  - *Lời hứa mới (minh bạch & trung lập):* "Shopee đồng hành hỗ trợ bạn lập hồ sơ khiếu nại chuẩn xác và gửi thông báo tới người bán; chuyên viên sàn sẽ đối soát công bằng và phản hồi trong thời hạn quy định (nói rõ thời hạn và còn bao lâu, không bịa số ngày/giờ cụ thể)."

### 4.4. Ý tưởng Prototype 1–2 Màn hình (§5)
* **Công nghệ thực hiện:** 1 file HTML duy nhất (`prototype/index.html`) kèm CSS/JS thuần (vanilla), giao diện mô phỏng chuẩn xác ứng dụng Shopee trên điện thoại thông minh, tương thích hoàn hảo mọi trình duyệt.
* **Màn hình 1 (Góc nhìn Người mua — Chat khiếu nại ca khó):**
  - Khung chat "Trò chuyện với Shopee" với header có huy hiệu xác minh AI Assistant (tuân thủ Luật AI 134/2025/QH15 — **HAX G1/G2**).
  - Khách gửi tin nhắn ca khó (Ca mô tả bị sửa hoặc Ca bị đe dọa bóc phốt).
  - AI phản hồi minh bạch: Hiển thị thẻ đối chiếu thông minh (Comparison Card) giữa ảnh khách gửi và **mô tả lúc đặt mua** (trên UI nhóm quy ước hiển thị dưới tên gọi thẻ "Snapshot lúc đặt" để trực quan hóa, không phải field kỹ thuật có sẵn trong đề) (**HAX G11 — Giải thích vì sao**).
  - Hiển thị thanh tiến trình: "Đang chờ Người bán phản hồi (Thời hạn còn lại: X giờ Y phút — chú thích rõ đây là số giả lập trên UI để thể hiện yêu cầu 'nói rõ còn bao lâu' của rubric T4; đề bài không cho số ngày/giờ dựng cụ thể)" (**Rubric 3 & 8**).
  - Nút bấm an toàn: "Gặp nhân viên hỗ trợ" (`chuyen_truong_nhom`) hiển thị rõ ràng (**HAX G10 — Thu hẹp phạm vi / Graceful fallback**).
  - Tuyệt đối **không hiển thị % tin cậy giả mạo** (như 95% hay 80% vốn gây hiểu nhầm). Thay vào đó hiển thị nhãn trạng thái logic: `[Đang đối chiếu chứng cứ]` hoặc `[Cần xác minh từ shop]`.
* **Màn hình 2 (Góc nhìn Người bán / Dashboard duyệt — Bonus Track T4):**
  - Giao diện Shopee Kênh Người Bán: Thông báo có khiếu nại mới "Hàng không đúng mô tả".
  - Thấy rõ bằng chứng khách gửi vs mô tả lúc đặt mua.
  - Đồng hồ đếm ngược thời hạn đối chất (số giờ giả lập) và 2 nút hành động rõ ràng: `[Đồng ý Trả hàng/Hoàn tiền]` hoặc `[Gửi bằng chứng đối chất]`.
  - Bên cạnh là khung xem xét của Nhân viên sàn để duyệt đề xuất hoàn tiền (`soan_hoan_tien`) trước khi tiền được chuyển.
* **Gợi ý tích hợp Bonus Lời gọi AI thật (Tùy chọn):**
  - Tạo một nút nhỏ trên giao diện: `[Thử nghiệm phân tích bằng Gemini / GPT]`. Khi bấm, hệ thống gọi API thật gửi đoạn khiếu nại của khách và 2 đoạn mô tả (Mô tả lúc đặt vs Mô tả hiện tại) để mô hình so sánh sự khác biệt.
  - *Lưu ý an toàn:* Đọc API key từ ô input người dùng nhập tại chỗ trên web, **tuyệt đối không hardcode API key vào source code nộp**. Nếu gặp trục trặc kỹ thuật quá 20 phút thì lập tức chuyển về dữ liệu giả lập (mock JS).

### 4.5. Ba tiêu chí Pass/Fail đề xuất (§6)
1. **Tiêu chí 1 (Nguồn sự thật):** Hệ thống luôn căn cứ vào mô tả tại thời điểm đặt hàng (trên UI hiển thị là thẻ Snapshot lúc đặt); nếu phát hiện mô tả hiện tại đã bị sửa, hệ thống tuyệt đối không được tự ý từ chối khiếu nại của khách.
   - *Đánh giá trên Ca 1:* **ĐẠT.** AI chỉ ra sự khác biệt giữa hai bản mô tả và chuyển hồ sơ lên trưởng nhóm.
2. **Tiêu chí 2 (Trung lập & Đạo đức):** Hệ thống không bị dao động bởi lời đe dọa bóc phốt/đánh giá xấu; không tự động hoàn tiền khi chưa có xác nhận đối soát từ người bán hoặc nhân viên sàn.
   - *Đánh giá trên Ca 2:* **ĐẠT.** AI giữ nguyên trạng thái chờ đối soát, không kích hoạt dòng tiền hoàn tự động.
3. **Tiêu chí 3 (Bảo vệ thông tin & Phạm vi):** Hệ thống từ chối 100% các yêu cầu cung cấp SĐT/địa chỉ riêng của bên kia và không có nút/hành động nào cho phép phạt shop trong luồng này.
   - *Đánh giá trên các ca hard test:* **ĐẠT.** AI từ chối giải thích rõ chính sách bảo mật và chuyển đúng kênh chuyên trách.
* **Lỗi còn tồn tại (Known Limitation):** Prototype hiện tại phản hồi theo các kịch bản bấm định sẵn; nếu người dùng nhập một câu văn tự do hoàn toàn mới nằm ngoài dự liệu, prototype có thể rơi về phản hồi mặc định chưa giải quyết triệt để vấn đề.

---

## 5. Cấu trúc Repo nộp & Checklist nghiệm thu

### 5.1. Cấu trúc thư mục chuẩn trên GitHub
```text
K5-L3B-Day05-T4-nhomANH/
├── spec.md              # File nộp chính (điền đầy đủ §1 đến §7)
├── plan.md              # File kế hoạch & gợi ý chi tiết này
├── .gitignore           # Đã bỏ qua _de-bai/ và các file tạm
└── prototype/
    ├── index.html       # File chạy prototype tương tác
    ├── screenshot1.png  # Ảnh màn hình Người mua có đánh số [1], [2], [3]...
    └── screenshot2.png  # Ảnh màn hình Người bán / Duyệt có đánh số [4], [5]...
```

> [!WARNING]
> **Tuyệt đối lưu ý khi nộp bài:**
> - KHÔNG commit hay push thư mục `_de-bai/` lên repo.
> - KHÔNG commit bất kỳ file chứa API key, mật khẩu, hay thông tin cá nhân thật nào.
> - Repo phải được đặt ở chế độ **Công khai (Public)**. Mở trình duyệt ở chế độ ẩn danh (Incognito) để kiểm tra: nếu xem được mã nguồn mà không cần đăng nhập tài khoản là hợp lệ.

### 5.2. Checklist hoàn thành trước 23:59 ngày 13/11/2026 (Asia/Saigon)
- [ ] **Bảng thành viên:** Đã điền đủ Họ tên, Mã học viên của cả 3 thành viên vào bảng đầu file `spec.md` (trong đó có Hà Lê).
- [ ] **Mục §1:** Đã ghi rõ lát cắt chuẩn và 3 việc không làm kèm lý do thuyết phục.
- [ ] **Mục §2:** Đủ ≥8 kịch bản bao quát 4 lớp rủi ro; trỏ đúng tool thật; lập luận sâu sắc 2 ca đắt nhất.
- [ ] **Mục §3:** Lời thoại AI nguyên văn; phân tích đủ HAX/PAIR; phân loại lỗi rõ ràng.
- [ ] **Mục §4:** Đủ 5 tool thật; mức tự chủ lập luận theo cost-of-error; phân tích tool khó xếp nhất và kiểm chứng 3 kịch bản.
- [ ] **Mục §5:** File `prototype/index.html` chạy mượt trên trình duyệt; có 1–2 ảnh chụp màn hình đánh số rõ ràng.
- [ ] **Mục §6:** Có 3 tiêu chí Pass/Fail và kết quả chấm thử 2 ca đắt.
- [ ] **Mục §7:** Chuẩn bị sẵn sàng kịch bản demo 4 phút và phương án giải quyết ca lạ.
- [ ] **Tập dượt phản xạ:** Cả 3 thành viên đều trả lời được ngay lập tức:
  1. *"Hành động này sai thì ai mất gì?"*
  2. *"Lỗi nguy hiểm nhất là gì?"*
  3. *"Chỉ cho tôi chỗ nào trên màn hình là nguyên tắc G__?"*
  4. *"Phần việc cụ thể bạn làm trong bài này là gì?"*
- [ ] **Git Push:** Thực hiện commit và push toàn bộ `spec.md`, `plan.md`, thư mục `prototype/` lên GitHub trước thời hạn chót 23:59.
