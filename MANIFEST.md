# MANIFEST — content-social

> Single source of truth cho version và cấu trúc skill.

## Version

```
skill:        3.1.0
last_updated: 2026-09-15
```

## Reference Files

| File | Mô tả | Version |
|------|-------|---------|
| `SKILL.md` | Entry point, luồng bắt buộc, guardrails | 3.1.0 |
| `references/workflow.md` | Intent detection, flows A–G, inline rules | 3.1.0 |
| `references/voice.md` | 7 tone giọng văn | 3.1.0 |
| `references/checks.md` | Post-write checklist | 3.1.0 |
| `references/platforms.md` | Facebook, TikTok, Zalo OA, Zalo Personal, Instagram | 3.1.0 |
| `references/formulas.md` | Copywriting formulas (AIDA, PAS, FAB...) | 3.0.0 |
| `references/psychology.md` | 18 hiệu ứng tâm lý + NLP + Ethics Gate | 3.1.0 |
| `references/pricing.md` | Quy tắc viết bài có giá | 3.0.0 |
| `references/hooks-conclusions.md` | Mở bài và kết bài | 3.0.0 |
| `references/colloquial-voice.md` | Văn nói tự nhiên | 3.0.0 |
| `references/conflict-storytelling.md` | Kỹ thuật xung đột cho Brand/Story | 3.0.0 |
| `references/feedback-storytelling.md` | Kỹ thuật feedback/review storytelling | 3.0.0 |
| `references/security.md` | Prompt injection defense | 3.1.0 |
| `references/risk-gate.md` | Content risk classification | 3.1.0 |
| `references/brand-profile.md` | Brand profile template | 3.1.0 |

## Changelog

### v3.1.0 (2026-09-15)
**P0 Fixes:**
- Đồng bộ version: `workflow.md` từ `v2.9 Stable` → `v3.1.0`, `voice.md` từ "6 Tone" → "7 Tone"
- Sửa mâu thuẫn Mind Map: Bước 1.5 không còn yêu cầu xuất mind map, chỉ chạy thầm
- Thêm Fact Provenance System: [USER], [IMAGE], [CATALOG], [BRAND], [INFERRED], [DEFAULT]
- Đổi DEFAULT VOCABULARY → SAFE GENERIC VOCABULARY với ràng buộc rõ ràng
- Fix Specificity Fallback loophole: không được dùng hành vi khách chưa có evidence
- Fix Brand Safety: phân biệt material defect vs storytelling heritage detail
- Thêm Prompt Injection Defense (references/security.md)

**P1 Improvements:**
- Thêm Ethical Persuasion Gate vào psychology.md
- Thêm Content Risk Classification (references/risk-gate.md)
- Thêm Zalo Personal section vào platforms.md + versioned labels
- Tạo Brand Profile template (references/brand-profile.md)
- Tạo evaluation suite skeleton (tests/)

### v3.0.0 (trước 2026-09-15)
- Nền tảng ban đầu: 7 flows, 7 tones, formulas, psychology
- Guardrails chống hallucination cơ bản

### v2.9 (legacy)
- Phiên bản TEARUS CONTENT AGENT gốc

## Architecture Note (Hermes Target)

```
HERMES
  │
  content-social skill
  │
  ├── brand-profile.md   ← inject brand-specific rules
  ├── workflow.md        ← generic flow logic
  ├── security.md        ← always loaded
  └── risk-gate.md       ← always loaded
```

Để dùng skill này cho brand khác: cập nhật brand-profile.md là đủ,
không cần sửa logic trong workflow.md.
