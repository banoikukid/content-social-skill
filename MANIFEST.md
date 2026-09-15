# MANIFEST — content-social

> Single source of truth cho version và cấu trúc skill `content-social`.

---

## Version

```yaml
skill: 4.5.0
release_type: pristine_craft_edition
last_updated: 2026-09-16
purpose: "Lean, practical Vietnamese F&B social copywriter for chatbots (Hermes)"
```

---

## Cấu Trúc Thư Mục Skill (v4.5.0)

```
content-social-skill/
├── README.md                # Giới thiệu tổng quan & hướng dẫn tích hợp Hermes (v4.5.0)
├── SKILL.md                 # Entry point, Prime Directive, Observation > Insight, 10-point DoD QA (v4.5.0)
├── MANIFEST.md              # Registry phiên bản & danh mục tài liệu (v4.5.0)
├── references/
│   ├── platforms.md         # Quy chuẩn 5 nền tảng (Facebook, IG, TikTok, Zalo OA, Zalo Personal, Soft tendencies)
│   ├── tones.md             # 5 tone giọng F&B, Ma trận thông số Tone & Emoji Density Tendency (sạch claim)
│   ├── formulas.md          # 4 công thức cốt lõi (Hook-Value-CTA, PAS, FAB, Storytelling sạch claim)
│   ├── hooks.md             # Mở bài 3s, 8 khuôn mẫu AI, Rhythm Engineering & Promise-Payoff (sạch claim)
│   ├── storytelling.md      # Động cơ 8 góc nhìn (Angle Engine), 3 tầng dữ liệu, Ma trận kỹ thuật, Soft CTA
│   ├── psychology.md        # 7 kỹ thuật tâm lý thực chiến F&B (chống bịa hành vi, giả định tương lai)
│   ├── pricing.md           # Kỹ thuật viết giá & ưu đãi an toàn bằng placeholder (sạch delivery claim)
│   └── examples.md          # 28+ bài viết mẫu chuẩn mực (Image/Brief to Caption, Rewrite, Bad vs Good)
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
| `README.md` | Tài liệu giới thiệu tổng quan dự án | 4.5.0 | ✅ Active |
| `SKILL.md` | Bộ não điều khiển, Prime Directive, Observation > Insight, 10 DoD checks | 4.5.0 | ✅ Active |
| `references/platforms.md` | Hướng dẫn định dạng 5 nền tảng, xu hướng mềm, user overrides | 4.5.0 | ✅ Active |
| `references/tones.md` | 5 tone giọng F&B, Ma trận thông số Tone & Emoji density tendencies | 4.5.0 | ✅ Active |
| `references/formulas.md` | 4 công thức cốt lõi, quy tắc fact-based FAB, sạch địa chỉ & claim | 4.5.0 | ✅ Active |
| `references/hooks.md` | Mở bài 3s, 8 khuôn mẫu AI, Rhythm & Promise-Payoff (sạch claim) | 4.5.0 | ✅ Active |
| `references/storytelling.md` | Động cơ 8 góc nhìn, 3 tầng dữ liệu, sạch operational claims | 4.5.0 | ✅ Active |
| `references/psychology.md` | 7 kỹ thuật tâm lý thực chiến F&B (chống bịa hành vi) | 4.5.0 | ✅ Active |
| `references/pricing.md` | Trình bày giá & ưu đãi an toàn, sạch delivery claim | 4.5.0 | ✅ Active |
| `references/examples.md` | Tuyển tập 28+ bài mẫu F&B chuẩn (Image/Brief, Rewrite, Bad vs Good) | 4.5.0 | ✅ Active |
| `tests/core-tests.md` | 10 kịch bản kiểm thử mẫu kiểm tra chất lượng copywriter | 4.5.0 | ✅ Active |

---

## Nhật Ký Thay Đổi (Changelog)

### v4.5.0 (2026-09-16) — The Pristine Craft Edition (Zero Hallucination Examples & Claim Check)
- **Observation > Insight (Insight là tùy chọn):** Thay đổi quy trình tư duy `Observation → Detail → Insight (optional) → Dominant Idea`. Ưu tiên chi tiết quan sát thật, loại bỏ việc ép AI tự vẽ ra insight sáo rỗng.
- **Tích hợp Claim Check vào QA 10 điểm (10 Silent DoD Checks):** Kiểm tra thầm: *Mỗi câu factual/vật lý có nguồn từ input đã xác nhận không?* Triệt tiêu toàn bộ claim bán chạy, công thức ngầm, hiệu ứng thể chất.
- **Thanh lọc 100% ví dụ tham khảo (Clean Reference Traps):**
  - `hooks.md`: Xóa claim hiệu ứng cơ thể ("mát lạnh", "nhẹ cả người", "tỉnh cả người") và operational fact ("tự ủ mẻ trà").
  - `formulas.md`: Xóa claim thể chất ("nạp lại năng lượng", "sốc lại tinh thần", "sảng khoái hẳn ra").
  - `storytelling.md`: Sạch operational claims và chỉ khai thác Craft khi có xác nhận từ quán.
  - `tones.md`: Bỏ hẳn quota số lượng emoji, chuyển 100% sang Emoji Density Tendency (`Low`, `Moderate`, `High`).
  - `pricing.md`: Xóa claim dịch vụ ship khi chưa có dữ kiện ("ship tận bàn làm việc").
  - `platforms.md`: Chuyển định mức emoji/hashtag sang soft tendencies.
- **Bổ sung `references/examples.md`:** 28+ kịch bản mẫu chuẩn mực F&B (5 Image $\rightarrow$ Caption, 5 Brief $\rightarrow$ Caption, 3 Rewrite, 3 Humor, 3 Storytelling, 3 Zalo Personal, 3 Promotions, 3 Cặp Bad vs Good).

---

### v4.4.0 (2026-09-16) — Master Copywriter Edition (Benchmark Global Skills)
- **4 Trụ Cột Sáng Tác (Golden Craft Principles):**
  1. *Một ý tưởng chủ đạo (One Dominant Idea):* 1 bài viết = 1 thông điệp trọng tâm, không nhồi nhét.
  2. *Caption ≠ Mô tả ảnh (Image as Springboard):* Dùng ảnh làm chất xúc tác/bằng chứng cho một ý tưởng hay khoảnh khắc.
  3. *Lời hứa & Lời giải (Hook $\rightarrow$ Promise $\rightarrow$ Payoff):* Hook hứa điều gì, thân bài phải giải quyết trọn vẹn điều đó; cấm clickbait vượt quá nội dung.
  4. *Tư duy tiếng Việt thuần thục (Native Vietnamese Craft):* Viết thẳng bằng tư duy đời thường người Việt, không dịch cấu trúc câu tiếng Anh.
- **Phân biệt Voice vs Tone:** Voice (Bản sắc thương hiệu cốt lõi không đổi) vs Tone (Tâm trạng linh hoạt theo từng bài viết).
- **Kỹ thuật ngầm chọn Hook (Internal 3-Hook Candidates):** Ngầm phác thảo 3 hướng mở bài và chọn hướng ăn nhập nhất với ý tưởng chủ đạo.
- **Tiêu chuẩn xuất bản hoàn hảo (Definition of Done QA):** Nâng cấp bộ kiểm định sáng tạo 8 điểm kiểm tra thầm nội bộ.

---

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
