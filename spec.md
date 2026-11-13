# Dàn ý bài nộp *(spec.md — nộp trước 23:59 ngày lab của lớp)*

> Copy dàn ý này vào `spec.md` của nhóm. Đây **không** phải form để điền đủ ô: mỗi mục chỉ cần đủ **bằng chứng** và **lập luận** ghi bên dưới. Viết ngắn, gạch đầu dòng là được. Hướng dẫn từng chặng: `02-guide.md`. Cách chấm: `04-rubric.md`.
>
> **Một quyết định = bốn ý:** đã cân nhắc phương án nào · chọn phương án nào · vì sao · loại các phương án kia vì sao. Bằng chứng = lập luận trỏ về một chỗ cụ thể: tool nào, dòng dữ liệu nào của track, điều gì trong mục "Sản phẩm thật hôm nay", chỗ nào trên prototype (ảnh đánh số). Không chạy agent.

# Bài nộp LAB5 — T4 · Nhóm nhomANH

Lớp: L3B · Track: T4 · Nhóm: nhomANH · Hạn nộp: 23:59 ngày 13/11/2026 (Asia/Saigon)

> **Lưu ý:** Mã học viên còn thiếu — điền trước khi nộp. Cả nhóm chốt §1 trong buổi thảo luận chung (`plan.md`); sau đó mỗi người làm task riêng theo file của mình.

| Họ và Tên | Mã Học Viên | Việc đã làm |
|---|---|---|
| Hà | (điền mã) | S2, S5.1 & prototype (main) — xem `Ha-plan.md` |
| Nghi | (điền mã) | S3, S5.2, S6 — xem `Nghi-plan.md` |
| An | (điền mã) | S4, S5.3–5.4, S7 — xem `An-plan.md` |

## §1. Lát cắt & phạm vi
- Lát cắt (chép từ track).
- 3 việc tính năng KHÔNG làm, mỗi việc một câu vì sao.

## §2. Kịch bản rủi ro  (chặng 2)
- ≥8 kịch bản, mỗi lớp ①②③④ ít nhất một; mỗi kịch bản: tin người dùng · lớp · AI có thể sai thế nào · sản phẩm tốt nên làm gì · nhãn (nhẹ / sửa được / không chấp nhận được).
- Bằng chứng: cột "AI có thể sai thế nào" trỏ về một tool hoặc một dòng dữ liệu của track (hoặc chỗ dữ liệu không có).
- Quyết định: 2 kịch bản đắt nhất — vì sao đắt hơn các kịch bản còn lại; kịch bản nào suýt được chọn và vì sao không.

## §3. Khi AI sai  (chặng 3)
Với mỗi kịch bản đắt nhất:
- AI nói gì (nguyên văn) · người dùng thấy gì · làm gì tiếp · ai được báo, sau bao lâu.
- Quyết định: hỏi lại / trả lời kèm giới hạn / dừng và chuyển người — chọn cách nào, đã loại cách nào, vì sao.
- Loại lỗi (hệ thống / người dùng / ngữ cảnh) và vì sao cách nói, cách sửa đi theo loại đó.
- 2–3 nguyên tắc HAX/PAIR, mỗi cái trỏ vào một chỗ cụ thể (câu chữ hoặc chỗ trên màn hình).
- Lỗi nào sửa câu chữ không cứu được (nếu có), và thiết kế cứu nó thế nào.

## §4. Mức tự chủ  (chặng 4)

Nguồn sự thật: đúng 5 tool ghi trong track T4 (`plan.md` §3.2). Track không có tool chỉ-đọc; đối chiếu mô tả lúc đặt là suy luận của AI. `de_xuat_hoan_tien` và `thuc_thi_hoan_tien` ở mục 4.2 là tách bước do nhóm đề xuất, không phải tool trong đề. Tool gốc duy nhất liên quan tiền về người mua là `soan_hoan_tien`.

### 4.1. Mức từng tool

**`yeu_cau_bang_chung` — Tự làm, có điều kiện** (một form có checklist, không gửi lại cùng một mục đã xin).
- Sai thì ai chịu: người nhận bức xúc ("tôi gửi rồi sao cứ hỏi lại"), người bán bị spam, ca bị kéo dài. Chưa mất tiền, chưa đổi tư cách pháp lý. Đảo lại: không — tin đã tới.
- Chờ người duyệt thì mất gì: người mua chờ hàng giờ chỉ để nhận mẫu xin ảnh; cả luồng tiếp nhận nghẽn.
- Đã cân nhắc mức Cần người duyệt. Loại vì chi phí chờ đắt hơn chi phí gửi nhầm một form xin bằng chứng.

