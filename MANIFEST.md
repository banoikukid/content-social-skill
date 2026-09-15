# MANIFEST — content-social

> Single source of truth cho version và cấu trúc skill `content-social`.

---

## Version

```yaml
skill: 4.3.0
release_type: insight_engine_and_clean_examples
last_updated: 2026-09-16
purpose: "Lean, practical Vietnamese F&B social copywriter for chatbots (Hermes)"
```

---

## Cấu Trúc Thư Mục Skill (v4.3.0)

```
content-social-skill/
├── README.md                # Giới thiệu tổng quan & hướng dẫn tích hợp Hermes
├── SKILL.md                 # Entry point, Prime Directive, Insight Engine, Creative QA (v4.3.0)
├── MANIFEST.md              # Registry phiên bản & danh mục tài liệu (v4.3.0)
├── references/
│   ├── platforms.md         # Quy chuẩn 5 nền tảng (Facebook, IG, TikTok, Zalo OA, Zalo Personal, User overrides)
│   ├── tones.md             # 5 tone giọng F&B, Ma trận thông số Tone (Parameters) & Adaptive Voice
│   ├── formulas.md          # 4 công thức cốt lõi (Soft Guidance, FAB fact-based, sạch địa chỉ & claim)
│   ├── hooks.md             # Mở bài 3s, 8 khuôn mẫu AI, Rhythm Engineering & Specificity (sạch claim)
│   ├── storytelling.md      # Động cơ 8 góc nhìn (Angle Engine), 3 tầng dữ liệu, Ma trận kỹ thuật, Soft CTA
│   ├── psychology.md        # 7 kỹ thuật tâm lý thực chiến F&B (chống bịa hành vi, giả định tương lai)
│   └── pricing.md           # Kỹ thuật viết giá & ưu đãi an toàn bằng placeholder
└── tests/
    └── core-tests.md        # 10 kịch bản kiểm thử thực tế
```

---

## Danh Mục Nền Tảng Hỗ Trợ (Platform Registry)

| Platform | Định dạng chính | Hành vi mặc định |
| :--- | :--- | :--- |
| `facebook` | Post chia sẻ, bán hàng, tương tác | Mở bài 3 dòng, ngắt dòng thoáng, hashtag tùy chọn |
| `instagram` | Caption thẩm mỹ, ảnh đẹp | Ngắn gọn, tập trung cảm xúc/không gian, hashtag thẩm mỹ |
| `tiktok_reels` | Kịch bản video dọc ngắn (15-45s) | Bảng 3 cột: Thời gian \| Hình ảnh/Góc quay \| Lời thoại/Voiceover |
| `zalo_oa` | Tin nhắn thông báo Broadcast | Tiêu đề in hoa, nội dung súc tích, đính kèm nút hành động |
| `zalo_personal` | Tin nhắn riêng tư 1:1, nhóm Zalo | Giọng người quen nói chuyện, không hashtag, CTA nhắn tin trực tiếp |

---

## Danh Mục Tài Liệu Tham Khảo (References)

| Tệp tin | Vai trò | Version | Trạng thái |
| :--- | :--- | :--- | :--- |
| `README.md` | Tài liệu giới thiệu tổng quan dự án | 4.3.0 | ✅ Active |
| `SKILL.md` | Bộ não điều khiển, Prime Directive, Insight Engine, 8-question Creative QA | 4.3.0 | ✅ Active |
| `references/platforms.md` | Hướng dẫn định dạng 5 nền tảng, nguyên tắc user request overrides default | 4.3.0 | ✅ Active |
| `references/tones.md` | 5 tone giọng F&B, Ma trận thông số Tone & Adaptive Voice | 4.3.0 | ✅ Active |
| `references/formulas.md` | 4 công thức cốt lõi, quy tắc fact-based FAB, sạch địa chỉ & claim | 4.3.0 | ✅ Active |
| `references/hooks.md` | Mở bài 3s, 8 khuôn mẫu AI, Kỹ thuật nhịp điệu (Rhythm) & Specificity | 4.3.0 | ✅ Active |
| `references/storytelling.md` | Động cơ 8 góc nhìn, phân định 3 tầng dữ liệu (Observed/Provided/Creative), Soft CTA | 4.3.0 | ✅ Active |
| `references/psychology.md` | 7 kỹ thuật tâm lý thực chiến F&B (chống bịa hành vi, giả định tương lai) | 4.3.0 | ✅ Active |
| `references/pricing.md` | Trình bày giá & ưu đãi an toàn bằng placeholder, sạch brand ngoài | 4.3.0 | ✅ Active |
| `tests/core-tests.md` | 10 kịch bản kiểm thử mẫu kiểm tra chất lượng copywriter | 4.3.0 | ✅ Active |

---

## Nhật Ký Thay Đổi (Changelog)

### v4.3.0 (2026-09-16) — Động Cơ Insight & Làm Sạch Triệt Để Ví Dụ
- **Động cơ Insight (Insight Engine):** Quan sát $\rightarrow$ Tìm chi tiết thú vị $\rightarrow$ Insight người đọc (khi có ích) $\rightarrow$ Chọn góc $\rightarrow$ Viết.
- **Làm sạch 100% ví dụ (Zero Fabricated Claims in Examples):** Xóa bỏ toàn bộ các claim ngầm trong ví dụ (`hooks.md`, `formulas.md`, `storytelling.md`, `tones.md`).
- **Phân định 3 tầng dữ liệu trong Kể chuyện:** `OBSERVED` (thị giác thấy trong ảnh), `PROVIDED` (user/menu cung cấp), `CREATIVE` (mood/ẩn dụ cảm xúc).
- **Ma trận thông số Tone (Tone Parameters Matrix):** Quy chuẩn ảnh hưởng của Tone lên nhịp điệu, độ dài câu, mức trực diện, emoji density, CTA style.
- **Quyền lực tối thượng của người dùng:** Yêu cầu rõ ràng từ người dùng luôn ghi đè quy cách mặc định của nền tảng.
- **Định nghĩa lại CTA:** Bắt buộc 1 hành động tiếp theo tự nhiên (1 clear next action) cho bài bán hàng; tùy chọn/kết mở cho bài kể chuyện.

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
