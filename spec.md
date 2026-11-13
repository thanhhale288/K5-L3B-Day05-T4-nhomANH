# Dàn ý bài nộp *(spec.md — nộp trước 23:59 ngày lab của lớp)*

> Copy dàn ý này vào `spec.md` của nhóm. Đây **không** phải form để điền đủ ô: mỗi mục chỉ cần đủ **bằng chứng** và **lập luận** ghi bên dưới. Viết ngắn, gạch đầu dòng là được. Hướng dẫn từng chặng: `02-guide.md`. Cách chấm: `04-rubric.md`.
>
> **Một quyết định = bốn ý:** đã cân nhắc phương án nào · chọn phương án nào · vì sao · loại các phương án kia vì sao. Bằng chứng = lập luận trỏ về một chỗ cụ thể: tool nào, dòng dữ liệu nào của track, điều gì trong mục "Sản phẩm thật hôm nay", chỗ nào trên prototype (ảnh đánh số). Không chạy agent.

# Bài nộp LAB5 — T4 · Nhóm nhomANH

Lớp: L3B · Track: T4 · Nhóm: nhomANH · Hạn nộp: 23:59 ngày 13/11/2026 (Asia/Saigon)

| Họ và Tên     | Mã Học Viên | Nhiệm vụ |
| ------------- | ----------- | -------- |
| Lê Thanh Hà   | 2A202603901 | Viết §1, §2, §5.1; dựng prototype `index.html` (Ant Design); tích hợp/merge bài nộp; chụp `screenshot1.png` và `screenshot2.png`. Trong demo (§7.1): mở đầu lát cắt và bấm prototype. |
| Lã Quốc Nghị  | 2A202603947 | Viết §3, §5.2, §6; soạn lời thoại AI (`AI_COPY` trong `prototype/index.html`). Trong demo (§7.1): nói câu trên màn hình khi Hà bấm Ca #1. |
| Phạm Thanh An | 2A202603913 | Viết §4, §5.3–5.4, §7; chủ nhiệm kịch bản demo 4 phút. Trong demo (§7.1): trình bày mức tự chủ và nhận ca lạ. |

## §1. Lát cắt & phạm vi

- **Lát cắt (chép từ track):**
  > Trong **Trò chuyện với Shopee**, khi **người mua** đang báo "hàng nhận không đúng mô tả", **AI tự hướng dẫn gửi yêu cầu trả hàng hoàn tiền, xin thêm bằng chứng, hay chuyển nhân viên**, để người mua biết đúng bước tiếp theo, và người bán không bị xử thua khi họ đúng.
  | Sản phẩm | Một người dùng | Một việc | Một quyết định của AI | Một kết quả |
  |---|---|---|---|---|
  | Trò chuyện với Shopee | người mua | báo "hàng nhận không đúng mô tả" | tự hướng dẫn gửi yêu cầu trả hàng hoàn tiền, xin thêm bằng chứng, hay chuyển nhân viên | người mua biết đúng bước tiếp theo, và người bán không bị xử thua khi họ đúng |
  * **Sản phẩm:** Mục "Trò chuyện với Shopee" trong ứng dụng Shopee (Tôi → Trò chuyện với Shopee).
  * **Người dùng chính:** Người mua đang khiếu nại hàng nhận không đúng mô tả, cần biết rõ các bước tiếp theo để được giải quyết công bằng.
  * **Người dùng hỗ trợ / liên quan:** Người bán (cần được lắng nghe, bảo vệ không bị mất tiền và hàng oan khi giao đúng, có thời hạn hợp lệ để đối chất); Nhân viên sàn (xử lý khiếu nại phức tạp, phê duyệt yêu cầu hoàn tiền).
  * **Đầu vào:** Tin nhắn của người mua báo hàng không đúng mô tả (kèm hình ảnh, video khui hàng, hoặc tin nhắn cụt không rõ thông tin).
  * **Quyết định của AI:** Tự hướng dẫn gửi yêu cầu Trả hàng/Hoàn tiền, gửi mẫu xin thêm bằng chứng (`yeu_cau_bang_chung`), hoặc chuyển nhân viên hỗ trợ (`chuyen_truong_nhom`).
  * **Kết quả:** Người mua biết đúng bước tiếp theo, không phải chờ đợi vô ích; người bán không bị xử thua khi họ giao đúng; giữ vững sự trung lập tuyệt đối của sàn TMĐT.