**`chuyen_truong_nhom` — Tự làm.**
- Sai thì ai chịu: hàng đợi trưởng nhóm tắc, thời gian chờ tăng. Không mất tiền ngay. Đảo lại: được — trưởng nhóm từ chối hoặc trả hồ sơ. Đây là đường lui khi ca vượt thẩm quyền hoặc mâu thuẫn.
- Chờ người duyệt thì mất gì: hành động này chính là xin người can thiệp; bắt duyệt trước khi chuyển là chặn đường lui.
- Đã cân nhắc mức Cần người duyệt. Loại vì lý do trên.

**`soan_hoan_tien` — Cần người duyệt.**
- Theo đề, tool này hoàn tiền thật cho người mua, không phải chỉ soạn nháp. Đảo lại: Khó — tiền đã về người mua.
- Ai duyệt: nhân viên xử lý khiếu nại sàn.
- Người duyệt thấy gì: ảnh khách gửi, thẻ đối chiếu mô tả lúc đặt (trên UI gọi là thẻ Snapshot lúc đặt — cách nhóm đặt tên để hiện yêu cầu "đối chiếu mô tả lúc đặt", không phải trường có sẵn trong đề), phản hồi của shop, phiếu đề xuất của AI.
- Quá hạn không ai duyệt: giữ tiền ở trạng thái tạm giữ của sàn (luồng tiền do nhóm đề xuất, không phải thuật ngữ trong đề); cảnh báo cho ca trực tiếp theo. Không tự xuất tiền, không tự huỷ.
- Sai thì ai chịu: người bán mất tiền và hàng dù giao đúng; sàn vỡ cam kết trung lập. Trỏ kịch bản §2 #7.
- Chờ một lượt duyệt thì mất gì: khách không được hoàn tức thì. Rẻ hơn một khoản không thu hồi được.
- Phương án Tự làm (kể cả đơn giá trị nhỏ) đã bị loại — xem 4.2.

