# Kế hoạch cá nhân: An (Người C)
## Phụ trách: `spec.md` §4, §5.3–5.4, §7 & Chủ nhiệm Kịch bản Demo 4 Phút
### Nhóm: nhomANH · Track: T4 Thương mại điện tử · Hạn nộp: 23:59 ngày 13/11/2026

> **NGUYÊN TẮC LÀM VIỆC ĐỘC LẬP & AN TOÀN GIT:**
> - An bắt đầu làm việc ngay sau buổi thảo luận chung (khoảng phút ~70), **hoàn toàn độc lập, không phải chờ code của Hà hay câu chữ của Nghi**.
> - **Input của An:** Đã có đầy đủ trong [plan.md](file:///Users/hale/Code/AI%20in%20action%20lab/Lab%20day%205/K5-L3B-Day05-nhomANH-AI-Product-UX-Autonomy/plan.md) (bản nháp mức tự chủ 5 tool, 2 ca đắt nhất, sơ đồ layout prototype).
> - **Phạm vi sở hữu:** `spec.md` các mục **§4**, **§5.3**, **§5.4**, **§7**.
> - **Git an toàn:** Làm việc trên branch `feature/an`, commit cục bộ thường xuyên khi hoàn thành từng mục (§4, §5.3–5.4, §7) để tránh mất tiến độ; merge vào `main` tại điểm họp 170–200.
> - **Tuyệt đối không sửa:** File `prototype/index.html` (để Hà code); file ảnh screenshot (để Nghi chụp); các mục §1, §2, §3, §5.1, §5.2, §6 trong `spec.md`.

---

## 1. Mục tiêu & Các Mốc Quan Trọng

* **Mốc M2 (Phút 125):** Mục **§4** trong `spec.md` đã sẵn sàng để TA kiểm tra (5 tool đủ mức và lý do theo cost-of-error; phân tích tool khó xếp nhất; thử nghiệm 3 kịch bản; đề xuất tách bước).
* **Phút 125 – 160:** Viết xong mục **§5.3 – §5.4** (mô tả cách thể hiện mức tự chủ trên UI và các quyết định thiết kế theo sơ đồ đã chốt).
* **Phút 160 – 170:** Soạn kịch bản demo 4 phút và phương án đón đầu ca lạ cho mục **§7**.
* **Điểm họp lại (Khoảng phút 170 – 200):**
  - Cầm trịch buổi tổng duyệt: Bấm prototype của Hà và điều phối lượt nói của 3 người (4 phút).
  - Đóng vai người xem thử thách 1 ca lạ để cả nhóm phản xạ theo ma trận mức tự chủ §4.

---

## 2. Checklist Hành động Từng bước của An

### Bước 1: Viết chi tiết Mục §4 trong `spec.md` (Phút 70 – 125 · R4: 25 điểm ──► MỐC M2)

#### 4.1. Lập luận ma trận Cost-of-Error cho 5 tool
- [ ] **Tool `yeu_cau_bang_chung` — Mức Tự làm (có điều kiện):**
  - *Lý do cost-of-error:* Tin đã tới thì không thu hồi được trong tâm lý người nhận, nhưng sai sót ở đây chỉ là gây phiền toái chứ không làm mất tiền hay thay đổi tư cách pháp lý. Ngược lại, nếu bắt nhân viên sàn duyệt từng form xin ảnh thì người mua phải chờ đợi vô ích hàng giờ, làm nghẽn toàn bộ luồng tiếp nhận ban đầu.
  - *Phương án đã loại:* Loại mức "Cần người duyệt" vì chi phí thời gian chờ đợi đắt hơn chi phí gửi form xin ảnh.
- [ ] **Tool `chuyen_truong_nhom` — Mức Tự làm:**
  - *Lý do cost-of-error:* Hành động chuyển hồ sơ hoàn toàn đảo ngược được (trưởng nhóm có thể từ chối hoặc trả lại hồ sơ). Đây là "đường lui an toàn" (graceful fallback) khi AI phát hiện ca ngoài thẩm quyền hoặc mâu thuẫn phức tạp.
  - *Phương án đã loại:* Loại "Cần duyệt" vì đây chính là hành động xin con người can thiệp.
- [ ] **Tool `soan_hoan_tien` — Mức Cần người duyệt:**
  - *Ai duyệt, thấy gì:* **Nhân viên xử lý khiếu nại sàn duyệt.** Nhân viên thấy ảnh thực tế khách gửi, trích xuất mô tả lúc đặt mua (thẻ Snapshot lúc đặt trên UI — *chú thích: đây là cách nhóm quy ước đặt tên và hiển thị trên giao diện prototype để trực quan hóa yêu cầu 'đối chiếu với mô tả lúc đặt hàng', không phải trường dữ liệu có sẵn trong đề bài*), phản hồi của shop và phiếu đề xuất của AI.
  - *Quá hạn thì sao:* Giữ nguyên tiền ở trạng thái bảo lãnh tạm giữ của sàn *(chú thích: khái niệm 'bảo lãnh/tạm giữ' là đề xuất thiết kế luồng tiền an toàn của nhóm, không phải thuật ngữ có sẵn trong đề bài)*, gửi cảnh báo đỏ cho ca trực tiếp theo, tuyệt đối không tự động xuất tiền.
  - *Lý do cost-of-error:* Bảng tool ghi rõ "Khó: tiền đã về người mua". Nếu AI tự hoàn sai, người bán mất cả tiền lẫn hàng dù họ giao đúng mô tả; sàn phải bỏ tiền túi bồi thường. Một bước duyệt 30 giây của nhân viên ngăn chặn được 100% rủi ro mất tiền oan.
- [ ] **Tool `tu_choi_khieu_nai` — Mức Cần người duyệt:**
  - *Ai duyệt, thấy gì:* Nhân viên sàn duyệt sau khi xem bằng chứng shop giao đúng mô tả lúc đặt và giải trình của hai bên.
  - *Quá hạn:* Tiếp tục đóng băng đơn hàng, không tự ý giải ngân cho shop khi chưa có người thẩm định.
  - *Lý do cost-of-error:* "Từ chối cho chắc" cũng có người thua! Đóng khiếu nại là tiền giải ngân về ví người bán ("Khó: tiền đã về người bán"). Nếu từ chối sai, người mua mất tiền oan, dẫn đến khiếu nại bùng nổ truyền thông.
- [ ] **Tool `phat_shop` — Mức CẤM hoàn toàn trong luồng này:**
  - *Lý do cost-of-error:* Trừ điểm uy tín hoặc khoá shop ảnh hưởng trực tiếp đến sinh kế của cả doanh nghiệp và hàng ngàn đơn hàng khác. Thẩm quyền này thuộc về quy trình điều tra độc lập của bộ phận chuyên trách; trợ lý chat chỉ giải quyết khiếu nại một đơn cụ thể.

#### 4.2. Phân tích Tool khó xếp nhất: `soan_hoan_tien`
- [ ] Ghi lại rõ quan điểm từng thành viên trong thảo luận:
  - **Hà:** Từng đề xuất mức **"Tự làm"** cho các đơn hàng có giá trị nhỏ (vd: dưới 100k) nhằm tối ưu chỉ số giải quyết tức thì (Instant Refund), tạo trải nghiệm "wow" cho khách và giảm tải tối đa cho hàng đợi nhân viên sàn.
  - **Nghi:** Kiên quyết phản đối, yêu cầu chọn mức **"Cần người duyệt"** vì đề bài chỉ rõ "Khó: tiền đã về người mua". Nếu AI bị thao túng bởi hình ảnh chỉnh sửa hoặc lời đe dọa bóc phốt (#7), tiền chảy ra khỏi sàn là vĩnh viễn không đòi lại được, người bán mất tiền oan và sàn phá vỡ cam kết trung lập.
  - **An:** Đồng tình với Nghi chốt mức **"Cần người duyệt"**, đồng thời đưa ra giải pháp kỹ thuật dung hòa: **Tách quy trình thành 2 bước**.
- [ ] **Đề xuất kỹ thuật tách bước (Value-add cho R4):**
  - Tách quy trình thành: `de_xuat_hoan_tien` (AI tự làm: thu thập đủ ảnh, đối chiếu mô tả lúc đặt, lập phiếu tổng hợp) và `thuc_thi_hoan_tien` (Nhân viên sàn duyệt: kiểm tra nhanh 30 giây và bấm nút chuyển tiền). *(Lưu ý bắt buộc: `de_xuat_hoan_tien` và `thuc_thi_hoan_tien` là đề xuất tách bước quy trình của nhóm, KHÔNG phải tool có trong đề bài; tool gốc trong đề duy nhất là `soan_hoan_tien` với đặc tính hoàn tiền thật, "Khó: tiền đã về người mua")*.
  - Kịch bản được chặn: Chặn đứng hoàn toàn việc AI bị thao túng bởi lời đe dọa bóc phốt (#7) mà tự động xuất tiền.

#### 4.3. Kiểm chứng mức tự chủ trên 3 kịch bản (Trả lời chuẩn 3 câu hỏi Rubric R4)
- [ ] *Kịch bản 1 (Mô tả bị sửa — Ca đắt #1):*
  1. *Cái sai có bị chặn không?* Có. AI không thể tự ý gọi `tu_choi_khieu_nai` sai nguồn sự thật vì tool này ở mức Cần duyệt; đồng thời AI kích hoạt `chuyen_truong_nhom` (Tự làm) để cảnh báo sửa mô tả.
  2. *Có việc nào AI làm khi lẽ ra phải hỏi không?* Không. AI không phán quyết thay con người mà chuyển đúng thẩm quyền chuyên viên.
  3. *Người dùng bình thường có phải chờ vô ích không?* Không. Khách nhận được thẻ đối chiếu minh bạch ngay lập tức và biết hồ sơ đang được ưu tiên xử lý.
- [ ] *Kịch bản 7 (Doạ bóc phốt — Ca đắt #2):*
  1. *Cái sai có bị chặn không?* Có. AI bị khóa hoàn toàn quyền tự xuất tiền (`soan_hoan_tien` Cần duyệt), ngăn chặn 100% rủi ro mất tiền oan cho người bán.
  2. *Có việc nào AI làm khi lẽ ra phải hỏi không?* Không. AI chỉ tự gửi mẫu xin bằng chứng (`yeu_cau_bang_chung` Tự làm) và ấn định thời hạn phản hồi cho shop, không tự đưa ra kết luận.
  3. *Người dùng bình thường có phải chờ vô ích không?* Không. Cả hai bên đều nhận được quy trình minh bạch kèm đồng hồ đếm ngược thời hạn.
- [ ] *Kịch bản bình thường (Áo size L nhận size M — Tin mồi 1 #4):*
  1. *Cái sai có bị chặn không?* Có. AI không vội vàng hoàn tiền khi mới chỉ có tin nhắn chữ, tránh thất thoát khi chưa có ảnh tem áo.
  2. *Có việc nào AI làm khi lẽ ra phải hỏi không?* Không. AI không đoán mò mà gửi đúng một form yêu cầu ảnh chụp tem áo và tin nhắn xác nhận của shop.
  3. *Người dùng bình thường có phải chờ vô ích không?* Không. Vì `yeu_cau_bang_chung` ở mức Tự làm, khách nhận được hướng dẫn và form gửi ảnh ngay trong 3 giây mà không phải chờ nhân viên duyệt từng tin nhắn.

#### 4.4. Thay đổi lời hứa thương hiệu với người dùng
- [ ] Phân tích rõ sự chuyển dịch: Từ lời hứa ảo tưởng *"Bot AI tự động giải quyết và hoàn tiền tức thì sau 1 giây"* sang lời hứa thực tế và minh bạch *"Shopee hỗ trợ bạn thu thập chứng cứ và lập hồ sơ khiếu nại chuẩn xác gửi tới người bán; chuyên viên sàn sẽ đối soát công bằng và phản hồi trong thời hạn quy định (nói rõ thời hạn và còn bao lâu, không đưa ra cam kết SLA số phút/số ngày bịa ngoài đề bài)"*.

### Bước 2: Viết Mục §5.3 và §5.4 trong `spec.md` (Phút 125 – 160)
- [ ] **Mục §5.3 — Cách thể hiện mức tự chủ trên giao diện:**
  - *Tự làm:* AI tự kích hoạt thẻ đối chiếu và gửi tin nhắn trong chat ngay lập tức.
  - *Cần người duyệt:* Trên Màn hình 2, hiển thị rõ khung duyệt của Chuyên viên sàn kèm 2 nút `[Phê duyệt hoàn tiền]` và `[Yêu cầu bổ sung]`.
  - *Cấm:* Tool `phat_shop` hoàn toàn không có nút bấm trên giao diện chat của người dùng.
- [ ] **Mục §5.4 — Đủ 4 Quyết định Thiết kế (Mỗi quyết định đủ 4 ý):**
  1. *Quyết định 1: Cách hiển thị độ chắc chắn & bằng chứng đối chiếu:*
     - *Cân nhắc:* (a) Điểm số tin cậy phần trăm (Confidence Score, vd 85%, 90%); (b) Nhãn trạng thái logic và thẻ đối chiếu trích xuất văn bản/hình ảnh thực tế.
     - *Chọn:* Nhãn trạng thái logic (`[Đang đối chiếu chứng cứ]`, `[Chờ người bán đối chất]`) kết hợp thẻ đối chiếu mô tả lúc đặt (vị trí **[1] — HAX G11**).
     - *Vì sao:* Đưa ra con số % giả tạo trong tranh chấp tài chính TMĐT sẽ gây ảo tưởng tin cậy nguy hiểm; người dùng cần bằng chứng khách quan chứ không phải con số xác suất mập mờ.
     - *Loại phương án khác:* Loại thanh điểm % vì không có căn cứ xác thực và vi phạm nguyên tắc minh bạch PAIR.
  2. *Quyết định 2: Cơ chế kiểm soát mức tự chủ (Control Mechanism):*
     - *Cân nhắc:* (a) Cho AI tự hoàn tiền rồi cung cấp nút Hoàn tác sau (Undo / Post-action); (b) Kiểm soát chặn trước bằng phê duyệt của con người (Pre-action verification).
     - *Chọn:* Kiểm soát chặn trước (Pre-action verification) đối với `soan_hoan_tien` và `tu_choi_khieu_nai`.
     - *Vì sao:* Bảng tool khẳng định "Khó: tiền đã về người mua / người bán"; tiền đã giải ngân ra khỏi sàn thì việc thu hồi cực kỳ phức tạp và tốn kém, hoàn tác sau là bất khả thi.
     - *Loại phương án khác:* Loại Undo vì không áp dụng được cho giao dịch tài chính liên quan đến ví tiền bên thứ ba.
  3. *Quyết định 3: Kiến trúc giao diện 2 màn hình (Người mua + Người bán / Sàn duyệt):*
     - *Cân nhắc:* (a) Chỉ làm 1 màn hình chat duy nhất của người mua; (b) Bố cục 2 màn hình chuyển tab giữa luồng Người mua và Kênh Người bán / Bàn duyệt Sàn.
     - *Chọn:* Bố cục 2 màn hình chuyển tab (Màn 1: Người mua; Màn 2: Người bán & Sàn).
     - *Vì sao:* Giúp chứng minh trực quan tính trung lập tuyệt đối của hệ thống: Người bán thấy khiếu nại và có thời hạn đối chất; Nhân viên sàn duyệt đề xuất trước khi tiền được chuyển (thể hiện trọn vẹn vị trí **[4]**).
     - *Loại phương án khác:* Loại 1 màn hình vì cái nhìn một chiều, không thể hiện được quyền lợi của bên bị khiếu nại theo yêu cầu của Rubric T4.
  4. *Quyết định 4: Cơ chế hiển thị thời hạn phản hồi:*
     - *Cân nhắc:* (a) Text thông báo tĩnh chung chung ("Shop sẽ phản hồi sớm"); (b) Cam kết thời gian cứng cố định (vd "24 giờ" hoặc "15 ngày"); (c) Đồng hồ đếm ngược thời gian thực kèm chú thích "dữ liệu dựng giả lập".
     - *Chọn:* Đồng hồ đếm ngược minh bạch kèm dòng chú thích rõ là dữ liệu dựng giả lập (vị trí **[3] — HAX G1/G2 & Rubric 8**).
     - *Vì sao:* Giải tỏa tâm lý sốt ruột của người mua mà không bịa ra chính sách thời hạn chính thức ngoài đề bài.
     - *Loại phương án khác:* Loại text tĩnh vì người dùng không biết phải chờ bao lâu; loại cam kết giờ cứng vì đề bài không cấp số liệu chính thức.

### Bước 3: Viết Kịch bản Demo 4 Phút & Đón đầu Ca lạ (§7) (Phút 160 – 170)
- [ ] Phân bổ thời lượng chi tiết cho 4 phút demo:
  * **Phút 0:00 – 0:30 (Mở đầu — Hà):** Nêu lát cắt một câu và 3 việc không làm.
  * **Phút 0:30 – 2:00 (Ca khó nhất — Hà & Nghi):** Bấm trực tiếp trên prototype ca người bán sửa mô tả (Ca #1) hoặc ca doạ bóc phốt (Ca #7). Chuẩn bị sẵn đường tắt cho Ca #8 (người bán đúng) để chứng minh AI dám nói "chưa đủ căn cứ". Chỉ rõ thẻ đối chiếu mô tả lúc đặt (HAX G11) và nút chuyển nhân viên (HAX G10).
  * **Phút 2:00 – 3:15 (Mức tự chủ — An):** Giải thích ma trận cost-of-error cho 5 tool, làm rõ vì sao `soan_hoan_tien` cần duyệt và giá trị của đề xuất tách bước.
  * **Phút 3:15 – 4:00 (Ứng biến ca lạ — Cả nhóm do An điều phối):** Sẵn sàng nhận câu hỏi/ca lạ từ TA và phân tích theo ma trận mức tự chủ.
- [ ] **Khung mẫu Phản ứng Ca lạ theo Rubric R7 & `spec.md` §7:**
  - *Bước 1 (Nhận diện):* Hành vi người dùng là gì? Thuộc lớp rủi ro nào?
  - *Bước 2 (Tra cứu ma trận §4):* Hành động tương ứng với tool nào trong 5 tool thật? Mức tự chủ tương ứng là Tự làm, Cần duyệt hay Cấm?
  - *Bước 3 (Prototype phản ứng):* AI nói gì nguyên văn? Giao diện hiển thị trạng thái gì? Ai được thông báo?
  - *Bước 4 (Đổi ý sau ca lạ):* Nhóm có đổi ý về mức tự chủ sau ca lạ này không? Vì sao giữ nguyên hoặc vì sao thay đổi?
- [ ] **Luyện tập trước với 2 Ca lạ Giả định:**
  - *Ca lạ 1 (Đòi bồi thường thêm voucher):* Khách nhận áo nhầm size, đòi sàn đền thêm voucher 500k vì làm lỡ đám cưới.
    * *Phản ứng:* AI giải thích luồng chat chỉ hỗ trợ Trả hàng/Hoàn tiền cho giá trị đơn hàng; yêu cầu bồi thường voucher thuộc thẩm quyền CSKH sàn → AI gọi `chuyen_truong_nhom` (Tự làm), không hứa hẹn bồi thường voucher.
    * *Có đổi ý không:* Không đổi ý; mức tự chủ phân cấp giữa giải quyết đơn và thẩm quyền CSKH đã chặn đứng rủi ro chi tiền bừa bãi.
  - *Ca lạ 2 (Hàng vỡ do vận chuyển, hai bên đổ lỗi nhau):* Người mua chụp ảnh nồi vỡ; người bán đưa video đóng gói nguyên vẹn, đổ lỗi cho đơn vị vận chuyển làm rơi vỡ.
    * *Phản ứng:* AI nhận diện mâu thuẫn bên thứ 3 (đơn vị vận chuyển); kích hoạt `yeu_cau_bang_chung` (Tự làm) xin ảnh phiếu gửi/biên bản đồng kiểm, và chuyển hồ sơ sang bộ phận điều tra vận chuyển qua `chuyen_truong_nhom` (Tự làm); tuyệt đối không gọi `soan_hoan_tien` hay `tu_choi_khieu_nai` khi chưa có kết luận.
    * *Có đổi ý không:* Không đổi ý; việc giữ `soan_hoan_tien` ở mức Cần duyệt bảo vệ người bán không bị mất tiền khi lỗi thuộc về nhà vận chuyển.

### Bước 4: Điều phối tại Điểm họp lại duy nhất (Phút 170 – 200)
- [ ] Cùng Hà và Nghi chạy thử kịch bản demo 4 phút với đồng hồ bấm giờ thực tế.
- [ ] Đặt thử các câu hỏi hóc búa và ca lạ giả định cho Hà và Nghi để luyện phản xạ.
- [ ] Hoàn thiện phần khung nhận định ca lạ trong mục §7 của `spec.md`.

---

## 3. Câu hỏi Sát hạch Demo mà An phải trả lời trôi chảy

> [!CAUTION]
> **Quy tắc Vibe-coding:** Nếu giảng viên hoặc TA hỏi về phần việc có tên An mà An không giải thích được lý do thiết kế, phần đó sẽ bị **0 điểm ở R7**.

An cần nắm chắc câu trả lời cho các câu hỏi sau:
1. *"Tại sao tool `soan_hoan_tien` không được để ở mức Tự làm dù tên nó có chữ 'soạn'?"*
   - Trả lời: Vì bảng tool quy định rõ chức năng thực tế của nó là 'Hoàn tiền cho người mua' và khả năng đảo ngược là 'Khó: tiền đã về người mua'. Nếu để AI tự làm, sai sót do bị thao túng bởi lời đe dọa hoặc ảnh giả mạo sẽ khiến tiền thoát khỏi tài khoản sàn ngay lập tức và không thể thu hồi được.
2. *"Nếu chuyên viên sàn không duyệt kịp yêu cầu khiếu nại thì quá hạn xử lý thế nào?"*
   - Trả lời: Tiền vẫn được giữ an toàn ở trạng thái bảo lãnh/tạm giữ của sàn (đề xuất thiết kế luồng an toàn của nhóm); hệ thống tự động gia hạn thời gian và gửi cảnh báo ưu tiên cho ca trực tiếp theo. Tuyệt đối không tự động hoàn hoặc tự động hủy khi hết giờ.
3. *"Cái giá khi AI gọi sai `tu_choi_khieu_nai` là gì?"*
   - Trả lời: 'Từ chối cho chắc' cũng có người thua. Tiền đã giải ngân cho người bán ("tiền đã về người bán"), người mua bị mất tiền oan và ôm sản phẩm lỗi, phá vỡ tính trung lập của sàn.
4. *"Đề xuất tách bước của nhóm mang lại giá trị gì cho kiến trúc sản phẩm?"*
   - Trả lời: Tách quy trình `soan_hoan_tien` (tool gốc của đề bài) thành 2 bước do nhóm đề xuất: `de_xuat_hoan_tien` (AI tự làm hồ sơ) và `thuc_thi_hoan_tien` (Con người duyệt chuyển tiền) vừa giải phóng 80% thời gian tổng hợp hồ sơ của nhân viên, vừa chặn đứng 100% rủi ro mất tiền tự động khi tool gốc có cost-of-error quá đắt (tiền về người mua không thu hồi được).
