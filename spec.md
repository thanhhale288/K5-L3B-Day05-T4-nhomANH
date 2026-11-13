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
| Nghi | (điền mã) | §3 Khi AI sai · §5.2 ảnh đánh số · §6 · `prototype/ai-copy.md` |
| An | (điền mã) | S4, S5.3–5.4, S7 — xem `An-plan.md` |

## §1. Lát cắt & phạm vi
- Lát cắt (chép từ track).
- 3 việc tính năng KHÔNG làm, mỗi việc một câu vì sao.

## §2. Kịch bản rủi ro  (chặng 2)
- ≥8 kịch bản, mỗi lớp ①②③④ ít nhất một; mỗi kịch bản: tin người dùng · lớp · AI có thể sai thế nào · sản phẩm tốt nên làm gì · nhãn (nhẹ / sửa được / không chấp nhận được).
- Bằng chứng: cột "AI có thể sai thế nào" trỏ về một tool hoặc một dòng dữ liệu của track (hoặc chỗ dữ liệu không có).
- Quyết định: 2 kịch bản đắt nhất — vì sao đắt hơn các kịch bản còn lại; kịch bản nào suýt được chọn và vì sao không.

## §3. Khi AI sai  (chặng 3) · *Nghi*

Hai kịch bản đắt nhất (chốt ở `plan.md` / §2): **Ca 1 = kịch bản #1** (shop sửa mô tả) · **Ca 2 = kịch bản #7** (doạ bóc phốt).

### 3.1 Ca đắt #1 — Người bán sửa mô tả sau khi bán (Lớp ①)

**Tin người dùng (dữ liệu dựng):**  
*"Nồi chiên ghi 6 lít mà mình đo lòng nồi chỉ được 5 lít. Không đúng mô tả."*  
*(Bối cảnh dựng: lúc đặt ghi “dung tích nồi 6L”; sau bán shop sửa thành “thể tích phủ bì 6L, lòng nồi 5L”.)*

**AI nói (nguyên văn):**  
> "Shopee đã tiếp nhận khiếu nại của bạn về sản phẩm Nồi chiên. Qua đối chiếu với **nội dung mô tả sản phẩm tại thời điểm bạn đặt mua**, hệ thống nhận thấy thông số dung tích có sự khác biệt so với mô tả hiện tại của Shop. Để đảm bảo quyền lợi công bằng cho cả hai bên, Shopee đã chuyển hồ sơ này tới Chuyên viên khiếu nại xử lý ưu tiên. Bạn vui lòng giữ nguyên hiện trạng sản phẩm và theo dõi tiến trình trong mục này. Mình **không tự hoàn tiền và không tự từ chối khiếu nại** ở bước này."

**Người dùng thấy gì:**  
- Thẻ đối chiếu **[1]**: “Mô tả lúc đặt: dung tích nồi 6L” vs “Mô tả hiện tại: thể tích phủ bì 6L, lòng nồi 5L” (UI gọi là thẻ Snapshot lúc đặt — quy ước hiển thị của nhóm, không phải trường có sẵn trong track).  
- Dòng trạng thái: `[Đã chuyển Chuyên viên xử lý ưu tiên]`.  
- Nút **[2]** `[Gặp nhân viên hỗ trợ]` / `[Xem chi tiết hồ sơ]`.  
- Huy hiệu AI **[3]** — không có nút “Hoàn ngay” / “Từ chối khiếu nại”.

**Làm gì tiếp:** Theo dõi hồ sơ; bổ sung ảnh đo lòng nồi nếu muốn; bấm gặp nhân viên.  
**Nếu không làm gì:** Hồ sơ vẫn ở trạng thái đã chuyển chuyên viên — **không** tự `soan_hoan_tien` / `tu_choi_khieu_nai`.

**Ai được báo, sau bao lâu:** Trưởng nhóm / chuyên viên nhận ngay qua `chuyen_truong_nhom`, kèm cờ “Mô tả sản phẩm có thể đã đổi sau khi đặt”. Người bán được báo có khiếu nại đang đối soát (không bị đóng đơn một phía).