**`tu_choi_khieu_nai` — Cần người duyệt.**
- Ai duyệt: nhân viên sàn, sau khi xem bằng chứng shop giao đúng mô tả lúc đặt và giải trình của hai bên.
- Quá hạn: đơn tiếp tục đóng băng; không tự giải ngân cho shop.
- Sai thì ai chịu: người mua mất tiền và giữ hàng sai. "Từ chối cho chắc" cũng có người thua. Đảo lại: Khó — tiền đã về người bán. Trỏ kịch bản §2 #1.
- Chờ người thì mất gì: shop chưa nhận tiền sớm. Rẻ hơn giải ngân oan.
- Đã cân nhắc mức Tự làm khi bằng chứng shop "khớp mô tả". Loại vì AI có thể đang nhìn mô tả hiện tại, không phải mô tả lúc đặt (ca #1); một bước duyệt chặn được.

**`phat_shop` — Cấm trong luồng chat này.**
- Sai thì ai chịu: trừ điểm hoặc khoá shop đụng sinh kế cả gian hàng và các đơn khác, không chỉ một khiếu nại. Đảo lại: Khó, ảnh hưởng cả shop.
- Một bước xác nhận của nhân viên chat không đủ: phạt thuộc quy trình điều tra riêng. Trỏ kịch bản §2 #6.
- Người dùng đi đâu: AI không hứa phạt; gọi `chuyen_truong_nhom` (Tự làm) sang bộ phận chuyên trách.
- Đã cân nhắc mức Cần người duyệt ngay trong chat. Loại vì người duyệt ở luồng này không có thẩm quyền điều tra hàng giả.

### 4.2. Tool khó xếp nhất: `soan_hoan_tien`

Mức nào cũng có giá, trỏ về §2:
- **Hà — Tự làm** với đơn nhỏ (ví dụ dưới một ngưỡng thấp), để hoàn tức thì và giảm hàng đợi. Cái giá: ca §2 #7, lời doạ bóc phốt hoặc ảnh chỉnh sửa làm tiền về người mua ngay, không đòi lại; người bán mất hàng dù chưa được đối chất.
- **Nghi — Cần người duyệt.** Đề ghi "Khó: tiền đã về người mua". Cái giá phía bên kia: ca bình thường §2 #4 (áo size L nhận size M, shop đã nhận gửi nhầm) phải chờ nhân viên, mất trải nghiệm giải quyết ngay.
- **An — cùng Nghi, và tách bước** để giảm cái giá của việc chờ: AI làm phần hồ sơ, người chỉ bấm phần tiền.

**Chốt: Cần người duyệt.** Trung lập và khoản không thu hồi nặng hơn chỉ số hoàn tức thì.

Tách bước (luật thêm, không phải tool trong đề):
- `de_xuat_hoan_tien`: AI tự làm — gom ảnh, đối chiếu mô tả lúc đặt, lập phiếu. Không đụng tiền.
- `thuc_thi_hoan_tien`: nhân viên sàn duyệt rồi bấm chuyển tiền. Bước này mới là `soan_hoan_tien` của đề.
- Ca được chặn: §2 #7 — AI không xuất tiền chỉ vì bị doạ.

### 4.3. Thử mức đã đặt trên 3 kịch bản

**Đắt nhất #1 — §2 kịch bản #1: người bán sửa mô tả sau khi bán** (tin mồi nồi 6 lít; dữ liệu dựng của nhóm: lúc đặt "6L", mô tả hiện tại "phủ bì 6L, lòng nồi 5L").
- Cái sai có bị chặn không? Có. `tu_choi_khieu_nai` không tự chạy khi AI chỉ thấy mô tả hiện tại. AI gọi `chuyen_truong_nhom` (Tự làm) kèm hai phiên bản mô tả.
- Còn việc nào làm khi lẽ ra phải hỏi? Không. AI không chốt bên nào thắng.
- Người dùng bình thường có phải chờ vô ích không? Không. Thẻ đối chiếu hiện ngay; hồ sơ được chuyển, không chờ duyệt từng câu hỏi.

**Đắt nhất #2 — §2 kịch bản #7: doạ bóc phốt nếu không hoàn trong 2 tiếng.**
- Cái sai có bị chặn không? Có. `soan_hoan_tien` khoá đến khi nhân viên duyệt. Lời doạ không phải căn cứ.
- Còn việc nào làm khi lẽ ra phải hỏi? Không. AI chỉ gọi `yeu_cau_bang_chung` (Tự làm) cho hai bên và ấn định hạn shop đối chất.
- Người dùng bình thường có phải chờ vô ích không? Không. Hai bên thấy quy trình và thời hạn còn lại (đồng hồ trên prototype là dữ liệu dựng).

**Bình thường — §2 kịch bản #4: áo size L nhận size M, shop nhận gửi nhầm** (tin mồi 1).
- Cái sai có bị chặn không? Có. Mới có tin chữ, chưa có ảnh tem, thì không gọi `soan_hoan_tien`.
- Còn việc nào làm khi lẽ ra phải hỏi? Không. Đúng một form xin ảnh tem áo và ảnh tin shop nhận lỗi.
- Người dùng bình thường có phải chờ vô ích không? Không. `yeu_cau_bang_chung` ở mức Tự làm, form tới trong chat, không chờ nhân viên duyệt từng tin.

### 4.4. Một mức tự chủ đã đổi lời hứa

Đặt `soan_hoan_tien` và `tu_choi_khieu_nai` ở Cần người duyệt thì lời hứa với người mua đổi:
- Nếu để Tự làm: "Bot tự giải quyết và hoàn tiền ngay."
- Mức đã chốt: "Trợ lý giúp thu thập chứng cứ và lập hồ sơ gửi người bán; chuyên viên sàn đối soát. Hệ thống nói rõ thời hạn yêu cầu trả hàng và còn bao lâu."

Không cam kết số phút hay số ngày chính thức. Đề không cấp số ngày dựng; 15 ngày trên trang trợ giúp Shopee thật là chính sách khác bài (`plan.md` §3.1).

## §5. Prototype  (chặng 5)
- Link hoặc file · công cụ · phần nào mock · có lời gọi AI thật không.
- 1–2 ảnh có đánh số; mỗi số: thể hiện gì · nguyên tắc HAX/PAIR nào · mức tự chủ nào.

### §5.3. Mức tự chủ trông thế nào trên màn hình

Sơ đồ đã chốt (`plan.md` §4.4): Màn 1 là chat người mua; Màn 2 là người bán và bàn duyệt của sàn. Số [1]–[4] là chỗ Nghi chụp và chú thích ở §5.2.

- **Tự làm — `yeu_cau_bang_chung`:** AI gửi form checklist ngay trong chat Màn 1, không có hộp chờ duyệt. Hoàn tác: không có, vì tin đã tới. Giảm hại bằng điều kiện ở §4.1 (một form, không hỏi lại mục đã gửi).
- **Tự làm — `chuyen_truong_nhom`:** nút "Gặp nhân viên hỗ trợ" ở **[2]**. Hoàn tác nằm ở phía người: trưởng nhóm trả hồ sơ, trạng thái chat đổi lại, không phải nút Undo của khách. Ca lạ không thuộc luồng trả hàng/hoàn tiền cũng đi nút này.
- **Cần người duyệt — `soan_hoan_tien` và `tu_choi_khieu_nai`:** không có nút xuất tiền hay đóng khiếu nại trên chat người mua. Trên Màn 2, vị trí **[4]**, nhân viên thấy ảnh, thẻ Snapshot lúc đặt, phản hồi shop và phiếu AI, rồi bấm `[Phê duyệt hoàn tiền]` hoặc `[Từ chối khiếu nại]` hoặc `[Yêu cầu bổ sung]`. Quá hạn: tiền giữ tạm giữ, không tự bấm hộ (§4.1).
- **Cấm — `phat_shop`:** không có nút trừ điểm hay khoá shop trên cả hai màn. Khách đòi khoá shop thì AI nói luồng này chỉ xử lý trả hàng/hoàn tiền và đưa đường `chuyen_truong_nhom` (**[2]**).

### §5.4. Bốn quyết định thiết kế

**1. Hiện độ chắc bằng nhãn trạng thái và thẻ đối chiếu, không bằng điểm phần trăm.**
- Đã cân nhắc: (a) điểm tin cậy kiểu 85%, 90%; (b) nhãn trạng thái kèm thẻ trích mô tả lúc đặt và ảnh khách gửi.
- Chọn: (b). Nhãn ví dụ `[Đang đối chiếu chứng cứ]`, `[Chờ người bán đối chất]`, cộng thẻ Snapshot lúc đặt ở **[1]** (HAX G11 — giải thích vì sao).
- Vì sao: tranh chấp tiền cần bằng chứng hai bên đọc được. Phần trăm không có căn cứ trong dữ liệu track và dễ tạo cảm giác AI đã chắc.
- Loại (a): không truy được nguồn số, trái minh bạch PAIR.

**2. Chặn trước khi đụng tiền, không hoàn tác sau.**
- Đã cân nhắc: (a) AI tự gọi `soan_hoan_tien` rồi đưa nút Hoàn tác; (b) nhân viên xác nhận trước khi tiền chuyển.
- Chọn: (b) cho cả `soan_hoan_tien` và `tu_choi_khieu_nai`. Trên màn hình là khung **[4]**, chưa bấm thì tiền chưa đi.
- Vì sao: bảng tool ghi "Khó: tiền đã về người mua" và "Khó: tiền đã về người bán". Thu hồi ví bên thứ ba không phải Undo.
- Loại (a): hoàn tác sau không áp được cho khoản đã giải ngân.

**3. Hai màn hình (người mua / người bán và sàn), không một khung chat.**
- Đã cân nhắc: (a) chỉ chat người mua; (b) hai tab — Màn 1 người mua, Màn 2 người bán và bàn duyệt.
- Chọn: (b). Màn 2 hiện thời hạn đối chất của shop và khung duyệt **[4]**.
- Vì sao: hoàn sai thì người bán thua, từ chối sai thì người mua thua. Một chiều không cho người bán được nghe và không cho thấy ai bấm tiền.
- Loại (a): không hiện được quyền đối chất (rubric riêng T4, ý 3) và mức Cần duyệt.

**4. Thời hạn là đồng hồ đếm ngược có chú thích dữ liệu dựng, không phải SLA bịa.**
- Đã cân nhắc: (a) câu tĩnh "Shop sẽ phản hồi sớm"; (b) cam kết cứng kiểu "24 giờ" hoặc "15 ngày"; (c) đồng hồ còn lại kèm dòng "dữ liệu dựng giả lập".
- Chọn: (c), vị trí **[3]** (HAX G1/G2 và rubric T4 ý 8).
- Vì sao: người mua biết còn chờ bao lâu. Đề chỉ yêu cầu nói rõ thời hạn và còn bao lâu, không cấp số ngày dựng.
- Loại (a): không biết phải chờ đến khi nào. Loại (b): 15 ngày là trang trợ giúp thật, đề ghi là chính sách khác bài; ghi thành cam kết của prototype là bịa.

## §6. Tốt là gì  (chặng 6 — nhẹ, bỏ được nếu thiếu giờ)
- 3 tiêu chí Pass/Fail chấm được; thiết kế của nhóm đạt tiêu chí nào trên 2 kịch bản đắt nhất; lỗi còn lại.

## §7. Demo

Ca lạ thật do TA hoặc giảng viên đưa tại chỗ. Mục này là kịch bản 4 phút, đường prototype đi khi gặp ca chưa chuẩn bị, và hai ca luyện sẵn. Sau demo, điền ca đã nhận vào dòng trống cuối mục.

### 7.1. Bốn phút, ai nói gì

Bấm trên `prototype/index.html`. Ca chính: §2 #1 (mô tả bị sửa). Đường tắt sẵn: §2 #8 (người bán đúng) và §2 #7 (doạ bóc phốt).

- **0:00–0:30 — Hà.** Một câu lát cắt §1, rồi ba việc không làm.
- **0:30–2:00 — Hà bấm, Nghi nói câu trên màn hình.** Ca #1: thẻ đối chiếu mô tả lúc đặt **[1]** (HAX G11), nút gặp nhân viên **[2]** (HAX G10). Nếu người xem hỏi nhánh người bán đúng, bấm ca #8: AI nói "Chưa đủ căn cứ", không gọi `soan_hoan_tien`.
- **2:00–3:15 — An.** Ma trận §4: vì sao `soan_hoan_tien` là Cần duyệt dù tên có chữ "soạn" (đề ghi hoàn tiền thật, "Khó: tiền đã về người mua"); tách `de_xuat_hoan_tien` / `thuc_thi_hoan_tien`; quá hạn thì giữ tạm giữ, không tự hoàn và không tự huỷ.
- **3:15–4:00 — An nhận ca lạ, cả nhóm trả lời theo 7.2.**

### 7.2. Ca lạ — bốn bước, bám mức §4

1. Hành vi là gì, thuộc lớp nào trong §2 (nguồn sự thật / thiếu thông tin / ngoài thẩm quyền / đặc thù domain)?
2. Đụng tool nào trong 5 tool thật, mức đó là Tự làm, Cần duyệt hay Cấm?
3. Prototype làm gì: AI nói gì, màn hình hiện trạng thái nào, ai được báo. Không khớp luồng trả hàng/hoàn tiền thì không gọi `soan_hoan_tien`, `tu_choi_khieu_nai`, `phat_shop`; hỏi một câu hoặc `chuyen_truong_nhom` qua **[2]**.
4. Có đổi mức tự chủ không, vì sao giữ hoặc đổi.

**Luyện 1 — đòi thêm voucher 500k vì lỡ đám cưới** (áo nhận nhầm size).
- Ngoài phạm vi một đơn trả hàng/hoàn tiền. AI không hứa voucher. Gọi `chuyen_truong_nhom` (Tự làm) sang CSKH sàn.
- Không đổi ý. Tiền ngoài giá trị đơn không được nút Tự làm.

**Luyện 2 — nồi vỡ, hai bên đổ cho đơn vị vận chuyển** (ảnh nồi vỡ; video shop đóng nguyên).
- Mâu thuẫn có bên thứ ba. AI gọi `yeu_cau_bang_chung` (Tự làm) xin phiếu gửi hoặc biên bản đồng kiểm, rồi `chuyen_truong_nhom` (Tự làm). Không gọi `soan_hoan_tien` hay `tu_choi_khieu_nai` khi chưa có kết luận.
- Không đổi ý. Giữ `soan_hoan_tien` ở Cần duyệt để người bán không mất tiền khi lỗi thuộc nhà vận chuyển.

### 7.3. Ca lạ nhận được lúc demo

- Ca TA/giảng viên đưa: *(điền sau demo)*
- Prototype đã làm gì:
- Nhóm có đổi ý mức nào trong §4 không:
