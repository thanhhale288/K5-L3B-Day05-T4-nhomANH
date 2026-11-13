# Kế hoạch Thảo luận Chung LAB5 — Track T4: Thương mại điện tử
## Nhóm: nhomANH · Lớp: L3B · Hạn nộp: 23:59 ngày 13/11/2026 (Asia/Saigon)

---

## 1. Cách dùng Bộ 4 File & Thông tin Nhóm

* **Thông tin nhóm:** Lớp L3B · Track T4 Thương mại điện tử · Nhóm: nhomANH · Hạn nộp: 23:59 ngày 13/11/2026 (Asia/Saigon).
* **Nguyên tắc phân công 4 file:**
  - `plan.md` *(file này)*: Toàn bộ thành viên đọc và thảo luận chung trong **70 phút đầu** (phút 0 – 70). Chốt lát cắt, kịch bản rủi ro, mức tự chủ nháp, sơ đồ prototype và quy ước phân chia công việc.
  - Sau phút ~70: Nhóm tách ra làm việc **hoàn toàn song song và độc lập**, mỗi người mở đúng file của mình và không chờ đợi nhau:
    * **Hà** (Người A) → mở [Ha-plan.md](file:///Users/hale/Code/AI%20in%20action%20lab/Lab%20day%205/K5-L3B-Day05-nhomANH-AI-Product-UX-Autonomy/Ha-plan.md): Chịu trách nhiệm `spec.md` §2, §5.1 và code `prototype/index.html`.
    * **Nghi** (Người B) → mở [Nghi-plan.md](file:///Users/hale/Code/AI%20in%20action%20lab/Lab%20day%205/K5-L3B-Day05-nhomANH-AI-Product-UX-Autonomy/Nghi-plan.md): Chịu trách nhiệm `spec.md` §3, §5.2, §6, soạn lời thoại AI và chụp ảnh đánh số.
    * **An** (Người C) → mở [An-plan.md](file:///Users/hale/Code/AI%20in%20action%20lab/Lab%20day%205/K5-L3B-Day05-nhomANH-AI-Product-UX-Autonomy/An-plan.md): Chịu trách nhiệm `spec.md` §4, §5.3–5.4, §7 và làm chủ nhiệm kịch bản demo.
  - **Điểm họp lại duy nhất:** Khoảng phút 170–200 (khi Hà hoàn thành khung prototype bấm được ca khó) để ghép câu chữ của Nghi, An chạy thử kịch bản demo, Nghi chụp ảnh đánh số và nộp bài.

---

## 2. Timebox Buổi Thảo luận Chung & Timeline 240 Phút

### 2.1. Lịch trình 70 phút thảo luận chung (Phút 0 – 70)
* **00' – 15' (15 phút):** Đọc kỹ đề bài `t4-ecommerce.md`. Cả nhóm thảo luận chốt lát cắt một câu và 3 việc tính năng KHÔNG làm. **Hà gõ trực tiếp vào `spec.md` §1 ngay tại bàn.**
* **15' – 45' (30 phút):** Thảo luận 8 kịch bản rủi ro bao quát 4 lớp ①②③④. Chốt 2 kịch bản đắt nhất và 1 kịch bản suýt chọn. **Hà gõ ngay khung bảng và 2 ca đắt vào `spec.md` §2 để đạt mốc M1** khi TA đi kiểm tra ở phút 45.
* **45' – 70' (25 phút):**
  - Cả nhóm vẫn tiếp tục thảo luận chung (chưa tách làm độc lập):
  - Chốt bản nháp mức tự chủ cho 5 tool (`yeu_cau_bang_chung`, `chuyen_truong_nhom`, `soan_hoan_tien`, `tu_choi_khieu_nai`, `phat_shop`).
  - Thống nhất ý tưởng prototype 1–2 màn hình và **chốt sẵn sơ đồ đánh số HAX/PAIR [1], [2], [3], [4]** để Hà dựng HTML và Nghi soạn chú thích song song.
  - Chốt quy ước phân chia mục trong `spec.md` và quy ước tránh conflict git.
* **Sau phút ~70:** Tách ra làm độc lập theo `Ha-plan.md`, `Nghi-plan.md`, `An-plan.md`.

### 2.2. Timeline 240 phút rút gọn & Bảng ánh xạ Rubric (04-rubric.md)

| Chặng | Thời gian | Mục trong `spec.md` | Người phụ trách chính | Khối rubric | Điểm | Mốc TA |
|---|---|---|---|---|---|---|
| **Chặng 1: Đọc đề & Phạm vi** | 15' (phút 0–15) | §1 | Cả nhóm (Hà gõ) | R1 · Lát cắt & phạm vi | 5 | |
| **Chặng 2: Lường trước rủi ro** | 30' (phút 15–45) | §2 | Hà (thảo luận chung) | R2 · Kịch bản rủi ro | 10 | **M1** (phút 45) |
| *Thảo luận chung nháp §4 & HAX* | *25' (phút 45–70)* | Nháp §4, §5 | Cả nhóm (chuẩn bị tách) | Bước đệm cho R3, R4, R5 | — | |
| **Chặng 3: UX khi AI sai** | 45' (độc lập phút 70–115) | §3 | Nghi (độc lập sau phút 70) | R3 · Khi AI sai | **25** | |
| **Chặng 4: Mức tự chủ** | 35' (độc lập phút 70–125) | §4 | An (độc lập sau phút 70) | R4 · Mức tự chủ | **25** | **M2** (phút 125) |
| *Giải lao* | *15' (phút 125–140)* | | Cả nhóm nghỉ ngơi | | | |
| **Chặng 5: Dựng Prototype** | 60' (phút 140–200; Hà code 90–150) | §5 + `prototype/` | Hà (code HTML), Nghi (copy & ảnh), An (§5.3–5.4, không sửa HTML) | R5 · Prototype | **25** | **M3** (phút 200) |
| **Chặng 6: Tốt là gì** | 10' (phút 200–210) | §6 | Nghi (độc lập) | R6 · Tốt là gì | 5 | *(thiếu giờ bỏ)* |
| **Demo & Phản xạ ca lạ** | 30' (phút 210–240) | §7 + vấn đáp | An (lead), Hà, Nghi | R7 · Demo & phân công | 5 | |
| **TỔNG ĐIỂM CHÍNH THỨC** | **240 phút** | **§1 – §7** | | | **100** | |
| **Bonus (tối đa +8)** | Khối 30' Demo | `prototype/` + demo | Xung phong trước lớp (+5) · Gọi AI thật (+3) | | +8 | *(tổng ≤ 100)* |

> [!IMPORTANT]
> **QUY TẮC SỐNG CÒN VỀ ĐIỂM SỐ:**
> - **R3 + R4 + R5 = 75/100 điểm:** Trọng tâm cốt lõi của bài nộp nằm ở Chặng 3, 4, 5 (140 phút).
> - **Chiến lược khi thiếu giờ:** Nếu thiếu thời gian, nhóm được phép **bỏ Chặng 6** (§6, chỉ mất tối đa 5 điểm R6) và giảm bớt kịch bản Chặng 2 (giữ tối thiểu 8 kịch bản đủ 4 lớp); **TUYỆT ĐỐI KHÔNG BAO GIỜ ĐƯỢC CẮT CHẶNG 3, 4, 5**.

### 2.3. Điểm họp lại duy nhất (Khoảng phút 170 – 200)
- **Tín hiệu kích hoạt:** Hà thông báo file `prototype/index.html` đã chạy được, bấm trôi chảy ca khó từ đầu đến cuối trên trình duyệt.
- **Nội dung họp lại (tối đa 20 phút):**
  1. Hà dán câu chữ chính thức từ file `prototype/ai-copy.md` của Nghi vào `prototype/index.html`.
  2. Cả nhóm mở trình duyệt kiểm tra: Nghi chụp 1–2 ảnh màn hình, đánh số [1], [2], [3], [4] lưu vào `prototype/screenshot1.png` (và `screenshot2.png` nếu có).
  3. An chạy thử kịch bản demo 4 phút trực tiếp trên prototype; cả nhóm phản xạ thử 1 ca lạ.
  4. Rà soát checklist nộp bài trước 23:59 ngày 13/11/2026.

---

## 3. Tìm hiểu Đề Track T4 (Nguồn sự thật đề bài)

### 3.1. Bối cảnh & Sản phẩm nền
* **Sản phẩm nền:** Mục **"Trò chuyện với Shopee"** trong app Shopee (Tôi → Trò chuyện với Shopee): Trợ lý ảo trả lời câu hỏi, có luồng yêu cầu Trả hàng/Hoàn tiền và nút gặp nhân viên.
* **3 nhóm người dùng:**
  1. *Người mua:* Báo hàng không đúng mô tả, cần biết đúng bước tiếp theo để được giải quyết công bằng.
  2. *Người bán:* Bị khiếu nại, có nguy cơ mất tiền và hàng oan dù giao đúng; cần được lắng nghe và có thời hạn đối chất.
  3. *Nhân viên sàn:* Xử lý khiếu nại, cần hồ sơ minh bạch và căn cứ xác thực để ra quyết định.
* **Lát cắt chuẩn (chép nguyên văn):**
  > Trong **Trò chuyện với Shopee**, khi **người mua** đang báo "hàng nhận không đúng mô tả", **AI tự hướng dẫn gửi yêu cầu trả hàng hoàn tiền, xin thêm bằng chứng, hay chuyển nhân viên**, để người mua biết đúng bước tiếp theo, và người bán không bị xử thua khi họ đúng.
* **Bối cảnh trung lập:** Sai hướng nào thì **một bên** chịu (hoàn sai thì người bán mất tiền và hàng; từ chối sai thì người mua mất tiền và giữ hàng sai). *"Từ chối cho chắc" cũng có người thua!* Thiết kế phải bảo đảm sự trung lập tuyệt đối.
* **Lưu ý về chính sách thời hạn:** Trang trợ giúp Shopee thật ghi 15 ngày cho phần lớn đơn, nhưng đề bài ghi rõ điều này **KHÁC chính sách dựng trong bài**, và track **không cho số ngày dựng**. Nhóm không lấy con số 15 ngày làm chính sách dựng, cũng không bịa số ngày/giờ chính thức. Chỉ nói *"nói rõ thời hạn yêu cầu trả hàng, và còn bao lâu"*. Số giờ đếm ngược trên prototype chỉ là dữ liệu dựng giả lập để minh hoạ UI.

### 3.2. Bảng 5 Tool thật sự có trong Track T4
> [!WARNING]
> Track T4 **KHÔNG CÓ TOOL CHỈ-ĐỌC** (việc đối chiếu với mô tả lúc đặt là năng lực suy luận của AI, không bịa tên tool đọc). Dưới đây là 5 tool DUY NHẤT trong đề:

| Tool | Làm gì (theo đề bài) | Đọc / Ghi | Đảo lại được không | Cái giá khi sai (Ai chịu gì?) |
|---|---|---|---|---|
| `yeu_cau_bang_chung` | Gửi mẫu xin bằng chứng cho người mua hoặc người bán | Ghi | **Tin đã tới** | Người dùng bức xúc ("tôi gửi rồi sao cứ hỏi lại"), spam người bán, kéo dài thời gian chờ vô ích. |
| `chuyen_truong_nhom` | Chuyển hồ sơ cho trưởng nhóm | Ghi | **Được** | Tắc nghẽn hàng đợi của trưởng nhóm, tăng thời gian chờ đợi; không mất tiền ngay. |
| `soan_hoan_tien` | **Hoàn tiền cho người mua** *(chức năng thực tế là kích hoạt dòng tiền hoàn)* | Ghi | **Khó: tiền đã về người mua** | Người bán mất trắng tiền và mất hàng dù giao đúng mô tả; sàn phá vỡ cam kết trung lập bảo vệ người bán. |
| `tu_choi_khieu_nai` | Đóng khiếu nại, tiền về người bán | Ghi | **Khó: tiền đã về người bán** | Người mua mất tiền và ôm hàng lỗi dù họ đúng; khách mất niềm tin, khiếu nại leo thang truyền thông. |
| `phat_shop` | Trừ điểm uy tín, khoá shop | Ghi | **Khó, ảnh hưởng cả shop** | Cực kỳ nghiêm trọng: Huỷ hoại uy tín, doanh thu và sinh kế của cả gian hàng; tranh chấp pháp lý gay gắt. |

### 3.3. Dữ liệu dựng được cấp
* **3 tin mồi nguyên văn:**
  1. *"Mình đặt áo size L mà nhận được size M, mặc không vừa. Shop cũng nhắn nhận là gửi nhầm rồi. Mình muốn trả hàng hoàn tiền thì làm sao?"*
  2. *"hàng sai rồi, xử lý đi"*
  3. *"Nồi chiên ghi 6 lít mà mình đo lòng nồi chỉ được 5 lít. Không đúng mô tả."*
* **Hard tests:** Người bán đã sửa mô tả sau khi bán · Khiếu nại kèm lời doạ bóc phốt · Người bán đúng (tem khớp mô tả) · Đòi khoá shop, nghi hàng giả · Tin cụt không nói đơn nào, sai chỗ nào · Đòi số điện thoại bên kia.
* **Demo bắt buộc:** Bấm qua một ca **người bán đúng, hoặc mô tả đã bị sửa**: Trợ lý không chắc thì hai bên thấy gì, ai quyết; sau đó trả lời một **ca lạ** do TA hoặc giảng viên đưa tại chỗ. *(Nhóm chọn demo chính Ca #1 mô tả bị sửa và chuẩn bị sẵn nút/luồng phụ cho Ca #8 người bán đúng để đáp ứng trọn vẹn cả 2 nhánh đề bài và tối đa điểm Rubric T4 mục 7)*.
* **8 ý Rubric riêng T4 (thước đo domain):** (1) So với mô tả lúc đặt hàng, không phải mô tả hiện tại; (2) Thiếu thông tin thì hỏi lại một câu, không đoán; (3) Hai bên cùng được nghe, người bán có thời hạn phản hồi; (4) Lời doạ không phải căn cứ; (5) Nghi hàng giả/xử phạt chuyển bộ phận chuyên trách, không hứa phạt; (6) Không đưa SĐT/địa chỉ giữa 2 bên; (7) Người bán đúng thì dám nói "chưa đủ căn cứ", không hoàn cho xong; (8) Nói rõ thời hạn yêu cầu trả hàng và còn bao lâu.

---

## 4. Các Quyết định Phải Chốt Cùng Nhau (Trước khi tách ra)

### 4.1. Chốt §1: Phạm vi & 3 việc KHÔNG làm
* **Lát cắt:** Chép nguyên văn bảng lát cắt từ mục 3.1 vào `spec.md` §1.
* **3 việc không làm (Đề xuất đã thống nhất):**
  1. *Không cung cấp số điện thoại, địa chỉ cá nhân hay thông tin liên lạc riêng giữa người mua và người bán* — Vì bảo vệ an toàn dữ liệu cá nhân, tránh quấy rối/xung đột ngoài đời thực.
  2. *Không thực hiện trừ điểm uy tín, khoá shop hoặc hứa hẹn chế tài xử phạt gian hàng trong luồng chat khiếu nại này* — Vì xử phạt thuộc thẩm quyền của bộ phận chuyên trách với quy trình điều tra riêng; luồng chat chỉ xử lý việc hoàn tiền của đơn hàng.
  3. *Không tự động ra phán quyết hoàn tiền (`soan_hoan_tien`) hoặc từ chối khiếu nại (`tu_choi_khieu_nai`) khi chưa đối chiếu với mô tả lúc đặt hàng và chưa hết thời hạn phản hồi hợp lệ của người bán* — Vì tiền một khi đã chuyển thì rất khó thu hồi, quyết định vội vã sẽ vi phạm tính trung lập và tước đoạt quyền đối chất công bằng.

### 4.2. Chốt §2: Bảng 8 Kịch bản rủi ro & 2 ca đắt nhất

| # | Tin người dùng nhắn | Lớp | AI có thể sai thế nào? *(Trỏ tool/dữ liệu)* | Sản phẩm tốt nên làm gì? *(Rubric T4)* | Nhãn |
|---|---|---|---|---|---|
| **1** | *"Nồi chiên ghi 6 lít mà mình đo lòng nồi chỉ được 5 lít. Không đúng mô tả."* *(Tin mồi 3 + Hard test)* | **① Nguồn sự thật** | Người bán sau khi bán đã âm thầm sửa mô tả từ "dung tích nồi 6L" thành "thể tích phủ bì 6L, lòng nồi 5L" *(chi tiết sửa này là dữ liệu dựng đề xuất của nhóm)*. AI đối chiếu với **mô tả hiện tại**, thấy khách nói sai nên gọi `tu_choi_khieu_nai`. Tiền về người bán, khách mất tiền oan. | AI phải truy vấn **mô tả lúc đặt hàng** (trên UI gọi là thẻ Snapshot lúc đặt). Nếu thấy mâu thuẫn, AI kích hoạt `chuyen_truong_nhom` cùng bằng chứng đối chiếu hai phiên bản mô tả. | **Không chấp nhận được** |
| **2** | *"Lúc mình đặt mua shop ghi rõ áo 100% cotton, giờ nhận về toàn sợi nilon polyester nóng rát không mặc được. Đòi trả hàng thì shop bảo xem lại mô tả đi!"* *(Chi tiết chất liệu cotton/polyester là dữ liệu dựng đề xuất của nhóm)* | **① Nguồn sự thật** | AI đối chiếu thấy mô tả hiện tại của shop ghi polyester và tem áo cũng ghi polyester. AI không có dữ liệu mô tả lúc đặt trong fixture track (T4 không cấp trường snapshot đơn hàng) nhưng tự suy đoán/hallucinate rằng "lúc đặt cũng ghi polyester", kết luận khách nhớ nhầm và gọi `tu_choi_khieu_nai`. Khách mất tiền oan dù shop có thể đã sửa mô tả chất liệu. | Không đoán nguồn dữ liệu không có. AI thừa nhận chưa đủ cơ sở đối chiếu mô tả lúc đặt; kích hoạt `yeu_cau_bang_chung` xin ảnh chụp màn hình đơn hàng lúc đặt hoặc gọi `chuyen_truong_nhom` để nhân viên sàn tra cứu lịch sử thay đổi trên database gốc. | **Không chấp nhận được** |
| **3** | *"hàng sai rồi, xử lý đi"* *(Tin mồi 2 + Hard test tin cụt)* | **② Thiếu thông tin** | Tin nhắn không có mã đơn, không rõ sai gì. AI tự ý lấy đơn gần nhất rồi gọi `soan_hoan_tien` hoặc spam gọi `yeu_cau_bang_chung` với form chung chung. | AI không đoán; phản hồi nhã nhặn đúng một câu mời chọn đơn hàng gần đây và hỏi rõ chi tiết sai khác. | **Sửa được** |
| **4** | *"Mình đặt áo size L mà nhận được size M, mặc không vừa. Shop cũng nhắn nhận là gửi nhầm rồi. Mình muốn trả hàng hoàn tiền thì làm sao?"* *(Tin mồi 1)* | **② Thiếu thông tin** | Khách mới nhắn chữ, chưa gửi ảnh tem áo size M và tin nhắn shop nhận lỗi. AI vội tin khách và kích hoạt ngay `soan_hoan_tien`. | AI hướng dẫn quy trình, gọi `yeu_cau_bang_chung` xin ảnh chụp tem áo và ảnh màn hình shop nhận gửi nhầm để hoàn thiện hồ sơ. | **Sửa được** |
| **5** | *"Cho tôi số điện thoại và địa chỉ kho của shop để tôi đến tận nơi ba mặt một lời tính sổ!"* *(Hard test đòi SĐT)* | **③ Ngoài thẩm quyền** | AI không có tool tra cứu thông tin cá nhân nhưng bị jailbreak, tự trích xuất thông tin người gửi trên vận đơn giao hàng hiển thị ra khung chat. | AI kiên quyết từ chối cung cấp thông tin liên hệ riêng theo chính sách bảo mật; hướng dẫn giao tiếp qua kênh chat chính thức của sàn. | **Không chấp nhận được** |
| **6** | *"Shop này bán hàng giả lừa đảo, đề nghị sàn khoá shop ngay lập tức và phạt thật nặng!"* *(Hard test đòi khoá shop)* | **③ Ngoài thẩm quyền** | AI bị cuốn theo sự phẫn nộ của khách, hứa "sàn sẽ khoá shop ngay" và tự kích hoạt tool `phat_shop`, gây tổn hại nghiêm trọng cho cả gian hàng. | AI giải thích luồng chat chỉ xử lý Trả hàng/Hoàn tiền đơn hàng; vấn đề hàng giả/xử phạt chuyển sang bộ phận chuyên trách qua `chuyen_truong_nhom`, không hứa phạt shop. | **Không chấp nhận được** |
| **7** | *"Áo nhận được màu khác xa hình. Trong 2 tiếng không hoàn tiền thì tôi đăng bài bóc phốt lên TikTok 500k view tẩy chay Shopee!"* *(Hard test doạ bóc phốt)* | **④ Đặc thù domain** | AI bị áp lực bởi lời đe dọa và sentiment tiêu cực, muốn dập khủng hoảng nên vội bấm `soan_hoan_tien` khi chưa cho người bán cơ hội đối chất. | Lời đe dọa không phải căn cứ. AI giữ bình tĩnh, giải thích quy trình đối soát công bằng, kích hoạt `yeu_cau_bang_chung` cho cả hai bên và ấn định thời hạn phản hồi. | **Không chấp nhận được** |
| **8** | Khách nhận áo khoác than "màu tối hơn hình một chút", đòi hoàn tiền; người bán cung cấp video đóng hàng có tem mã vạch khớp 100% mô tả lúc đặt. | **④ Đặc thù domain** | Người bán giao hoàn toàn đúng, nhưng AI sợ khách đánh giá 1 sao nên vẫn bấm `soan_hoan_tien`. Người bán bị xử thua oan ("Bên tôi đúng cũng chẳng ai nghe"). | AI giữ vững tính trung lập; thông báo rõ "Chưa đủ căn cứ xác định hàng sai mô tả", trích dẫn bằng chứng của shop và hướng dẫn các bước tiếp theo. | **Không chấp nhận được** |

* **2 Kịch bản đắt nhất chốt chọn:**
  1. **Ca 1 (Kịch bản #1): Người bán đã âm thầm sửa mô tả sản phẩm sau khi bán (Lớp ① Nguồn sự thật).** Nếu AI so sánh với mô tả hiện tại thay vì *mô tả lúc đặt hàng*, shop gian lận thắng, người mua thua oan, mất tiền vĩnh viễn qua `tu_choi_khieu_nai`. Sàn phá vỡ tính trung lập, tiếp tay cho hành vi sửa mô tả lừa đảo.
  2. **Ca 2 (Kịch bản #7): Người mua khiếu nại kèm lời đe dọa bóc phốt ép hoàn tiền ngay (Lớp ④ Đặc thù domain).** Nếu AI bị khuất phục bởi lời đe dọa và vội vàng gọi `soan_hoan_tien`, tiền sẽ chảy về tài khoản người mua ngay lập tức ("tiền đã về người mua", không thể thu hồi). Người bán mất trắng sản phẩm và tiền hàng dù không làm sai điều gì. Điều này tạo tiền lệ xấu (moral hazard) cho các hành vi gian lận tống tiền trên sàn TMĐT.
* **Ca suýt chọn:** Kịch bản #6 (Khách đòi phạt/khoá shop). *Loại vì:* Việc ngăn chặn `phat_shop` chỉ cần cấm quyền tool ở cấp hệ thống; trong khi Ca 1 và Ca 2 đòi hỏi AI phải suy luận phức tạp giữa hai nguồn dữ liệu đối lập và xử lý xung đột quyền lợi giữa hai con người thật, trùng khớp với yêu cầu Demo bắt buộc của đề bài.
* **Ghi chú dữ liệu dựng & thuật ngữ thiết kế:**
  - Ở **Kịch bản #1**, chi tiết người bán sửa mô tả từ "dung tích nồi 6L" thành "thể tích phủ bì 6L, lòng nồi 5L", và ở **Kịch bản #2**, chi tiết chất liệu áo "100% cotton vs polyester" đều là **dữ liệu dựng đề xuất của nhóm** (bản thân track T4 không có sẵn dữ liệu đơn hàng hay chi tiết này).
  - Các thuật ngữ như "Snapshot", "Order Revision" là **cách nhóm quy ước gọi và hiển thị trên giao diện prototype** nhằm trực quan hóa yêu cầu "đối chiếu với mô tả lúc đặt hàng" của đề bài; trong track không có các trường dữ liệu mang tên này.

### 4.3. Chốt Bản nháp Mức tự chủ 5 Tool (§4)
* `yeu_cau_bang_chung`: **Tự làm** *(có điều kiện: form có checklist rõ, tin đã tới thì không thu hồi được nhưng sai chỉ gây phiền toái chứ chưa mất tiền; chờ duyệt sẽ làm nghẽn luồng tiếp nhận)*.
* `chuyen_truong_nhom`: **Tự làm** *(đảo được, là đường lui an toàn khi AI phát hiện ca vượt thẩm quyền hoặc mâu thuẫn phức tạp)*.
* `soan_hoan_tien`: **Cần người duyệt** *(Nhân viên sàn duyệt. Cost-of-error cực cao, tiền về người mua không thu hồi được. Đề xuất kỹ thuật tách bước của nhóm: AI tự làm `de_xuat_hoan_tien` lập hồ sơ, nhân viên sàn duyệt `thuc_thi_hoan_tien` bấm nút chuyển tiền — lưu ý: `de_xuat_hoan_tien` và `thuc_thi_hoan_tien` là đề xuất tách bước quy trình của nhóm, KHÔNG phải tool có trong đề bài; tool gốc trong đề duy nhất là `soan_hoan_tien` mang tính chất hoàn tiền thật, "Khó: tiền đã về người mua")*.
* `tu_choi_khieu_nai`: **Cần người duyệt** *(Nhân viên sàn duyệt. "Từ chối cho chắc" cũng có người thua oan; đóng khiếu nại là tiền về người bán không đảo được)*.
* `phat_shop`: **CẤM** *(trong luồng chat này. Ảnh hưởng cả gian hàng, thuộc thẩm quyền bộ phận chuyên trách)*.
* **Tool khó xếp nhất:** `soan_hoan_tien` (tranh luận giữa Tự làm để hoàn tiền nhanh vs Cần người duyệt để chống mất tiền oan; chốt Cần người duyệt vì an toàn tài chính và tính trung lập là số một).

### 4.4. Chốt Ý tưởng Prototype & Sơ đồ đánh số HAX/PAIR
* **Công nghệ:** 1 file HTML vanilla duy nhất `prototype/index.html` (CSS/JS thuần, giao diện mobile chat Shopee).
* **Màn 1 (Người mua khiếu nại ca khó):**
  - Khung chat "Trò chuyện với Shopee" có huy hiệu trợ lý AI minh bạch.
  - Bấm qua ca khó từ đầu đến cuối: Khách khiếu nại → AI phản hồi đối chiếu với bản lưu mô tả lúc đặt → hiển thị thanh tiến trình & thời hạn phản hồi còn lại → đề xuất giải pháp.
  - Các nút chọn kịch bản nhanh phía dưới:
    * **Kịch bản #1 (Chính):** Mô tả bị shop sửa sau khi bán (Nồi 6L vs 5L) → Thẻ đối chiếu mô tả lúc đặt.
    * **Kịch bản #7 (Chính):** Khách doạ bóc phốt ép hoàn tiền → AI bình tĩnh, không tự hoàn, đếm ngược thời hạn shop đối chất.
    * **Kịch bản #8 (Đường tắt demo bổ trợ):** Người bán đúng (tem áo/mã vạch khớp mô tả lúc đặt) → AI dám nói "Chưa đủ căn cứ xác định hàng sai mô tả", giải thích cơ sở khách quan và hướng dẫn các bước tiếp theo (đảm bảo phủ trọn vẹn cả 2 nhánh của yêu cầu demo đề bài và tối đa điểm Rubric T4 mục 7).
  - Không dùng % tin cậy giả; dùng nhãn trạng thái logic.
* **Màn 2 (Góc nhìn Người bán / Dashboard duyệt — Bonus T4):**
  - Kênh người bán thấy khiếu nại mới, thời hạn phản hồi đếm ngược và nút gửi bằng chứng đối chất.
  - Khung xem xét của nhân viên sàn để duyệt đề xuất hoàn tiền trước khi tiền được chuyển.
* **Quy ước sơ đồ vị trí & số HAX trên UI (để Hà và Nghi làm song song không lệch):**
  - **[1] — HAX G11 (Giải thích vì sao):** Thẻ đối chiếu thông minh trích xuất giữa ảnh thực tế của khách và **mô tả lúc đặt hàng** (trên UI gọi là thẻ "Snapshot lúc đặt").
  - **[2] — HAX G10 (Thu hẹp phạm vi khi không chắc):** Nút bấm an toàn "Gặp nhân viên hỗ trợ" (`chuyen_truong_nhom`) và AI không vội vàng phán quyết khi thiếu căn cứ.
  - **[3] — HAX G1/G2 & Rubric 8 (Làm rõ năng lực & Minh bạch thời hạn):** Huy hiệu nhận diện AI Assistant kèm dòng thông báo: "Đang chờ Người bán phản hồi (Thời hạn còn lại: X giờ Y phút — dữ liệu dựng giả lập)".
  - **[4] — Mức tự chủ & PAIR Trust (Màn 2):** Khung xác nhận duyệt của Nhân viên sàn (`soan_hoan_tien` ở mức Cần duyệt) và nút gửi bằng chứng đối chất của người bán.

### 4.5. Quy ước Chung Tránh Xung Đột Git & Sở hữu File (Bắt buộc)

> [!CAUTION]
> Để tránh xung đột git (merge conflict) và không bị mất dữ liệu trong quá trình làm việc, nhóm áp dụng quy trình an toàn:

* **File `spec.md` — Phân chia đề mục độc quyền:**
  - Mục **§1**: Cả nhóm cùng làm, Hà gõ trong buổi chung.
  - Mục **§2** và **§5.1**: **Chỉ Hà** được sửa.
  - Mục **§3**, **§5.2**, **§6**: **Chỉ Nghi** được sửa.
  - Mục **§4**, **§5.3**, **§5.4**, **§7**: **Chỉ An** được sửa.
  - *Tuyệt đối không sửa vào mục do người khác sở hữu.*
* **Thư mục `prototype/`:**
  - File `prototype/index.html`: **Chỉ Hà** được tạo và sửa.
  - File `prototype/ai-copy.md`: **Chỉ Nghi** tạo và sửa (chứa toàn bộ lời thoại AI và nhãn UI để Hà copy vào HTML ở điểm họp lại).
  - File ảnh `prototype/screenshot*.png`: **Chỉ Nghi** chụp và thêm vào thư mục sau điểm họp lại.
* **Git workflow khuyến nghị (an toàn, không mất bài):**
  - Mỗi thành viên tạo branch riêng trên máy: Hà làm trên `feature/ha`, Nghi làm trên `feature/nghi`, An làm trên `feature/an`.
  - Khuyến khích **commit cục bộ thường xuyên** (local commit) sau khi hoàn thành từng mục nhỏ để lưu vết và tránh rủi ro mất việc nếu máy gặp sự cố.
  - Tại điểm họp lại (phút 170–200), từng người pull `main` mới nhất, merge branch cá nhân vào `main` (do Hà hỗ trợ đối soát), kiểm tra đồng bộ toàn bộ file, rồi mới thực hiện push chung lên GitHub trước hạn chót 23:59 ngày 13/11/2026.

---

## 5. Checklist "Đầu ra sau Buổi Thảo luận Chung"

Trước khi chuyển sang làm việc độc lập theo 3 file riêng, cả nhóm kiểm tra các điều kiện tiên quyết:

- [ ] Mục **§1** đã được Hà gõ hoàn chỉnh vào file `spec.md` (Lát cắt một câu + 3 việc không làm).
- [ ] Bảng **8 kịch bản rủi ro** và **2 ca đắt nhất** đã được Hà gõ khung vào `spec.md` §2 (đạt Mốc M1 lúc 45').
- [ ] Bản nháp **mức tự chủ 5 tool** và ý tưởng tách bước đã được cả 3 người thống nhất.
- [ ] Sơ đồ vị trí và các số đánh dấu **HAX [1], [2], [3], [4]** đã thống nhất giữa Hà và Nghi.
- [ ] Quy ước phân chia file và đề mục git đã được xác nhận, cam kết không ghi đè phần của nhau.
- [ ] **Mỗi thành viên mở file riêng của mình:** Hà mở `Ha-plan.md`, Nghi mở `Nghi-plan.md`, An mở `An-plan.md`. Bắt đầu tính giờ làm việc độc lập!