**Quyết định UX (đủ 4 ý):**  
- *Cân nhắc:* (a) hỏi lại một câu · (b) trả lời kèm giới hạn rồi để buyer tự gửi yêu cầu · (c) dừng và chuyển chuyên viên (`chuyen_truong_nhom`).  
- *Chọn:* **(c) chuyển chuyên viên**, đồng thời hiện thẻ đối chiếu hai phiên bản mô tả.  
- *Vì sao:* Mâu thuẫn **nguồn sự thật** (mô tả lúc đặt vs hiện tại) — AI không có thẩm quyền kết luận shop gian lận hay tự chốt tiền; `tu_choi_khieu_nai` / `soan_hoan_tien` đảo khó.  
- *Loại:* (a) hỏi lại — khách đã nêu đủ lệch số; hỏi thêm không tạo căn cứ pháp lý. (b) chỉ trả lời kèm giới hạn — không chặn được nếu AI (hoặc bước sau) vẫn neo mô tả hiện tại để từ chối.

**Loại lỗi:** **Ngữ cảnh (context error)** — hệ thống “so khớp” có thể chạy đúng thuật toán nhưng neo **sai mốc thời gian** của mô tả (hiện tại thay vì lúc đặt). Cách nói: thừa nhận đã thấy lệch hai bản, không đổ lỗi buyer. Cách sửa: **thiết kế bắt buộc hiện Snapshot lúc đặt + chuyển người**, không chỉ đổi wording.

### 3.2 Ca đắt #2 — Khiếu nại kèm doạ bóc phốt (Lớp ④)

**Tin người dùng:**  
*"Áo nhận được màu khác xa hình. Trong 2 tiếng không hoàn tiền thì tôi đăng bài bóc phốt lên TikTok 500k view tẩy chay Shopee!"*

**AI nói (nguyên văn):**  
> "Shopee rất thấu hiểu sự sốt ruột của bạn. Tuy nhiên, để đảm bảo tính công bằng theo quy chế sàn, mọi yêu cầu Trả hàng/Hoàn tiền cần đối soát chứng cứ khách quan và dành thời hạn hợp lệ để Người bán phản hồi. Shopee đã ghi nhận khiếu nại và ấn định thời hạn phản hồi cho Người bán (thời gian còn lại hiển thị bên dưới). **Lời cảnh báo công khai không phải căn cứ để hoàn tiền ngay.** Bạn có thể bổ sung ảnh/video lệch màu so với mô tả lúc đặt; sau thời hạn, chuyên viên sẽ đối soát theo chứng cứ — không theo áp lực truyền thông."

**Người dùng thấy gì:**  
- Đồng hồ / dòng thời hạn phản hồi shop **[3]** (số giờ là dữ liệu dựng giả lập UI — track không cấp số ngày/giờ chính thức).  
- Không có nút hoàn tức thì; có `[Gửi thêm bằng chứng]`, **[2]** `[Gặp nhân viên hỗ trợ]`.  
- Thanh tiến trình: Đã nhận khiếu nại → Đang chờ shop phản hồi.

**Làm gì tiếp:** Bổ sung chứng cứ; theo dõi hạn; hoặc gặp nhân viên nếu cần.  
**Nếu không làm gì:** Hết hạn phản hồi shop → hồ sơ lên chuyên viên đối soát; **không** auto `soan_hoan_tien` vì im lặng hay vì doạ.

**Ai được báo:** Người bán nhận khiếu nại **ngay** + hạn phản hồi + nút gửi bằng chứng đối chất (Màn 2 / **[4]**). Nhân viên sàn có phiếu theo dõi; chỉ khi đủ hồ sơ mới thấy đề xuất duyệt hoàn (nếu có).

