# Dàn ý bài nộp *(spec.md — nộp trước 23:59 ngày lab của lớp)*

> Copy dàn ý này vào `spec.md` của nhóm. Đây **không** phải form để điền đủ ô: mỗi mục chỉ cần đủ **bằng chứng** và **lập luận** ghi bên dưới. Viết ngắn, gạch đầu dòng là được. Hướng dẫn từng chặng: `02-guide.md`. Cách chấm: `04-rubric.md`.
>
> **Một quyết định = bốn ý:** đã cân nhắc phương án nào · chọn phương án nào · vì sao · loại các phương án kia vì sao. Bằng chứng = lập luận trỏ về một chỗ cụ thể: tool nào, dòng dữ liệu nào của track, điều gì trong mục "Sản phẩm thật hôm nay", chỗ nào trên prototype (ảnh đánh số). Không chạy agent.

# Bài nộp LAB5 — T4 · Nhóm nhomANH

Lớp: L3B · Track: T4 · Nhóm: nhomANH · Hạn nộp: 23:59 ngày 13/11/2026 (Asia/Saigon)

> **Lưu ý:** Mã học viên còn thiếu — điền trước khi nộp. Cả nhóm chốt §1 trong buổi thảo luận chung (`plan.md`); sau đó mỗi người làm task riêng theo file của mình.

| Họ và Tên     | Mã Học Viên | Việc đã làm                                    |
| ------------- | ----------- | ---------------------------------------------- |
| Lê Thanh Hà   | 2A202603901 | S2, S5.1 & prototype (main) — xem `Ha-plan.md` |
| Lã Quốc Nghị  | 2A202603947 | S3, S5.2, S6 — xem `Nghi-plan.md`              |
| Phạm Thanh An | 2A202603913 | S4, S5.3–5.4, S7 — xem `An-plan.md`            |

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

Với mỗi kịch bản đắt nhất:

- AI nói gì (nguyên văn) · người dùng thấy gì · làm gì tiếp · ai được báo, sau bao lâu.
- Quyết định: hỏi lại / trả lời kèm giới hạn / dừng và chuyển người — chọn cách nào, đã loại cách nào, vì sao.
- Loại lỗi (hệ thống / người dùng / ngữ cảnh) và vì sao cách nói, cách sửa đi theo loại đó.
- 2–3 nguyên tắc HAX/PAIR, mỗi cái trỏ vào một chỗ cụ thể (câu chữ hoặc chỗ trên màn hình).
- Lỗi nào sửa câu chữ không cứu được (nếu có), và thiết kế cứu nó thế nào.

## §4. Mức tự chủ  (chặng 4)

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

### §5.1. File, công cụ, phần mock *(Hà)*
- File: `prototype/index.html` — mở bằng double-click (hoặc kéo vào Chrome/Safari), không cần bước build hay `node_modules`.
- Công cụ: HTML + React 18.3.1 UMD + Ant Design 5.22.7 (kèm `reset.css`) + dayjs 1.11.13 + @ant-design/icons 5.5.2 + @babel/standalone 7.26.10, tải qua CDN jsDelivr (đã pin phiên bản; URL đã kiểm tra HTTP 200). JSX viết inline, biên dịch trên trình duyệt. Giao diện desktop (3 cột), token cam Shopee `#EE4D2D`. Dựng bằng `agy` (Gemini 3.8 Flash High).
- Phần mock: toàn bộ dữ liệu đơn hàng (tên người, shop, mã đơn, giá), tin nhắn, thẻ đối chiếu mô tả lúc đặt / mô tả hiện tại, đồng hồ hạn phản hồi người bán, bằng chứng shop, trạng thái 5 tool. Chi tiết nồi 6L vs 5L và số giờ đếm ngược là dữ liệu dựng của nhóm. "Snapshot lúc đặt" là quy ước hiển thị UI, không phải trường có trong đề bài.
- Lời gọi AI thật: **không**. Không fetch API, không hardcode API key.

- Link hoặc file · công cụ · phần nào mock · có lời gọi AI thật không.
- 1–2 ảnh có đánh số; mỗi số: thể hiện gì · nguyên tắc HAX/PAIR nào · mức tự chủ nào.
- Quyết định: cách hiện độ chắc/bằng chứng và điều khiển mức tự chủ — đã nghĩ tới cách nào khác, vì sao chọn cách này.

## §6. Tốt là gì  (chặng 6 — nhẹ, bỏ được nếu thiếu giờ)

- 3 tiêu chí Pass/Fail chấm được; thiết kế của nhóm đạt tiêu chí nào trên 2 kịch bản đắt nhất; lỗi còn lại.

## §7. Demo

- Ca lạ nhận được ở demo: prototype đã làm gì, và nhóm có đổi ý gì sau ca đó không.
