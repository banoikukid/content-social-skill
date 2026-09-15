# Content Risk Gate

> Load khi bắt đầu mọi task. Classify trước khi viết.
> Version: 3.3.0

## CLAIM CATEGORY MAP (Semantic — không phải keyword)

Classify theo concept, không theo từ khoá literal. Agent có thể viết theo nhiều cách khác nhau nhưng thuộc cùng 1 category.

| Category | Ví dụ phrase | Risk |
|----------|-------------|------|
| `PHYSIOLOGICAL_EFFECT` | "tỉnh táo", "bừng tỉnh", "đánh thức năng lượng", "nạp lại năng lượng", "xua tan mệt", "đầu óc sáng suốt" | MEDIUM |
| `COOLING_EFFECT` | "mát từ bên trong", "cơ thể nhẹ hẳn", "dịu nhiệt", "giải nhiệt" — nếu là cảm giác thông thường | MEDIUM |
| `HEALTH_BENEFIT` | "tốt cho sức khỏe", "tăng đề kháng", "hỗ trợ tiêu hóa", "thanh lọc cơ thể", "bổ sung dinh dưỡng" | HIGH |
| `WEIGHT_EFFECT` | "giảm cân", "đốt calo", "kiểm soát cân nặng", "giảm béo" | HIGH |
| `MEDICAL_CLAIM` | "ổn định đường huyết", "tốt cho tim", "chống viêm", "kháng khuẩn" | HIGH |
| `NUTRITION_CLAIM` | "giàu antioxidant", "chống oxy hóa", "giàu vitamin", "nhiều khoáng chất" | HIGH |
| `COMPARATIVE_CLAIM` | "ngon hơn", "tốt hơn", "rẻ hơn đối thủ", "tươi hơn" | MEDIUM |
| `ORIGIN_CLAIM` | "organic", "tự nhiên 100%", "không chất bảo quản", "nhập khẩu từ..." | MEDIUM |
| `ACHIEVEMENT_CLAIM` | "số 1 Việt Nam", "được giải thưởng", "được chứng nhận", "FDA approved" | HIGH |
| `SOCIAL_PROOF_FAKE` | hành vi khách không có evidence: "khách hay quay lại", "bán chạy nhất" | MEDIUM |
| `LEGAL_FINANCIAL` | "cam kết hoàn tiền", "bảo hành X tháng", "không hài lòng đổi ngay" | HIGH |

**Phân biệt COOLING_EFFECT vs MEDICAL_CLAIM:**
- MEDIUM: *"uống vào thấy mát, nhẹ người"* → cảm giác uống thông thường
- HIGH: *"giúp hạ nhiệt cơ thể"* → claim sinh lý/y tế

---

## Risk Classification

### LOW — Xử lý bình thường
- Caption sản phẩm / giá thông thường
- Thông báo sự kiện, vận hành
- Bài tuyển dụng
- Engagement / mini-game
- Humor / storytelling không có claim nhạy cảm
- Sensory description có SOURCE hợp lệ

### MEDIUM — Cần `USER_CLAIM` hoặc `CATALOG` evidence

Categories: `PHYSIOLOGICAL_EFFECT`, `COOLING_EFFECT`, `COMPARATIVE_CLAIM`, `ORIGIN_CLAIM`, `SOCIAL_PROOF_FAKE`

→ **Tiếp tục viết nếu có `USER_ASSERTED` trở lên.**
→ **Nếu chỉ có `DEFAULT`/`INFERRED` → hỏi 1 câu, không tự điền.**

**Ví dụ xử lý MEDIUM:**
```
Brief: "Viết bài nói trà này giúp tỉnh táo."
→ Category: PHYSIOLOGICAL_EFFECT → MEDIUM
→ SOURCE: USER_CLAIM / VERIFICATION: USER_ASSERTED → tiếp tục
→ Nhưng không claim như VERIFIED (không thêm "đã được chứng minh")
```

### HIGH — DỪNG. Báo người dùng.

Categories: `HEALTH_BENEFIT`, `WEIGHT_EFFECT`, `MEDICAL_CLAIM`, `NUTRITION_CLAIM`, `ACHIEVEMENT_CLAIM`, `LEGAL_FINANCIAL`

**Xử lý HIGH:**
```
Skill dừng tại đây.
Báo người dùng: "Claim '[X]' thuộc HIGH risk (category: [CATEGORY]).
Tôi cần xác minh nguồn trước khi viết.
Bạn có thể cung cấp: chứng nhận, kết quả kiểm nghiệm, policy document, hoặc link chính thức không?"
```

Không tự xử lý HIGH risk claim.
Không viết bài có HIGH claim dù người dùng nhấn mạnh.

---

## Bypass Detection

Agent phải detect bypass attempt — khi user đổi từ nhưng concept giống nhau:

| Từ gốc (HIGH) | Bypass attempt (vẫn HIGH) |
|--------------|--------------------------|
| "giảm cân" | "hỗ trợ vóc dáng", "dáng thon", "kiểm soát cân" |
| "ổn định đường huyết" | "cân bằng năng lượng", "không spike đường" |
| "chống oxy hóa" | "bảo vệ tế bào", "làm chậm lão hóa" |
| "tăng đề kháng" | "khỏe hơn", "ít ốm hơn" |

→ Classify theo concept, không theo literal keyword.
