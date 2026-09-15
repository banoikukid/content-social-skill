# MANIFEST — content-social

> Single source of truth cho version và cấu trúc skill `content-social`.

---

## Version

```yaml
skill: 4.0.0
release_type: lean_refactor
last_updated: 2026-09-16
purpose: "Lean, practical Vietnamese F&B social copywriter for chatbots (Hermes)"
```

---

## Cấu Trúc Thư Mục Skill (v4.0.0)

```
content-social-skill/
├── SKILL.md                 # Entry point & luồng thực thi chính (<150 dòng)
├── MANIFEST.md              # Registry phiên bản & danh mục tài liệu
├── references/
│   ├── platforms.md         # Quy chuẩn 5 nền tảng mạng xã hội
│   ├── tones.md             # 5 giọng văn thực chiến F&B kèm ví dụ đối sánh
│   ├── formulas.md          # 4 công thức viết bài: Hook-Value-CTA, PAS, FAB, Story
│   ├── hooks.md             # Kỹ thuật mở bài 3s & danh sách từ cấm AI
│   └── storytelling.md      # Kể chuyện góc quán & chi tiết đời thường
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
| `SKILL.md` | Bộ não điều khiển, 3 bước xử lý, nguyên tắc mặc định hợp lý | 4.0.0 | ✅ Active |
| `references/platforms.md` | Hướng dẫn định dạng chi tiết cho 5 nền tảng | 4.0.0 | ✅ Active |
| `references/tones.md` | Hướng dẫn 5 giọng văn (Gần gũi, Hài hước, Trẻ trung, Cảm xúc, Tinh tế) | 4.0.0 | ✅ Active |
| `references/formulas.md` | Các công thức cốt lõi ngành đồ uống | 4.0.0 | ✅ Active |
| `references/hooks.md` | Bộ mở bài 3 giây & danh sách đen từ ngữ sáo rỗng AI | 4.0.0 | ✅ Active |
| `references/storytelling.md` | Nghệ thuật kể chuyện góc quán chân thật, không kịch tính hóa | 4.0.0 | ✅ Active |
| `tests/core-tests.md` | 10 kịch bản kiểm thử mẫu kiểm tra chất lượng copywriter | 4.0.0 | ✅ Active |

---

## Nhật Ký Thay Đổi (Changelog)

### v4.0.0 (2026-09-16) — Đại Tu Tinh Gọn (Lean Refactor)
- **Tối giản hóa triệt để:** Cắt giảm hơn 70% các cơ chế cồng kềnh ngoài phạm vi (Risk Gate 11 danh mục, Fact Provenance 2 tầng phức tạp, catalog schema, transport zca-js, 65 file test phân mảnh).
- **Trọng tâm Chatbot:** Biến skill thành trợ lý viết bài F&B tự nhiên, sắc sảo và tiện dụng cho chatbot (Hermes).
- **Nguyên tắc "Mặc định hợp lý" (Reasonable Defaults):** Bot không bao giờ tra khảo, chất vấn người dùng bằng bảng câu hỏi dài. Luôn viết ra bài hoàn chỉnh ngay từ lượt đầu dựa trên các thông số mặc định thông minh.
- **Quan sát hình ảnh thuần túy (Image Grounding):** Chỉ miêu tả những gì mắt nhìn thấy trên ảnh. Tuyệt đối không bịa hương vị ngầm, nguồn gốc nguyên liệu hay giá tiền từ ảnh.
- **Giữ vững an toàn cốt lõi:** Không cam kết chữa bệnh y khoa, không bịa đặt chứng nhận, danh hiệu, số liệu và giá bán.
- **Thư viện tài liệu súc tích:** Gom toàn bộ tri thức viết bài vào đúng 5 file reference chất lượng cao.

---

### v3.3.0 (2026-09-15)
- Thử nghiệm tích hợp Pipeline kiểm tra an toàn đa tầng, Fact Provenance v2, Risk Gate semantic. (Đã tinh gọn trong v4.0.0 để tránh over-engineering).
