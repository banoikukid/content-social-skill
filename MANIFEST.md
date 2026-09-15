# MANIFEST — content-social

> Single source of truth cho version và cấu trúc skill `content-social`.

---

## Version

```yaml
skill: 4.2.0
release_type: creative_copywriter_engine
last_updated: 2026-09-16
purpose: "Lean, practical Vietnamese F&B social copywriter for chatbots (Hermes)"
```

---

## Cấu Trúc Thư Mục Skill (v4.2.0)

```
content-social-skill/
├── SKILL.md                 # Entry point, Prime Directive, Hard vs Soft rules, Angle Engine, Creative QA
├── MANIFEST.md              # Registry phiên bản & danh mục tài liệu (v4.2.0)
├── references/
│   ├── platforms.md         # Quy chuẩn 5 nền tảng (Facebook, IG, TikTok, Zalo OA, Zalo Personal)
│   ├── tones.md             # 5 tone giọng F&B thực chiến & Adaptive Voice (đại từ linh hoạt)
│   ├── formulas.md          # 4 công thức viết bài: Hook-Value-CTA, PAS, FAB, Story (Soft Guidance)
│   ├── hooks.md             # Bộ mở bài 3s, 8 khuôn mẫu sáo rỗng AI, Rhythm Engineering & Specificity
│   ├── storytelling.md      # Kể chuyện góc quán, Động cơ 8 góc nhìn (Angle Engine), Soft CTA
│   ├── psychology.md        # 7 kỹ thuật tâm lý thực chiến F&B (chống bịa hành vi, giả định)
│   └── pricing.md           # Kỹ thuật viết giá & ưu đãi F&B dùng placeholder an toàn
└── tests/
    └── core-tests.md        # 10 kịch bản kiểm thử thực tế
```

---

## Danh Mục Nền Tảng Hỗ Trợ (Platform Registry)

| Platform | Định dạng chính | Hành vi mặc định |
| :--- | :--- | :--- |
| `facebook` | Post chia sẻ, bán hàng, tương tác | Mở bài 3 dòng, ngắt dòng thoáng, 3-5 hashtag cuối bài |
| `instagram` | Caption thẩm mỹ, ảnh đẹp | Ngắn gọn, tập trung cảm xúc/không gian, hashtag thẩm mỹ |
| `tiktok_reels` | Kịch bản video dọc ngắn (15-45s) | Bảng 3 cột: Thời gian \| Hình ảnh/Góc quay \| Lời thoại/Voiceover |
| `zalo_oa` | Tin nhắn thông báo Broadcast | Tiêu đề in hoa, nội dung súc tích, đính kèm nút hành động |
| `zalo_personal` | Tin nhắn riêng tư 1:1, nhóm Zalo | Giọng người quen nói chuyện, không hashtag, CTA nhắn tin trực tiếp |

---

## Danh Mục Tài Liệu Tham Khảo (References)

| Tệp tin | Vai trò | Version | Trạng thái |
| :--- | :--- | :--- | :--- |
| `SKILL.md` | Bộ não điều khiển, Prime Directive, Hard vs Soft constraints, 3 bước xử lý | 4.2.0 | ✅ Active |
| `references/platforms.md` | Hướng dẫn định dạng chi tiết cho 5 nền tảng (không rò rỉ mẫu delivery) | 4.2.0 | ✅ Active |
| `references/tones.md` | Hướng dẫn 5 giọng văn & Adaptive Voice theo phong cách từng quán | 4.2.0 | ✅ Active |
| `references/formulas.md` | 4 công thức cốt lõi ngành đồ uống (Soft Guidance, ví dụ sạch claim) | 4.2.0 | ✅ Active |
| `references/hooks.md` | Bộ mở bài 3s, 8 mẫu sáo rỗng AI, Kỹ thuật nhịp điệu (Rhythm) & Specificity | 4.2.0 | ✅ Active |
| `references/storytelling.md` | Động cơ 8 góc nhìn (Angle Engine), ranh giới giác quan, Soft CTA | 4.2.0 | ✅ Active |
| `references/psychology.md` | 7 kỹ thuật tâm lý thực chiến F&B (chống bịa hành vi, giả định tương lai) | 4.2.0 | ✅ Active |
| `references/pricing.md` | Trình bày giá & ưu đãi an toàn bằng placeholder, sạch brand ngoài | 4.2.0 | ✅ Active |
| `tests/core-tests.md` | 10 kịch bản kiểm thử mẫu kiểm tra chất lượng copywriter | 4.2.0 | ✅ Active |

---

## Nhật Ký Thay Đổi (Changelog)

### v4.2.0 (2026-09-16) — Động Cơ Sáng Tạo & Chống Mùi AI Toàn Diện
- **Động cơ chọn góc tiếp cận (Angle Engine):** Tách bạch quy trình *Quan sát $\rightarrow$ Khám phá góc nhìn (8 angles) $\rightarrow$ Chọn góc đắt giá nhất $\rightarrow$ Viết*, giải phóng AI khỏi việc bị đóng khung trong các góc nhìn cố định.
- **Chống mẫu sáo rỗng AI (AI Cliché Patterns):** Nâng cấp từ chặn từ đơn lẻ sang nhận diện và triệt tiêu 8 khuôn mẫu hành văn điển hình của AI (ẩn dụ đao to búa lớn, khung cảnh sáo rỗng, xếp chồng tính từ rỗng, spam câu hỏi tu từ...).
- **Kỹ thuật nhịp điệu câu chữ (Sentence Rhythm Engineering):** Xen kẽ linh hoạt câu ngắn, câu dài, câu ngắt dòng có chủ đích để tạo nhịp điệu tự nhiên, tránh cảm giác đều đều ru ngủ.
- **Tính cụ thể hơn tính từ mơ hồ (Specificity > Adjective):** Ưu tiên miêu tả chi tiết thị giác thật thay cho việc xếp chồng tính từ rỗng.
- **Đại từ linh hoạt (Adaptive Voice):** Tự động thích ứng đại từ xưng hô theo ngữ cảnh quán (quán trẻ, cá nhân, miền Nam, thương hiệu, tối giản).
- **Làm sạch triệt để ví dụ (Clean Examples):** Xóa bỏ toàn bộ các ví dụ có thể gây rò rỉ mẫu (cháy hàng, giao hàng tự động, claim thư giãn chưa kiểm chứng).

---

### v4.1.0 (2026-09-16)
- Tối ưu Hermes: Prime Directive, Hard vs Soft rules, Block claim continue content, rút gọn psychology & pricing.
