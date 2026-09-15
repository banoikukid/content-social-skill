# Platform Format Guide

> Version: 3.1.0 | Last updated: 2026-09-15
> Labels: `[RECOMMENDED FORMAT]` = best practice; `[API LIMIT]` = hard limit từ platform API

## Facebook Fanpage

**Đặc thù:**
- Text bị cắt sau ~3 dòng → "Xem thêm" — hook phải nằm trong 3 dòng đầu `[RECOMMENDED FORMAT]`
- Dài được, nhưng mỗi đoạn ≤3 dòng, xuống hàng giữa các ý
- Emoji: dùng vừa phải, không nhét đầu mỗi dòng
- CTA cuối: 1 câu hỏi hoặc 1 hành động (comment, tag bạn, ghé quán)

**Format mẫu:**
```
[Hook — 1-2 câu, tự đứng được]

[Thân — thông tin chính, 2-4 đoạn ngắn]

[CTA — 1 câu]
```

---

## TikTok / Reels (Script)

**Đặc thù:**
- Không phải caption — là script nói hoặc text overlay
- 3 giây đầu quyết định người xem có scroll không
- Nhịp nhanh, câu ngắn, mỗi câu = 1 ý
- Không cần giải thích dài — show, don't tell

**Format mẫu:**
```
[0-3s: Hook] — câu/hình ảnh gây dừng scroll
[3-12s: Body] — 3-5 câu, mỗi câu 1 ý
[12s+: CTA] — 1 hành động rõ ràng
```

**Ví dụ structure:**
```
Hook: "Cái này tôi order 3 lần trong 1 tuần."
Body: Tên món. Giá. Lý do cụ thể. Điểm khác biệt.
CTA: "Địa chỉ trong bio." hoặc "Comment 'menu' nhận ngay."
```

---

## Zalo OA (Official Account — Broadcast)

**Đặc thù:**
- Đọc trên mobile, trong notification → câu đầu = subject line
- Ngắn hơn Facebook: không quá 150 từ cho broadcast `[RECOMMENDED FORMAT]`
- Tone thân mật, như nhắn tin cho khách quen
- Không dùng hashtag
- CTA phải có link hoặc số điện thoại nếu cần đặt hàng

**Format mẫu:**
```
[Câu mở — thân, ngắn, như nhắn bạn]
[1-2 câu thông tin chính]
[CTA + link/SĐT nếu có]
```

---

## Zalo Personal (DM / Nhóm)

> Dùng khi Hermes gửi qua Zalo cá nhân (`zca-js` connector), không phải OA broadcast.
> Formatting rules khác OA — không áp dụng OA rules cho channel này.

**Đặc thù:**
- Ngữ cảnh: nhắn tin 1-1 hoặc nhóm chat thân thiện
- Ngắn gọn, tự nhiên hơn OA — viết như nhắn tin thật
- Không cần CTA có link nếu người nhận đã biết đặt hàng
- Emoji được dùng tự nhiên (1-3 cái)
- Không broadcast format — không cần subject line

**Format mẫu:**
```
[1-2 câu thông tin chính — thân mật]
[CTA nhẹ hoặc câu hỏi]
```

**Ví dụ (Cherry DM):**
```
🍵 Trà đào hôm nay 39k nha.
Muốn lấy 2 ly thì nhắn mình.
```

---

## Instagram (Feed & Stories)

**Đặc thù:**
- **Feed:** Ưu tiên phần nhìn (Visual-First). Caption trên Instagram rất ít khi được đọc hết trừ khi cực kỳ lôi cuốn trong 1-2 câu đầu. Hook ngắn gọn, trực diện, kích thích người xem trượt sang ảnh tiếp theo (carousel) hoặc nhấp vào link bio.
- **Stories:** Tương tác nhanh, vòng đời ngắn (24h). Ngôn ngữ cực kỳ ngắn gọn, thân mật (Tone 1), thường đi kèm sticker câu hỏi, poll bình chọn, hoặc liên kết "Swipe Up" / Sticker link mua hàng.
- Sử dụng hashtag có chọn lọc, tập trung vào tên món, địa điểm và tên thương hiệu ở cuối bài (tối đa 5-8 hashtag, không spam). `[RECOMMENDED FORMAT]`

> ⚠️ Instagram chưa có trong metadata SKILL.md. Nếu dùng Instagram, cập nhật `brand-profile.md` platforms list.

**Format mẫu (Instagram Feed):**
```
[Hook ngắn — ≤ 2 câu cực kỳ bắt mắt hoặc đánh trúng cảm quan]

[Thân — 1-2 đoạn cực ngắn mô tả cảm quan/giá trị hoặc ưu đãi]

[CTA ngắn — Kêu gọi hành động như click link bio, comment nhận menu]

#hashtag1 #hashtag2 #tearus...
```
