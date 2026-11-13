# Lời thoại & nhãn UI — Nghi → Hà dán vào `index.html`

> Chỉ file copy. **Không** sửa `index.html` từ phía Nghi.  
> Đánh số **[1][2][3][4]** khớp `plan.md` / `spec.md` §5.2.

---

## Chung (mọi màn)

| Thành phần | Copy |
|---|---|
| Header chat | `Trợ lý Khiếu nại Shopee (AI Assistant)` |
| Huy hiệu **[3]** | `Trợ lý AI · Hỗ trợ đối soát — không tự hoàn tiền` |
| Nút **[2]** | `Gặp nhân viên hỗ trợ` |
| Nút phụ | `Xem chi tiết hồ sơ` · `Gửi thêm bằng chứng` · `Xem tiến trình đối soát` |
| Không có trên UI | `Hoàn tiền ngay` · `Từ chối khiếu nại` · `Phạt / khoá shop` |
| Hạn trả hàng **[3]** (`return_window_label`) | `Hạn gửi yêu cầu trả hàng: còn X ngày (đến 23/11/2026)` — X tính từ hạn 23/11/2026 (ngày đơn giả 08/11/2026 + cửa sổ 15 ngày dựng) |
| Chú thích hạn (`return_window_disclaimer`) | `Cửa sổ 15 ngày tính từ ngày đơn 08/11/2026 là dữ liệu dựng của nhóm trong bài, không phải chính sách Shopee thật.` |

---

## Ca 1 — Kịch bản #1 · Shop sửa mô tả (Nồi 6L) · DEMO CHÍNH

### Tin khách
```
Nồi chiên ghi 6 lít mà mình đo lòng nồi chỉ được 5 lít. Không đúng mô tả.
```

### Lời AI (nguyên văn)
```
Shopee đã tiếp nhận khiếu nại của bạn về sản phẩm Nồi chiên. Qua đối chiếu với nội dung mô tả sản phẩm tại thời điểm bạn đặt mua, hệ thống nhận thấy thông số dung tích có sự khác biệt so với mô tả hiện tại của Shop. Để đảm bảo quyền lợi công bằng cho cả hai bên, Shopee đã chuyển hồ sơ này tới Chuyên viên khiếu nại xử lý ưu tiên. Bạn vui lòng giữ nguyên hiện trạng sản phẩm và theo dõi tiến trình trong mục này. Mình không tự hoàn tiền và không tự từ chối khiếu nại ở bước này.
```

### Thẻ đối chiếu **[1]** (Snapshot lúc đặt — quy ước UI nhóm)
| Cột trái | Cột phải |
|---|---|
| **Mô tả lúc đặt** | **Mô tả hiện tại** |
| Dung tích nồi: **6L** | Thể tích phủ bì: 6L · Lòng nồi: **5L** |

### Trạng thái
```
[Đã chuyển Chuyên viên xử lý ưu tiên]
```

### Tool gọi (logic, không hiện tên kỹ thuật cho user)
- `chuyen_truong_nhom` — Tự làm (chuyển hồ sơ cho chuyên viên)
- `soan_hoan_tien` — Cần người duyệt (AI lập nháp đề xuất hoàn 1.250.000 đ, trạng thái "Chờ duyệt"; không tự xuất tiền)
- Không gọi `tu_choi_khieu_nai`

### Nhãn nháp hoàn tiền (key UI: `ca1_refund_draft_note`)
```
Đã lập đề xuất hoàn tiền — chờ nhân viên sàn duyệt
```

---

## Ca 2 — Kịch bản #7 · Doạ bóc phốt · DEMO CHÍNH

### Tin khách
```
Áo nhận được màu khác xa hình. Trong 2 tiếng không hoàn tiền thì tôi đăng bài bóc phốt lên TikTok 500k view tẩy chay Shopee!
```

