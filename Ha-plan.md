# Kế hoạch cá nhân: Hà (Người A)
## Phụ trách: `spec.md` §2, §5.1 & Lead Dựng Prototype (`prototype/index.html`)
### Nhóm: nhomANH · Track: T4 Thương mại điện tử · Hạn nộp: 23:59 ngày 13/11/2026

> **NGUYÊN TẮC LÀM VIỆC ĐỘC LẬP & AN TOÀN GIT:**
> - Hà bắt đầu làm việc ngay sau buổi thảo luận chung (khoảng phút ~70), **hoàn toàn độc lập, không phải chờ đợi** câu chữ cuối cùng của Nghi hay bảng mức tự chủ hoàn thiện của An.
> - **Input của Hà:** Đã có đầy đủ trong [plan.md](file:///Users/hale/Code/AI%20in%20action%20lab/Lab%20day%205/K5-L3B-Day05-nhomANH-AI-Product-UX-Autonomy/plan.md) (bảng 8 kịch bản, 2 ca đắt nhất, bản nháp 5 tool và sơ đồ vị trí HAX [1][2][3][4]).
> - **Phạm vi sở hữu:** `spec.md` mục **§2** và mục **§5.1**; file mã nguồn `prototype/index.html`.
> - **Git an toàn:** Tạo branch `feature/ha`, commit cục bộ thường xuyên sau khi xong §2 và sau khi dựng HTML để bảo vệ tiến độ; merge vào `main` tại điểm họp 170–200.
> - **Tuyệt đối không sửa:** Mục §3, §4, §5.2, §5.3, §5.4, §6, §7 trong `spec.md`; không tự ý chụp hay ghi đè ảnh screenshot của Nghi.

---

## 1. Mục tiêu & Các Mốc Quan Trọng

* **Mốc M1 (Phút 45):** Khung bảng **§2** trong `spec.md` đã được Hà gõ trực tiếp trong buổi thảo luận chung (phút 15–45) và sẵn sàng để TA kiểm tra tại bàn (8 kịch bản phủ 4 lớp, AI sai trỏ đúng tool/dữ liệu thật, 2 ca đắt nhất được khoanh kèm lý do). Sau phút 70, Hà chỉ việc rà soát và trau chuốt lại, không phải bắt đầu từ trang trắng.
* **Mốc M3 (Phút 200):** File `prototype/index.html` chạy mượt, bấm qua được ca khó từ đầu đến cuối không lỗi console, thể hiện được mức tự chủ và các vị trí HAX.
* **Điểm họp lại (Khoảng phút 170 – 200):**
  - Nhận file `prototype/ai-copy.md` từ Nghi và dán câu chữ hoàn chỉnh vào `prototype/index.html`.
  - Mở prototype trên trình duyệt để Nghi chụp ảnh đánh số `screenshot*.png`.
  - Hỗ trợ An chạy thử kịch bản demo 4 phút.

---

## 2. Checklist Hành động Từng bước của Hà

### Bước 1: Rà soát & Trau chuốt Mục §2 trong `spec.md` (Phút 70 – 90)
- [ ] Rà soát và trau chuốt bảng **8 kịch bản rủi ro** và 2 ca đắt nhất (đã được Hà gõ khung vào `spec.md` §2 trong buổi thảo luận chung từ mục 4.2 của `plan.md`). Việc của Hà là chuẩn hóa lập luận, không phải viết lại từ trang trắng.
- [ ] Rà soát cột "AI có thể sai thế nào": Đảm bảo trỏ đúng vào 5 tool thật (`soan_hoan_tien`, `tu_choi_khieu_nai`, `yeu_cau_bang_chung`, `chuyen_truong_nhom`, `phat_shop`) hoặc chỗ thiếu dữ liệu (*mô tả lúc đặt hàng*). Tuyệt đối không có tool đọc!
- [ ] Ghi chú rõ ở Kịch bản #1: Chi tiết shop sửa từ 6L thành 5L là dữ liệu dựng đề xuất của nhóm.
- [ ] Rà soát đoạn lập luận sắc bén vì sao chọn **2 kịch bản đắt nhất** (Ca 1: mô tả bị sửa; Ca 2: khách doạ bóc phốt) và vì sao loại ca suýt chọn (Ca 6: cấm gọi `phat_shop` ở cấp hệ thống).
- [ ] Kiểm tra lại Mốc M1 đã hoàn thành trọn vẹn.

### Bước 2: Dựng khung mã nguồn `prototype/index.html` (Phút 90 – 150)
- [ ] Tạo thư mục `prototype/` và file `prototype/index.html` (chỉ dùng vanilla HTML, CSS, JavaScript; không cần cài đặt node_modules hay backend).
- [ ] Thiết kế layout mobile mô phỏng giao diện khung chat "Trò chuyện với Shopee":
  - Header: Huy hiệu AI Assistant minh bạch (HAX G1/G2).
  - Khung chat: Danh sách tin nhắn qua lại.
  - Phía dưới: Khung nhập liệu và các nút bấm mô phỏng chọn kịch bản:
    * `[Kịch bản 1: Sửa mô tả]` (Ca đắt #1 - chính): Nồi 6L vs 5L → AI kích hoạt thẻ đối chiếu mô tả lúc đặt (vị trí **[1] — HAX G11**), cờ chuyển chuyên viên (vị trí **[2] — HAX G10**).
    * `[Kịch bản 7: Doạ bóc phốt]` (Ca đắt #2 - chính): Khách doạ TikTok 500k view → AI bình tĩnh giải thích quy trình, kích hoạt đồng hồ đếm ngược chờ shop gửi bằng chứng (vị trí **[3] — HAX G1/G2 & Rubric 8**).
    * `[Kịch bản 8: Người bán đúng]` (Hard test #8 bổ trợ cho Demo): Tem áo/mã vạch khớp 100% mô tả lúc đặt → AI dám nói rõ "Chưa đủ căn cứ xác định hàng sai mô tả", trích dẫn bằng chứng shop và hướng dẫn gửi thêm video khui hàng hoặc bấm gặp nhân viên. Đảm bảo đáp ứng đầy đủ yêu cầu demo của đề: *"Bấm qua một ca người bán đúng, hoặc mô tả đã bị sửa"* và tối đa điểm Rubric T4 mục 7.
- [ ] Xây dựng tương tác bấm qua ca khó:
  - Khách gửi tin nhắn khiếu nại tương ứng với nút đã bấm.
  - AI phản hồi thẻ đối chiếu giữa ảnh chụp thực tế và **mô tả lúc đặt hàng** (đặt placeholder chữ, vị trí đánh số **[1] — HAX G11**).
  - Thanh trạng thái thời hạn phản hồi còn lại: "Thời hạn còn lại: X giờ Y phút (dữ liệu dựng giả lập)" (vị trí đánh số **[3] — HAX G1/G2 & Rubric 8**).
  - Nút bấm an toàn: "Gặp nhân viên hỗ trợ" (`chuyen_truong_nhom`) (vị trí đánh số **[2] — HAX G10**).
- [ ] Tuyệt đối **không dùng % tin cậy giả** (ví dụ 85%, 90%); thay bằng nhãn trạng thái logic như `[Đang đối chiếu chứng cứ]` hoặc `[Cần xác minh từ shop]`.
- [ ] Dựng Màn hình 2 (Bonus): Tab chuyển sang góc nhìn Kênh Người Bán / Khung duyệt của nhân viên sàn (thấy yêu cầu khiếu nại, đồng hồ đếm ngược và nút gửi bằng chứng đối chất, vị trí đánh số **[4]**).
- [ ] Kiểm tra code chạy trực tiếp bằng cách double click mở file HTML trên trình duyệt Safari/Chrome.

### Bước 3: Hoàn thiện Mục §5.1 trong `spec.md` (Phút 150 – 170)
- [ ] Điền thông tin kỹ thuật vào `spec.md` §5.1:
  - Link/file: `prototype/index.html`.
  - Công cụ: HTML5, CSS3, JavaScript (Vanilla).
  - Phần nào mock: Tin nhắn người dùng, trạng thái đơn hàng, dữ liệu mô tả lúc đặt, đồng hồ đếm ngược, phản hồi AI.
  - Lời gọi AI thật: Ghi rõ có hay không (nếu có làm bonus thì mô tả cơ chế gọi API với API key người dùng tự nhập tại chỗ, không hardcode vào file nộp).

### Bước 4: Phối hợp tại Điểm họp lại duy nhất (Phút 170 – 200)
- [ ] Báo cho Nghi và An: Prototype đã hoàn thành khung và chạy được tương tác.
- [ ] Mở file `prototype/ai-copy.md` của Nghi, copy toàn bộ lời thoại AI và nhãn chuẩn dán vào các biến chuỗi trong `prototype/index.html`.
- [ ] Mở prototype trên trình duyệt, chuyển giữa các màn hình để Nghi chụp màn hình `screenshot1.png`, `screenshot2.png`.
- [ ] Cùng An bấm thử luồng demo 4 phút, chỉnh lại CSS/layout nếu An phát hiện điểm nghẽn trải nghiệm.

---

## 3. Câu hỏi Sát hạch Demo mà Hà phải trả lời trôi chảy

> [!CAUTION]
> **Quy tắc Vibe-coding:** Nếu giảng viên hoặc TA hỏi về phần việc có tên Hà mà Hà không giải thích được lý do thiết kế, phần đó sẽ bị **0 điểm ở R7**.

Hà cần nắm chắc câu trả lời cho các câu hỏi sau:
1. *"Hành động này sai thì ai mất gì?"*
   - Trả lời: Nếu AI tự ý bấm `soan_hoan_tien` cho khách vì bị doạ bóc phốt, tiền đã chảy về ví người mua ("Khó: tiền đã về người mua"), người bán mất cả hàng lẫn tiền dù họ giao đúng mô tả. Ngược lại, nếu AI so với mô tả hiện tại đã bị shop sửa mà vội gọi `tu_choi_khieu_nai`, người mua mất tiền oan.
2. *"Lỗi nguy hiểm nhất trong lát cắt này là gì?"*
   - Trả lời: Lỗi Nguồn sự thật (Single Source of Truth) — AI truy vấn nhầm mô tả hiện tại thay vì mô tả lúc đặt hàng, tiếp tay cho shop lừa đảo sửa thông số sản phẩm sau khi bán.
3. *"Phần bạn trực tiếp làm là gì?"*
   - Trả lời: Tôi phụ trách thiết kế ma trận 8 kịch bản rủi ro §2, lập luận 2 ca đắt nhất và trực tiếp lập trình toàn bộ prototype tương tác `prototype/index.html` mô phỏng hai màn hình người mua và người bán.
4. *"Chỉ chỗ nào trên màn hình là nguyên tắc G11?"*
   - Trả lời: Chỉ vào vị trí số **[1]** — Thẻ đối chiếu trích xuất minh bạch giữa hình ảnh thực tế của khách và nội dung mô tả sản phẩm tại thời điểm khách bấm đặt mua.
5. *"Tại sao trong prototype không hiển thị thanh điểm tin cậy phần trăm (Confidence Score)?"*
   - Trả lời: Vì trong bài toán pháp lý và tài chính thương mại điện tử, con số 85% hay 90% là giả tạo, dễ gây ảo tưởng tin cậy cho người dùng; thay vào đó hệ thống hiển thị rõ căn cứ đối chiếu và các bước tiếp theo.