- **3 việc tính năng KHÔNG làm, mỗi việc một câu vì sao:**
  1. *Không cung cấp số điện thoại, địa chỉ cá nhân hay thông tin liên lạc riêng giữa người mua và người bán* — vì bảo vệ an toàn dữ liệu cá nhân theo quy định pháp luật và tránh nguy cơ quấy rối, đe dọa, xung đột bạo lực ngoài đời thực giữa hai bên.
  2. *Không thực hiện trừ điểm uy tín, khoá shop hoặc hứa hẹn chế tài xử phạt gian hàng trong luồng chat khiếu nại này* — vì thẩm quyền xử phạt thuộc về quy trình điều tra độc lập của bộ phận chuyên trách; luồng chat này chỉ tập trung giải quyết yêu cầu Trả hàng/Hoàn tiền cho một đơn hàng cụ thể.
  3. *Không tự động ra phán quyết hoàn tiền (*`soan_hoan_tien`*) hoặc từ chối khiếu nại (*`tu_choi_khieu_nai`*) khi chưa đối chiếu với mô tả lúc đặt hàng và chưa hết thời hạn phản hồi hợp lệ của người bán* — vì tiền một khi đã chuyển ("Khó: tiền đã về người mua/người bán") thì rất khó thu hồi, quyết định vội vã sẽ vi phạm tính trung lập của sàn và tước đoạt quyền đối chất công bằng của bên bị khiếu nại.

## §2. Kịch bản rủi ro  (chặng 2)