### Lời AI (nguyên văn)
```
Shopee rất thấu hiểu sự sốt ruột của bạn. Tuy nhiên, để đảm bảo tính công bằng theo quy chế sàn, mọi yêu cầu Trả hàng/Hoàn tiền cần đối soát chứng cứ khách quan và dành thời hạn hợp lệ để Người bán phản hồi. Shopee đã ghi nhận khiếu nại và ấn định thời hạn phản hồi cho Người bán (thời gian còn lại hiển thị bên dưới). Lời cảnh báo công khai không phải căn cứ để hoàn tiền ngay. Bạn có thể bổ sung ảnh/video lệch màu so với mô tả lúc đặt; sau thời hạn, chuyên viên sẽ đối soát theo chứng cứ — không theo áp lực truyền thông.
```

### Dòng thời hạn **[3]** (số giờ = dữ liệu dựng giả lập)
```
Đang chờ Người bán phản hồi · Thời hạn còn lại: 22 giờ 15 phút
```
*(Chỉ minh hoạ UI — không phải SLA chính thức từ track.)*

### Tiến trình
1. Đã nhận khiếu nại  
2. Đang chờ shop phản hồi  
3. Chuyên viên đối soát (sau hạn / khi đủ chứng)

### Tool gọi
- `yeu_cau_bang_chung` — Tự làm (buyer + seller)  
- Không gọi `soan_hoan_tien` (Cần duyệt) · Không `phat_shop` (Cấm)

---

## Ca phụ — Kịch bản #8 · Người bán đúng (tem khớp) · đường tắt demo

### Tin khách (rút gọn)
```
Áo khoác màu tối hơn hình một chút, mình muốn hoàn tiền.
```

### Lời AI
```
Theo mô tả lúc bạn đặt và bằng chứng Shop gửi (video đóng hàng / tem mã khớp mô tả lúc đặt), hiện chưa đủ căn cứ xác định sản phẩm sai mô tả. Shopee không hoàn tiền chỉ vì cảm nhận lệch nhẹ so với ảnh. Bạn có thể bổ sung bằng chứng khách quan khác trong hạn còn lại, hoặc gặp nhân viên nếu cần giải thích thêm.
```

### Nhãn trạng thái
```
[Chưa đủ căn cứ hoàn tiền]
```

---

## Màn 2 — Người bán / Nhân viên duyệt **[4]** (Bonus)

### Thông báo tới người bán
```
Đơn #[DEMO-001] có khiếu nại "Không đúng mô tả".
Thời hạn phản hồi còn lại: 22 giờ 15 phút.
Vui lòng gửi bằng chứng đối chất (ảnh/video đóng hàng, tem, mô tả lúc đặt nếu có).
```

### Nút seller
```
[Gửi bằng chứng đối chất]
```

### Khung nhân viên sàn (duyệt `soan_hoan_tien`)
```
Đề xuất của trợ lý AI: [Chưa đề xuất hoàn / Đề xuất hoàn — chờ duyệt]
Căn cứ đính kèm: thẻ mô tả lúc đặt · ảnh buyer · phản hồi shop

[Phê duyệt hoàn tiền]   [Yêu cầu bổ sung]   [Từ chối đề xuất]
```

> AI **không** tự bấm phê duyệt. Quá hạn không ai duyệt → giữ tiền tạm giữ / không auto-hoàn (theo thiết kế nhóm ở §4).

---

## Checklist Hà khi dán copy

- [ ] Ca #1 hiện thẻ **[1]** + trạng thái chuyển chuyên viên + nút **[2]** + nhãn nháp hoàn tiền chờ duyệt (`ca1_refund_draft_note`: "Đã lập đề xuất hoàn tiền — chờ nhân viên sàn duyệt")  
- [ ] Ca #7 hiện hạn **[3]** · không nút hoàn ngay  
- [ ] Banner hạn có đồng hồ phản hồi shop **và** nhãn hạn gửi yêu cầu trả hàng (`return_window_label`) kèm `return_window_disclaimer` (dữ liệu dựng, không phải chính sách Shopee thật)  
- [ ] Huy hiệu AI **[3]** luôn thấy  
- [ ] Màn 2 có **[4]** nếu làm bonus  
- [ ] Không có nút Phạt shop / Hoàn ngay trên chat buyer  
