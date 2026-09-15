# MANIFEST — content-social

> Single source of truth cho version và cấu trúc skill `content-social`.

---

## Version

```yaml
skill: 4.1.0
release_type: hermes_optimized
last_updated: 2026-09-16
purpose: "Lean, practical Vietnamese F&B social copywriter for chatbots (Hermes)"
```

---

## Cấu Trúc Thư Mục Skill (v4.1.0)

```
content-social-skill/
├── SKILL.md                 # Entry point & luồng thực thi 3 bước (có Prime Directive & Hard vs Soft rules)
├── MANIFEST.md              # Registry phiên bản & danh mục tài liệu
├── references/
│   ├── platforms.md         # Quy chuẩn 5 nền tảng mạng xã hội (FB, IG, TikTok, Zalo OA, Zalo Personal)
│   ├── tones.md             # 5 giọng văn thực chiến F&B kèm ví dụ đối sánh
│   ├── formulas.md          # 4 công thức viết bài: Hook-Value-CTA, PAS, FAB, Story (Soft Guidance)
│   ├── hooks.md             # Kỹ thuật mở bài 3s & danh sách từ cấm AI
│   ├── storytelling.md      # Kể chuyện góc quán, 4 góc nhìn hình ảnh, quy tắc Soft CTA
│   ├── psychology.md        # 7 kỹ thuật tâm lý thực chiến F&B (không lý thuyết NLP rườm rà)
│   └── pricing.md           # Kỹ thuật trình bày giá & ưu đãi F&B dùng placeholder an toàn
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
| `SKILL.md` | Bộ não điều khiển, Prime Directive, Hard vs Soft constraints, 3 bước xử lý | 4.1.0 | ✅ Active |
| `references/platforms.md` | Hướng dẫn định dạng chi tiết cho 5 nền tảng | 4.1.0 | ✅ Active |
| `references/tones.md` | Hướng dẫn 5 giọng văn (Gần gũi, Hài hước, Trẻ trung, Cảm xúc, Tinh tế) | 4.1.0 | ✅ Active |
| `references/formulas.md` | 4 công thức cốt lõi ngành đồ uống (Soft Guidance) | 4.1.0 | ✅ Active |
| `references/hooks.md` | Bộ mở bài 3 giây & danh sách đen từ ngữ sáo rỗng AI | 4.1.0 | ✅ Active |
| `references/storytelling.md` | Nghệ thuật kể chuyện, 4 góc nhìn hình ảnh, Soft CTA | 4.1.0 | ✅ Active |
| `references/psychology.md` | 7 kỹ thuật tâm lý thực chiến F&B (chống bịa hành vi, giả định tương lai) | 4.1.0 | ✅ Active |
| `references/pricing.md` | Trình bày giá & ưu đãi an toàn bằng placeholder | 4.1.0 | ✅ Active |
| `tests/core-tests.md` | 10 kịch bản kiểm thử mẫu kiểm tra chất lượng copywriter | 4.1.0 | ✅ Active |

---

## Nhật Ký Thay Đổi (Changelog)

### v4.1.0 (2026-09-16) — Tối Ưu Hermes & Tiếp Thu Audit
- **Nguyên tắc tối cao (The Prime Directive):** Đặt chất lượng nội dung và sự tự nhiên của tiếng Việt lên trên việc bám chấp vào khuôn mẫu/template.
- **Phân định rõ ràng Hard vs Soft Rules:** Hard = Không bịa đặt (giá, y khoa, thành phần), đúng brief, tôn trọng nền tảng; Soft = Công thức, mở bài, số emoji, nhịp điệu.
- **CTA linh hoạt:** Bắt buộc cho bài Bán hàng/Khuyến mãi/Tuyển dụng; Tùy chọn (Soft/Optional) cho Storytelling, Brand, Humor để tránh phá nát cảm xúc.
- **Khai thác hình ảnh đa góc độ:** Bổ sung 4 góc nhìn (Sản phẩm, Không gian, Đời thường, Tối giản), loại bỏ hoàn toàn việc ép ảnh vào cliché *"trốn deadline / chữa lành"*.
- **Tái tích hợp `psychology.md` & `pricing.md` tinh gọn:** 
  - `psychology.md`: Rút từ 18 hiệu ứng NLP xuống đúng 7 kỹ thuật F&B thực chiến. Sửa dứt điểm lỗi tự bịa hành vi khách hàng. Future Pacing bắt buộc dùng câu giả định.
  - `pricing.md`: Hướng dẫn viết giá/deal dùng placeholder chuẩn, không rò rỉ thương hiệu bên ngoài.

---

### v4.0.0 (2026-09-16)
- Đại tu tinh gọn, loại bỏ >70% compliance machinery và gom tests.