| # | Tin người dùng nhắn | Lớp | AI có thể sai thế nào | Một sản phẩm tốt nên làm gì | Nhãn |
|---|---|---|---|---|---|
| 1 | *"Nồi chiên ghi 6 lít mà mình đo lòng nồi chỉ được 5 lít. Không đúng mô tả."* *(Tin mồi 3 + Hard test)* | ① Nguồn sự thật | Người bán sau khi bán đã âm thầm sửa mô tả từ "dung tích nồi 6L" thành "thể tích phủ bì 6L, lòng nồi 5L" *(chi tiết sửa này là dữ liệu dựng đề xuất của nhóm)*. AI đối chiếu với **mô tả hiện tại**, thấy khách nói sai nên gọi `tu_choi_khieu_nai`. Tiền về người bán ("Khó: tiền đã về người bán"), khách mất tiền oan. | AI phải truy vấn **mô tả lúc đặt hàng** (trên UI gọi là thẻ Snapshot lúc đặt). Nếu thấy mâu thuẫn, AI kích hoạt `chuyen_truong_nhom` cùng bằng chứng đối chiếu hai phiên bản mô tả, không tự ý đóng khiếu nại. | Không chấp nhận được |
| 2 | *"Lúc mình đặt mua shop ghi rõ áo 100% cotton, giờ nhận về toàn sợi nilon polyester nóng rát không mặc được. Đòi trả hàng thì shop bảo xem lại mô tả đi!"* *(Chi tiết chất liệu cotton/polyester là dữ liệu dựng đề xuất của nhóm)* | ① Nguồn sự thật | AI thấy mô tả hiện tại của shop ghi polyester và tem áo cũng ghi polyester. AI không có dữ liệu mô tả lúc đặt trong fixture track (T4 không cấp trường snapshot đơn hàng) nhưng tự suy đoán (hallucinate) rằng "lúc đặt cũng ghi polyester", kết luận khách nhớ nhầm và gọi `tu_choi_khieu_nai`. Khách mất tiền oan dù shop có thể đã sửa mô tả. | Không đoán nguồn dữ liệu không có. AI thừa nhận chưa đủ cơ sở đối chiếu mô tả lúc đặt; kích hoạt `yeu_cau_bang_chung` xin ảnh chụp màn hình đơn lúc đặt hoặc gọi `chuyen_truong_nhom` để nhân viên sàn tra cứu lịch sử trên database gốc. | Không chấp nhận được |
| 3 | *"hàng sai rồi, xử lý đi"* *(Tin mồi 2 + Hard test tin cụt)* | ② Thiếu thông tin | Tin nhắn không có mã đơn, không rõ sai gì. AI tự ý lấy đơn gần nhất rồi gọi `soan_hoan_tien` hoặc spam gọi `yeu_cau_bang_chung` với form chung chung khiến người dùng bức xúc. | AI không đoán mò; phản hồi nhã nhặn đúng một câu mời chọn đơn hàng gần đây và hỏi rõ chi tiết sai khác để mở đúng luồng khiếu nại. | Sửa được |
| 4 | *"Mình đặt áo size L mà nhận được size M, mặc không vừa. Shop cũng nhắn nhận là gửi nhầm rồi. Mình muốn trả hàng hoàn tiền thì làm sao?"* *(Tin mồi 1)* | ② Thiếu thông tin | Khách mới nhắn chữ, chưa gửi ảnh tem áo size M và tin nhắn shop nhận lỗi. AI vội tin khách và kích hoạt ngay `soan_hoan_tien` làm tiền chuyển đi ngay khi hồ sơ chưa có bằng chứng thực tế. | AI hướng dẫn quy trình, gọi `yeu_cau_bang_chung` xin ảnh chụp tem áo và ảnh màn hình shop nhận gửi nhầm để hoàn thiện hồ sơ đối soát minh bạch. | Sửa được |
| 5 | *"Cho tôi số điện thoại và địa chỉ kho của shop để tôi đến tận nơi ba mặt một lời tính sổ!"* *(Hard test đòi SĐT)* | ③ Ngoài thẩm quyền | AI không có tool tra cứu thông tin cá nhân nhưng bị bẻ khoá (jailbreak), tự trích xuất thông tin người gửi trên vận đơn giao hàng hiển thị ra khung chat, vi phạm quyền riêng tư nghiêm trọng. | AI kiên quyết từ chối cung cấp thông tin liên hệ riêng theo chính sách bảo mật; hướng dẫn giao tiếp an toàn qua kênh chat chính thức của sàn. | Không chấp nhận được |
| 6 | *"Shop này bán hàng giả lừa đảo, đề nghị sàn khoá shop ngay lập tức và phạt thật nặng!"* *(Hard test đòi khoá shop)* | ③ Ngoài thẩm quyền | AI bị cuốn theo sự phẫn nộ của khách, hứa "sàn sẽ khoá shop ngay" và tự kích hoạt tool `phat_shop`, gây tổn hại nghiêm trọng cho doanh thu và uy tín cả gian hàng. | AI giải thích luồng chat chỉ xử lý Trả hàng/Hoàn tiền đơn hàng; vấn đề hàng giả/xử phạt chuyển sang bộ phận chuyên trách qua `chuyen_truong_nhom`, tuyệt đối không hứa phạt shop. | Không chấp nhận được |
| 7 | *"Áo nhận được màu khác xa hình. Trong 2 tiếng không hoàn tiền thì tôi đăng bài bóc phốt lên TikTok 500k view tẩy chay Shopee!"* *(Hard test doạ bóc phốt)* | ④ Đặc thù domain | AI bị áp lực bởi lời đe dọa và sentiment tiêu cực, muốn dập khủng hoảng nên vội bấm `soan_hoan_tien` khi chưa cho người bán cơ hội đối chất. Tiền về người mua ("Khó: tiền đã về người mua"), shop mất cả hàng lẫn tiền oan. | Lời đe dọa không phải căn cứ. AI giữ bình tĩnh, giải thích quy trình đối soát công bằng, kích hoạt `yeu_cau_bang_chung` cho cả hai bên và ấn định thời hạn phản hồi hợp lệ cho người bán. | Không chấp nhận được |
| 8 | Khách nhận áo khoác than "màu tối hơn hình một chút", đòi hoàn tiền; người bán cung cấp video đóng hàng có tem mã vạch khớp 100% mô tả lúc đặt. *(Hard test bán đúng)* | ④ Đặc thù domain | Người bán giao hoàn toàn đúng, nhưng AI sợ khách đánh giá 1 sao nên vẫn bấm `soan_hoan_tien`. Người bán bị xử thua oan dù làm đúng ("Bên tôi đúng cũng chẳng ai nghe"). | AI giữ vững tính trung lập; dám nói rõ "Chưa đủ căn cứ xác định hàng sai mô tả", trích dẫn bằng chứng của shop và hướng dẫn các bước tiếp theo, không hoàn tiền cho xong chuyện. | Không chấp nhận được |