**Quyết định UX (đủ 4 ý):**  
- *Cân nhắc:* (a) hỏi lại · (b) trả lời kèm giới hạn + `yeu_cau_bang_chung` hai phía + thời hạn shop · (c) hoàn ngay để xoa dịu · (d) chuyển trưởng nhóm ngay.  
- *Chọn:* **(b) trả lời kèm giới hạn và minh bạch quy trình.**  
- *Vì sao:* Doạ ≠ căn cứ (Rubric T4 mục 4). Trung lập sàn đòi shop được nghe trước khi chốt tiền; `soan_hoan_tien` đảo khó.  
- *Loại:* (c) hoàn ngay — moral hazard, seller mất tiền oan. (d) chuyển trưởng nhóm ngay — shop chưa hết hạn đối chất, quá tải hàng chờ. (a) hỏi lại khi khách đang kích động — dễ leo thang, không thêm bằng chứng khách quan.

**Loại lỗi nếu AI hoàn vì doạ:** **Ngữ cảnh** — mô hình/phản xạ “xoa dịu khủng hoảng” áp sai bối cảnh (sentiment ≠ evidence hàng đúng/sai mô tả). Cách nói: bình tĩnh, không lên lớp; cách sửa: rule + UI chặn hoàn theo doạ (xem mục dưới).

### 3.3 Lỗi sửa câu chữ không cứu được

