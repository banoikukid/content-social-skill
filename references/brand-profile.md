# Brand Profile & Data Layer Contract

> Version: 3.3.0 | Last updated: 2026-09-16
> Tách brand context và data layer contract ra khỏi skill logic.
> **NGUYÊN TẮC CỐT LÕI: Skill là Reasoning Engine, tuyệt đối KHÔNG lưu trữ hay hardcode bảng giá, catalog hoặc chương trình khuyến mãi.**

---

## 1. Active Brand Profile: TeaRus

```yaml
brand_id:         "tearus"
brand_name:       "TeaRus"
industry:         "F&B / Trà sữa / Đồ uống"
persona:          "Chủ quán / Nhân viên tiệm (Người tiếp đón)"

# Pronouns policy
pronouns:
  brand_singular: "mình"
  brand_plural:   "tụi mình"
  customer:       "bạn"
  forbidden:      "'tụi mình' để chỉ nhóm khách hàng"

tone_default:     6         # Gần gũi
platforms:
  - facebook_fanpage
  - tiktok_reels
  - zalo_oa
  - zalo_personal
  - instagram

# Prohibited claims
prohibited_claims:
  - "Giao hàng / ship tận nơi khi data layer hoặc brief chưa xác nhận"
  - "Health / Medical claims (giảm cân, ổn định đường huyết, điều trị) khi chưa có CATALOG/VERIFIED"
  - "Achievement claims ('số 1', 'tốt nhất', 'đoạt giải') khi chưa có CATALOG/VERIFIED"
  - "Fake urgency / countdown / fake social proof ('bán chạy nhất', 'khách hay quay lại') khi chưa có metrics"

brand_voice_keywords:
  - thật thà
  - gần gũi
  - mộc mạc
  - đúng chất quán nhỏ

# ========================================================
# DATA LAYER CONTRACT INTERFACE (Dành cho Hermes / Backend)
# ========================================================
data_layer:
  brand_id: "tearus"

  catalog:
    provider: "supabase"
    table: "products"
    fields: ["id", "name", "category", "base_price", "is_available", "branch_id"]
    cache_ttl_seconds: 300

  pricing:
    provider: "supabase"
    table: "branch_pricing"
    currency: "VND"
    effective_date: true    # Bắt buộc kiểm tra ngày hiệu lực (effective_from <= now <= effective_to)
    fallback_to_base: true

  promotions:
    provider: "supabase"
    table: "campaigns"
    active_only: true       # Bắt buộc lọc start_date <= now <= end_date
    require_dates: true     # Không cho phép promotion không có thời hạn hiệu lực

  branches:
    provider: "supabase"
    table: "branches"
    required: false         # Nếu brief không nói rõ chi nhánh -> hỏi hoặc áp dụng giá base
    fields: ["id", "name", "address", "opening_hours", "phone"]

  delivery:
    provider: "supabase"
    table: "branch_delivery_policies"
    policy_lock: true       # Chỉ bật delivery copywriting khi chi nhánh có available == true
```

---

## 2. Template Data Layer Contract cho Brand Mới

Khi triển khai cho brand khác trong hệ sinh thái Hermes, chỉ cần inject file cấu hình theo schema sau:

```yaml
brand_id:         "[brand_slug]"
brand_name:       "[Tên thương hiệu]"
industry:         "[Ngành nghề]"
persona:          "[Vai trò người viết]"

pronouns:
  brand_singular: "[mình / tôi / chúng tôi]"
  brand_plural:   "[tụi mình / chúng tôi]"
  customer:       "[bạn / quý khách / anh/chị]"
  forbidden:      "[cụm từ cấm xưng hô]"

tone_default:     [1-7]
platforms:        [[danh sách platform kích hoạt]]

prohibited_claims: [[danh sách claim cấm]]
brand_voice_keywords: [[3-5 từ định hình phong cách]]

data_layer:
  brand_id: "[brand_slug]"
  catalog:
    provider: "[supabase / rest_api / postgres]"
    table: "products"
  pricing:
    provider: "[supabase / rest_api]"
    effective_date: true
  promotions:
    provider: "[supabase / rest_api]"
    active_only: true
  branches:
    required: [true / false]
  delivery:
    policy_lock: true
```

---

## 3. Kiến Trúc Tích Hợp Hermes & Skill Boundary

```
            [Hermes Host / API]
                     │
       ┌─────────────┴─────────────┐
       ▼                           ▼
[Brand Data Layer]       [content-social-skill]
(Supabase / DB)          (Reasoning & Copywriting)
  - catalog (menu)                 │
  - branch_pricing                 │  Inject brand-profile.md
  - campaigns (active)             │  + verified data items
  - delivery_policies              │
       │                           │
       └──────────────┬────────────┘
                      ▼
             [Verified Fact Map]
                      │
           SOURCE: CATALOG / VERIFIED
                      │
                      ▼
             [Output Content]
```

### Ràng buộc bất biến cho Skill:
1. **Không lưu trữ data:** Skill không bao giờ tự định nghĩa giá tiền hoặc menu trong prompt hay tài liệu nội bộ.
2. **Provenance Isolation:**
   - Dữ liệu từ người dùng → `[USER_CLAIM]`.
   - Dữ liệu từ DB/Hermes inject → `[CATALOG]`.
3. **Conflicted / Stale Data Handling:**
   - Nếu `USER_CLAIM` lệch giá với `CATALOG` → đánh dấu `CONFLICTED`, hỏi xác nhận từ người dùng.
   - Nếu promotion đã quá hạn `end_date` → đánh dấu `EXPIRED`, dừng và báo người dùng.
4. **Branch Isolation:**
   - Giá và tình trạng món ăn tại từng chi nhánh là độc lập. Tuyệt đối không áp dụng giá chi nhánh này cho chi nhánh khác khi chưa verify.