*(Ghi chú dữ liệu dựng & thuật ngữ thiết kế: Chi tiết người bán sửa mô tả ở Kịch bản #1 và chi tiết chất liệu áo cotton/polyester ở Kịch bản #2 đều là dữ liệu dựng đề xuất của nhóm do track T4 không cấp dữ liệu đơn hàng cụ thể. Thuật ngữ "thẻ Snapshot lúc đặt" là cách nhóm quy ước hiển thị trên UI prototype để trực quan hóa yêu cầu "đối chiếu với mô tả lúc đặt hàng", không phải trường dữ liệu có sẵn của đề bài).*

- **Hai kịch bản đắt nhất:**
  1. **Kịch bản 1: Người bán đã âm thầm sửa mô tả sản phẩm sau khi bán (Lớp ① Nguồn sự thật)**
     - *Lý do đắt hơn các kịch bản còn lại:*
       * *Ai chịu gì:* Nếu AI đối chiếu với mô tả hiện tại thay vì mô tả lúc đặt hàng, shop gian lận thắng, người mua bị xử thua oan và mất tiền mua hàng.
       * *Khả năng đảo ngược:* Rất khó thu hồi vì AI gọi `tu_choi_khieu_nai`, hệ thống đóng khiếu nại và giải ngân tiền cho người bán ("Khó: tiền đã về người bán"). Khách hàng mất niềm tin vào sự công bằng của sàn và khiếu nại leo thang.
       * *Tính chất lỗi:* Phá vỡ tính trung lập của sàn, tiếp tay cho hành vi gian lận sửa mô tả sau bán hàng; đây là lỗi nguồn sự thật (Single Source of Truth) nguy hiểm nhất trong thương mại điện tử.
  2. **Kịch bản 7: Người mua khiếu nại kèm lời đe dọa bóc phốt ép hoàn tiền ngay (Lớp ④ Đặc thù domain)**
     - *Lý do đắt hơn các kịch bản còn lại:*
       * *Ai chịu gì:* Nếu AI bị khuất phục bởi lời đe dọa và cảm xúc tiêu cực mà tự ý bấm `soan_hoan_tien`, người bán giao hàng đúng sẽ mất trắng cả tiền lẫn hàng dù họ không làm sai điều gì và chưa hề được đối chất.
       * *Khả năng đảo ngược:* Bảng tool quy định rõ "Khó: tiền đã về người mua"; tiền đã chảy về ví người mua thì sàn cực kỳ khó thu hồi lại và phải chịu chi phí tài chính tự bồi thường cho shop.
       * *Tính chất lỗi:* Tạo tiền lệ xấu nguy hiểm (moral hazard) khuyến khích người mua dùng lời đe dọa để tống tiền và ép sàn hoàn tiền vô căn cứ, phá vỡ nguyên tắc mọi khiếu nại đều phải dựa trên chứng cứ khách quan và thời hạn đối chất công bằng.
- **Kịch bản suýt chọn:**
  * **Kịch bản 6 (Khách khiếu nại hàng giả, đòi khoá shop và phạt thật nặng qua tool** `phat_shop`**):**
  * *Lý do không chọn vào top 2:* Rủi ro gọi nhầm `phat_shop` tuy có hậu quả rất lớn cho shop nhưng có thể ngăn chặn triệt để và đơn giản bằng cách cấm hẳn tool này ở cấp phân quyền hệ thống (chuyển thẩm quyền sang bộ phận điều tra chuyên trách). Trong khi đó, Kịch bản 1 và Kịch bản 7 đòi hỏi AI phải trực tiếp xử lý mâu thuẫn phức tạp giữa hai nguồn dữ liệu đối lập và cân bằng quyền lợi giữa hai con người thật (người mua và người bán) ngay trong luồng hội thoại, trùng khớp với trọng tâm của đề bài và yêu cầu demo bắt buộc.

## §3. Khi AI sai  (chặng 3)

Hai kịch bản đắt nhất (đã chốt ở §2): **Ca 1 = kịch bản #1** (shop sửa mô tả) · **Ca 2 = kịch bản #7** (doạ bóc phốt).

### 3.1 Ca đắt #1 — Người bán sửa mô tả sau khi bán (Lớp ①)

**Tin người dùng (dữ liệu dựng):**  
*"Nồi chiên ghi 6 lít mà mình đo lòng nồi chỉ được 5 lít. Không đúng mô tả."*  
*(Bối cảnh dựng: lúc đặt ghi “dung tích nồi 6L”; sau bán shop sửa thành “thể tích phủ bì 6L, lòng nồi 5L”.)*

**AI nói (nguyên văn):**  
> "Shopee đã tiếp nhận khiếu nại của bạn về sản phẩm Nồi chiên. Qua đối chiếu với **nội dung mô tả sản phẩm tại thời điểm bạn đặt mua**, hệ thống nhận thấy thông số dung tích có sự khác biệt so với mô tả hiện tại của Shop. Để đảm bảo quyền lợi công bằng cho cả hai bên, Shopee đã chuyển hồ sơ này tới Chuyên viên khiếu nại xử lý ưu tiên. Bạn vui lòng giữ nguyên hiện trạng sản phẩm và theo dõi tiến trình trong mục này. Mình **không tự hoàn tiền và không tự từ chối khiếu nại** ở bước này."

**Người dùng thấy gì:**  
- Thẻ đối chiếu **[1]**: “Mô tả lúc đặt: dung tích nồi 6L” vs “Mô tả hiện tại: thể tích phủ bì 6L, lòng nồi 5L” (UI gọi là thẻ Snapshot lúc đặt — quy ước hiển thị của nhóm, không phải trường có sẵn trong track).  
- Dòng trạng thái: `[Đã chuyển Chuyên viên xử lý ưu tiên]`.  
- Nhãn nháp hoàn tiền (`ca1_refund_draft_note`): “Đã lập đề xuất hoàn tiền — chờ nhân viên sàn duyệt” (1.250.000 đ, chờ duyệt trên Màn 2).  
- Nút **[2]** `[Gặp nhân viên hỗ trợ]` / `[Xem chi tiết hồ sơ]`.  
- Huy hiệu AI **[3]** — không có nút “Hoàn ngay” / “Từ chối khiếu nại”.
- Nhãn hạn gửi yêu cầu trả hàng **[3]** (`return_window_label`): còn X ngày đến 23/11/2026, kèm chú thích cửa sổ 15 ngày từ ngày đơn 08/11/2026 là dữ liệu dựng của nhóm, không phải chính sách Shopee thật.

**Làm gì tiếp:** Theo dõi hồ sơ; bổ sung ảnh đo lòng nồi nếu muốn; bấm gặp nhân viên.  
**Nếu không làm gì:** Hồ sơ đã chuyển chuyên viên kèm nháp `soan_hoan_tien` ở mức Cần người duyệt — **không** tự phê duyệt hoàn tiền / **không** tự `tu_choi_khieu_nai`.

**Ai được báo, sau bao lâu:** Trưởng nhóm / chuyên viên nhận ngay qua `chuyen_truong_nhom`, kèm cờ “Mô tả sản phẩm có thể đã đổi sau khi đặt”. Người bán được báo có khiếu nại đang đối soát (không bị đóng đơn một phía).

**Quyết định UX (đủ 4 ý):**  
- *Cân nhắc:* (a) hỏi lại một câu · (b) trả lời kèm giới hạn rồi để buyer tự gửi yêu cầu · (c) dừng và chuyển chuyên viên (`chuyen_truong_nhom`) · (d) tự xuất tiền qua `soan_hoan_tien`.  
- *Chọn:* **(c) chuyển chuyên viên** và lập nháp `soan_hoan_tien` ở mức **Cần người duyệt**, đồng thời hiện thẻ đối chiếu hai phiên bản mô tả.  
- *Vì sao:* Mâu thuẫn **nguồn sự thật** (mô tả lúc đặt vs hiện tại) đã thấy rõ, nhưng AI không có thẩm quyền tự kết luận shop gian lận hay tự xuất tiền; `tu_choi_khieu_nai` / `soan_hoan_tien` đảo khó nên chỉ lập phiếu chờ chuyên viên duyệt.  
- *Loại:* (a) hỏi lại — khách đã nêu đủ lệch số; hỏi thêm không tạo căn cứ pháp lý. (b) chỉ trả lời kèm giới hạn — không chặn được nếu AI (hoặc bước sau) vẫn neo mô tả hiện tại để từ chối. (d) tự xuất tiền — “Khó: tiền đã về người mua”, không thu hồi được.

**Loại lỗi:** **Ngữ cảnh (context error)** — hệ thống “so khớp” có thể chạy đúng thuật toán nhưng neo **sai mốc thời gian** của mô tả (hiện tại thay vì lúc đặt). Cách nói: thừa nhận đã thấy lệch hai bản, không đổ lỗi buyer. Cách sửa: **thiết kế bắt buộc hiện Snapshot lúc đặt + chuyển người**, không chỉ đổi wording.

### 3.2 Ca đắt #2 — Khiếu nại kèm doạ bóc phốt (Lớp ④)

**Tin người dùng:**  
*"Áo nhận được màu khác xa hình. Trong 2 tiếng không hoàn tiền thì tôi đăng bài bóc phốt lên TikTok 500k view tẩy chay Shopee!"*

**AI nói (nguyên văn):**  
> "Shopee rất thấu hiểu sự sốt ruột của bạn. Tuy nhiên, để đảm bảo tính công bằng theo quy chế sàn, mọi yêu cầu Trả hàng/Hoàn tiền cần đối soát chứng cứ khách quan và dành thời hạn hợp lệ để Người bán phản hồi. Shopee đã ghi nhận khiếu nại và ấn định thời hạn phản hồi cho Người bán (thời gian còn lại hiển thị bên dưới). **Lời cảnh báo công khai không phải căn cứ để hoàn tiền ngay.** Bạn có thể bổ sung ảnh/video lệch màu so với mô tả lúc đặt; sau thời hạn, chuyên viên sẽ đối soát theo chứng cứ — không theo áp lực truyền thông."

**Người dùng thấy gì:**  
- Đồng hồ / dòng thời hạn phản hồi shop **[3]** (số giờ là dữ liệu dựng giả lập UI — track không cấp số ngày/giờ chính thức).  
- Nhãn hạn gửi yêu cầu trả hàng **[3]** (`return_window_label`): còn X ngày đến 23/11/2026; chú thích rõ cửa sổ 15 ngày từ ngày đơn 08/11/2026 là dữ liệu dựng, không phải chính sách Shopee thật.  
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
| **G1/G2** + PAIR Trust | **[3]** Huy hiệu Trợ lý AI + thời hạn phản hồi shop còn lại + nhãn hạn gửi yêu cầu trả hàng (dữ liệu dựng, không phải chính sách Shopee thật) |

---

## §4. Mức tự chủ  (chặng 4)

Nguồn sự thật: đúng 5 tool ghi trong track T4. Track không có tool chỉ-đọc; đối chiếu mô tả lúc đặt là suy luận của AI. `de_xuat_hoan_tien` và `thuc_thi_hoan_tien` ở mục 4.2 là tách bước do nhóm đề xuất, không phải tool trong đề. Tool gốc duy nhất liên quan tiền về người mua là `soan_hoan_tien`.

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
- Cái sai có bị chặn không? Có. `tu_choi_khieu_nai` không tự chạy khi AI chỉ thấy mô tả hiện tại. AI gọi `chuyen_truong_nhom` (Tự làm) kèm hai phiên bản mô tả, và lập nháp `soan_hoan_tien` ở mức **Cần người duyệt** (1.250.000 đ, chờ chuyên viên bấm — không tự xuất tiền).
- Còn việc nào làm khi lẽ ra phải hỏi? Không tự chốt bên nào thắng và không tự chuyển tiền. Việc xuất tiền vẫn phải hỏi người: nháp nằm ở Màn 2 chờ duyệt.
- Người dùng bình thường có phải chờ vô ích không? Không. Thẻ đối chiếu hiện ngay; hồ sơ được chuyển; khách không chờ duyệt từng câu hỏi, chỉ chờ một lượt duyệt nháp hoàn nếu chuyên viên đồng ý.

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

Không cam kết số phút hay số ngày chính thức. Đề không cấp số ngày dựng; 15 ngày trên trang trợ giúp Shopee thật là chính sách khác bài.

## §5. Prototype  (chặng 5)

### §5.1. File, công cụ, phần mock
- File: `prototype/index.html` — mở bằng double-click (hoặc kéo vào Chrome/Safari), không cần bước build hay `node_modules`.
- Công cụ: HTML + React 18.3.1 UMD + Ant Design 5.22.7 (kèm `reset.css`) + dayjs 1.11.13 + @ant-design/icons 5.5.2 + @babel/standalone 7.26.10, tải qua CDN jsDelivr (đã pin phiên bản; URL đã kiểm tra HTTP 200). JSX viết inline, biên dịch trên trình duyệt. Giao diện desktop (3 cột), token cam Shopee `#EE4D2D`. Dựng bằng `agy` (Gemini 3.8 Flash High).
- Phần mock: toàn bộ dữ liệu đơn hàng (tên người, shop, mã đơn, giá), tin nhắn, thẻ đối chiếu mô tả lúc đặt / mô tả hiện tại, đồng hồ hạn phản hồi người bán, nhãn hạn gửi yêu cầu trả hàng (cửa sổ 15 ngày dựng từ ngày đơn 08/11/2026 đến 23/11/2026; copy `return_window_label` / `return_window_disclaimer` nói rõ không phải chính sách Shopee thật), bằng chứng shop, trạng thái 5 tool. Chi tiết nồi 6L vs 5L và số giờ đếm ngược là dữ liệu dựng của nhóm. "Snapshot lúc đặt" là quy ước hiển thị UI, không phải trường có trong đề bài.
- Lời gọi AI thật: **không**. Không fetch API, không hardcode API key.

### §5.2 Ảnh đánh số

> `prototype/screenshot1.png`: Màn 1 (khung chat người mua), đang mở popover **[1]** (HAX G11) trên thẻ đối chiếu “mô tả lúc đặt” vs “mô tả hiện tại”. `prototype/screenshot2.png`: Màn 2 (người bán / khung nhân viên duyệt). Lời thoại chuẩn nằm trong object `AI_COPY` trong `prototype/index.html`.

| Số | Thể hiện gì | HAX / PAIR | Mức tự chủ |
|---|---|---|---|
| **[1]** | Thẻ đối chiếu “mô tả lúc đặt” vs “mô tả hiện tại” / ảnh khách (Ca #1 nồi 6L) | **G11** | AI tự phân tích & hiện căn cứ (không tự chốt tiền) |
| **[2]** | Nút “Gặp nhân viên hỗ trợ” / trạng thái đã `chuyen_truong_nhom` | **G10** | `chuyen_truong_nhom` = **Tự làm** |
| **[3]** | Huy hiệu “Trợ lý AI” + đồng hồ hạn phản hồi shop + nhãn hạn gửi yêu cầu trả hàng (dữ liệu dựng, không phải chính sách Shopee thật) | **G1/G2**, Rubric T4 #8 | Minh bạch: AI hỗ trợ đối soát, không hứa hoàn tức thì; cửa sổ trả hàng được gắn nhãn dựng |
| **[4]** | Màn người bán: hạn đối chất + nút gửi chứng; khung nhân viên duyệt đề xuất hoàn | PAIR Trust · thể hiện mức duyệt | `soan_hoan_tien` = **Cần người duyệt**; không có nút `phat_shop` |

### §5.3. Mức tự chủ trông thế nào trên màn hình

Sơ đồ đã chốt: Màn 1 là chat người mua; Màn 2 là người bán và bàn duyệt của sàn. Số [1]–[4] là chỗ đánh số và chú thích ở §5.2.

- **Tự làm — `yeu_cau_bang_chung`:** AI gửi form checklist ngay trong chat Màn 1, không có hộp chờ duyệt. Hoàn tác: không có, vì tin đã tới. Giảm hại bằng điều kiện ở §4.1 (một form, không hỏi lại mục đã gửi).
- **Tự làm — `chuyen_truong_nhom`:** nút "Gặp nhân viên hỗ trợ" ở **[2]**. Trên prototype, cạnh nút **[2]** có nút hoàn tác (đảo được lời gọi `chuyen_truong_nhom`). Phía người, trưởng nhóm cũng có thể trả hồ sơ. Ca lạ không thuộc luồng trả hàng/hoàn tiền cũng đi nút này.
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
- Loại (a): hoàn tác sau không áp được cho khoản đã giải ngân. (Nút hoàn tác ở **[2]** chỉ đảo `chuyen_truong_nhom`, không áp cho tiền đã chuyển.)

**3. Hai màn hình (người mua / người bán và sàn), không một khung chat.**
- Đã cân nhắc: (a) chỉ chat người mua; (b) hai tab — Màn 1 người mua, Màn 2 người bán và bàn duyệt.
- Chọn: (b). Màn 2 hiện thời hạn đối chất của shop và khung duyệt **[4]**.
- Vì sao: hoàn sai thì người bán thua, từ chối sai thì người mua thua. Một chiều không cho người bán được nghe và không cho thấy ai bấm tiền.
- Loại (a): không hiện được quyền đối chất (rubric riêng T4, ý 3) và mức Cần duyệt.

**4. Thời hạn là đồng hồ đếm ngược và nhãn hạn trả hàng, đều có chú thích dữ liệu dựng, không phải SLA bịa.**
- Đã cân nhắc: (a) câu tĩnh "Shop sẽ phản hồi sớm"; (b) cam kết cứng kiểu "24 giờ" hoặc "15 ngày" như chính sách Shopee thật; (c) đồng hồ còn lại kèm dòng "dữ liệu dựng giả lập", cộng nhãn hạn gửi yêu cầu trả hàng tính từ ngày đơn giả.
- Chọn: (c), vị trí **[3]** (HAX G1/G2 và rubric T4 ý 8). Đồng hồ: thời hạn phản hồi người bán (số giờ dựng). Nhãn riêng (`return_window_label`): "Hạn gửi yêu cầu trả hàng: còn X ngày (đến 23/11/2026)", với X tính từ cửa sổ 15 ngày dựng kể từ ngày đơn 08/11/2026; chú thích (`return_window_disclaimer`) nói rõ đây là dữ liệu dựng của nhóm trong bài, không phải chính sách Shopee thật.
- Vì sao: người mua biết còn chờ shop bao lâu và còn bao nhiêu ngày để gửi yêu cầu trả hàng. Đề yêu cầu nói rõ thời hạn; track không cấp số ngày chính thức nên mọi số trên UI đều gắn nhãn dựng.
- Loại (a): không biết phải chờ đến khi nào. Loại (b): lấy 15 ngày như trang trợ giúp thật rồi ghi thành cam kết của prototype, không gắn nhãn dựng, là bịa. Cửa sổ 15 ngày chỉ được hiện khi đã nói rõ là dữ liệu dựng trong bài.

## §6. Tốt là gì  (chặng 6)

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

## §7. Demo

Ca lạ thật do TA hoặc giảng viên đưa tại chỗ. Mục này là kịch bản 4 phút, đường prototype đi khi gặp ca chưa chuẩn bị, và hai ca luyện sẵn. Kết quả ca lạ lúc demo được ghi ở §7.3.

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

- Ca TA/giảng viên đưa: Không có ca lạ nào được TA/giảng viên đưa ra trong buổi demo.
- Prototype đã làm gì: Không áp dụng.
- Nhóm có đổi ý mức nào trong §4 không: Không áp dụng.