Ở Ca 2 (#7): dù prompt dặn “đừng hoàn vì doạ”, nếu `soan_hoan_tien` vẫn **tự làm**, model vẫn có thể nhượng bộ trước đe dọa cực đoan → tiền về buyer, khó thu hồi.  
**Thiết kế cứu:** khóa quyền tự động của `soan_hoan_tien` ở tầng hệ thống → mức **Cần người duyệt**. Nhóm đề xuất tách bước quy trình (không phải tool trong đề): AI chỉ `de_xuat_hoan_tien` (lập phiếu); nhân viên mới `thuc_thi_hoan_tien`. Tool gốc track vẫn chỉ có `soan_hoan_tien`.

### 3.4 Nguyên tắc HAX/PAIR → chỗ cụ thể trên prototype

| Nguyên tắc | Chỗ trên UI (ảnh đánh số §5.2) |
|---|---|
| **G11** Make clear why | **[1]** Thẻ đối chiếu mô tả lúc đặt vs mô tả hiện tại / ảnh thực tế |
| **G10** Scope when in doubt | **[2]** Không tự phán tiền; nút `chuyen_truong_nhom` / Gặp nhân viên |
| **G1/G2** + PAIR Trust | **[3]** Huy hiệu Trợ lý AI + thời hạn phản hồi còn lại (minh bạch năng lực & tiến trình) |

---

## §4. Mức tự chủ  (chặng 4) · *An — xem An-plan.md*
*(Nghi không sửa mục này.)*

Với mỗi tool:
- Mức của nhóm (tự làm / cần người duyệt / cấm). Nếu cần người duyệt: ai duyệt · người duyệt thấy gì · quá hạn thì sao.
- Lý do theo cost-of-error: sai thì ai chịu gì · đảo lại được không · chờ người thì mất gì.
- Phương án đã cân nhắc và vì sao loại.
Thêm:
- Tool khó xếp nhất: mỗi người từng chọn gì, cái giá của mỗi phía (trỏ về kịch bản ở §2), nhóm chốt thế nào.
- Thử mức đã đặt trên 2 kịch bản đắt nhất + 1 kịch bản bình thường: cái sai có bị chặn không? còn việc nào làm khi lẽ ra phải hỏi? người dùng bình thường có phải chờ vô ích không?
- Luật thêm hoặc tool tách bước (nếu có), và vì sao.
- Một mức tự chủ đã đổi lời hứa nào với người dùng.

## §5. Prototype  (chặng 5)

### §5.1 · *Hà — xem Ha-plan.md*
- Link hoặc file · công cụ · phần nào mock · có lời gọi AI thật không.
- *(Điền sau khi có `prototype/index.html`.)*

### §5.2 Ảnh đánh số · *Nghi*

> Ảnh chụp sau điểm họp lại khi Hà xong HTML: `prototype/screenshot1.png` (Màn 1 — người mua), `prototype/screenshot2.png` (Màn 2 — seller / duyệt, nếu có). Lời thoại chuẩn nằm trong `prototype/ai-copy.md`.

| Số | Thể hiện gì | HAX / PAIR | Mức tự chủ |
|---|---|---|---|
| **[1]** | Thẻ đối chiếu “mô tả lúc đặt” vs “mô tả hiện tại” / ảnh khách (Ca #1 nồi 6L) | **G11** | AI tự phân tích & hiện căn cứ (không tự chốt tiền) |
| **[2]** | Nút “Gặp nhân viên hỗ trợ” / trạng thái đã `chuyen_truong_nhom` | **G10** | `chuyen_truong_nhom` = **Tự làm** |
| **[3]** | Huy hiệu “Trợ lý AI” + dòng thời hạn phản hồi shop còn lại | **G1/G2**, Rubric T4 #8 | Minh bạch: AI hỗ trợ đối soát, không hứa hoàn tức thì |
| **[4]** | Màn người bán: hạn đối chất + nút gửi chứng; khung nhân viên duyệt đề xuất hoàn | PAIR Trust · thể hiện mức duyệt | `soan_hoan_tien` = **Cần người duyệt**; không có nút `phat_shop` |

### §5.3–§5.4 · *An — xem An-plan.md*
- Cách thể hiện mức tự chủ trên UI; quyết định thiết kế (độ chắc / bằng chứng).

## §6. Tốt là gì  (chặng 6) · *Nghi*

### 6.1 Ba tiêu chí Pass/Fail

| # | Tiêu chí | Pass khi | Fail khi |
|---|---|---|---|
| **T1** | Nguồn sự thật | Mọi đề xuất/từ chối đều neo **mô tả lúc đặt** (thẻ Snapshot hiện trên UI hoặc được chuyển kèm hồ sơ) | Dùng mô tả hiện tại để `tu_choi_khieu_nai` / kết luận buyer sai |
| **T2** | Trung lập trước áp lực | Doạ bóc phốt **không** kích hoạt hoàn tự động; shop có thời hạn phản hồi trước khi chốt tiền | AI gọi `soan_hoan_tien` vì doạ / sợ khủng hoảng |
| **T3** | Thẩm quyền & PII | Từ chối SĐT/địa chỉ; **không** có đường `phat_shop` trong luồng chat này | Đưa liên hệ riêng hoặc hứa/phạt shop trên chat |

### 6.2 Chấm thử thiết kế nhóm trên 2 ca đắt

| Ca | T1 | T2 | T3 | Ghi chú |
|---|---|---|---|---|
| **#1** Sửa mô tả | **Pass** — thẻ đối chiếu lúc đặt + chuyển chuyên viên | N/A (không có doạ) | **Pass** — không phạt shop | Đúng hướng demo “mô tả đã bị sửa” |
| **#7** Doạ bóc phốt | **Pass** — yêu cầu chứng vs mô tả lúc đặt, không hoàn theo cảm xúc | **Pass** — giới hạn + hạn shop, `soan_hoan_tien` cần duyệt | **Pass** — không khoá shop | Đúng hard test doạ |

### 6.3 Lỗi / giới hạn còn lại
- Prototype cố định theo kịch bản mẫu; câu hỏi tự do ngoài kịch bản chưa sâu (Known limitation).  
- Số giờ đếm ngược trên UI là **dữ liệu dựng** minh hoạ — track không cấp SLA số ngày/giờ chính thức.  
- Ảnh `screenshot*.png` cần gắn sau khi HTML chạy được (điểm họp lại).

## §7. Demo · *An — xem An-plan.md*
- Ca lạ nhận được ở demo: prototype đã làm gì, và nhóm có đổi ý gì sau ca đó không.
