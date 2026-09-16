# MANIFEST — content-social

> Single source of truth cho version và cấu trúc skill `content-social`.

---

## Version

```yaml
skill: 4.9.0
release_type: consumer_insight_sales_writing_edition
last_updated: 2026-09-16
purpose: "Lean, practical Vietnamese F&B social copywriter for chatbots (Hermes) with Consumer Insight & Sales Writing"
```

---

## Cấu Trúc Thư Mục Skill (v4.9.0)

```
content-social-skill/
├── README.md                # Giới thiệu tổng quan & hướng dẫn tích hợp Hermes (v4.9.0)
├── SKILL.md                 # Entry point, Prime Directive, Provenance & Creative Boundary, Consumer Insight, 10 DoD Checks (v4.9.0)
├── MANIFEST.md              # Registry phiên bản & danh mục tài liệu (v4.9.0)
├── references/
│   ├── platforms.md         # Quy chuẩn 5 nền tảng (Facebook, IG, TikTok, Zalo OA, Zalo Personal, Soft heuristics)
│   ├── tones.md             # 5 tone giọng F&B, Ma trận thông số Tone & [OBSERVED]/[PROVIDED]/[CREATIVE] tagged
│   ├── formulas.md          # Công thức viết bài & Chuỗi tư duy bán hàng (SITUATION → TENSION → DESIRE → PRODUCT ROLE)
│   ├── hooks.md             # Kỹ thuật mở bài, Rhythm & Promise-Payoff, 6 dạng Hook thấu cảm & Reason to Care
│   ├── psychology.md        # Tâm lý bán hàng F&B (Attention → Relevance → Desire → Action, giữ nghiêm Semantic Fidelity)
│   ├── pricing.md           # Kỹ thuật viết giá & ưu đãi an toàn bằng placeholder (không tự thêm điều kiện promo)
│   ├── regression-fixtures.md # Bộ kiểm tra hồi quy chuẩn mực (8 bài ranh giới dữ kiện + 5 bài Consumer Insight CI-1..CI-5)
│   └── examples.md          # Tuyển tập 28+ bài viết mẫu chuẩn mực theo Source-Provenance Rule (v4.9.0)
└── tests/
    └── core-tests.md        # Bộ kiểm thử cốt lõi (8 bài Provenance + 5 bài Consumer Insight + 10 kịch bản thực tế)
```

---

## Danh Mục Nền Tảng Hỗ Trợ (Platform Registry)

| Platform | Định dạng chính | Hành vi mặc định |
| :--- | :--- | :--- |
| `facebook` | Post chia sẻ, bán hàng, tương tác | Mở bài gãy gọn, ngắt dòng thoáng, hashtag tùy chọn |
| `instagram` | Caption thẩm mỹ, ảnh đẹp | Ngắn gọn, tập trung cảm xúc/không gian, hashtag thẩm mỹ |
| `tiktok_reels` | Kịch bản video dọc ngắn | Bảng phân cảnh: Thời gian \| Hình ảnh/Góc quay \| Lời thoại/Voiceover |
| `zalo_oa` | Tin nhắn thông báo Broadcast | Tiêu đề in hoa, nội dung súc tích, đính kèm nút hành động |
| `zalo_personal` | Tin nhắn riêng tư 1:1, nhóm Zalo | Giọng người quen nói chuyện, không hashtag, CTA nhắn tin trực tiếp |

---

## Danh Mục Tài Liệu Tham Khảo (References)

| Tệp tin | Vai trò | Version | Trạng thái |
| :--- | :--- | :--- | :--- |
| `README.md` | Tài liệu giới thiệu tổng quan dự án | 4.9.0 | ✅ Active |
| `SKILL.md` | Bộ não điều khiển, Prime Directive, Provenance & Consumer Insight Layer | 4.9.0 | ✅ Active |
| `references/platforms.md` | Hướng dẫn định dạng 5 nền tảng, quy tắc gợi ý mềm (Soft Heuristics) | 4.9.0 | ✅ Active |
| `references/tones.md` | 5 tone giọng F&B, Ma trận thông số Tone & Data-layer tagged | 4.9.0 | ✅ Active |
| `references/formulas.md` | Công thức cốt lõi & Chuỗi tư duy bán hàng tự nhiên | 4.9.0 | ✅ Active |
| `references/hooks.md` | Mở bài, Rhythm, Promise-Payoff & 6 dạng Hook thấu cảm | 4.9.0 | ✅ Active |
| `references/storytelling.md` | 8 góc nhìn theo Reader Attention, khóa chặt Creative ≠ Factual | 4.9.0 | ✅ Active |
| `references/psychology.md` | Chuỗi tâm lý bán hàng (Attention → Relevance → Desire → Action) | 4.9.0 | ✅ Active |
| `references/pricing.md` | Trình bày giá & ưu đãi an toàn bằng placeholder tagged | 4.9.0 | ✅ Active |
| `references/regression-fixtures.md` | 8 bài hồi quy Provenance + 5 bài Consumer Insight (CI-1 đến CI-5) | 4.9.0 | ✅ Active |
| `references/examples.md` | Tuyển tập 28+ bài mẫu F&B chuẩn theo Source-Provenance Rule | 4.9.0 | ✅ Active |
| `tests/core-tests.md` | 8 bài Provenance + 5 bài Consumer Insight + 10 kịch bản thực chiến | 4.9.0 | ✅ Active |

---

## Nhật Ký Thay Đổi (Changelog)

### v4.9.0 (2026-09-16) — Consumer Insight & Sales Writing Edition
- **Tích hợp lớp Consumer Insight nhẹ nhàng trước Dominant Idea:**
  - **Tam giác nguyên tắc cốt lõi:**
    - `FACT tells us what we can say.` (Fact quyết định được nói gì)
    - `INSIGHT tells us why the customer may care.` (Insight quyết định vì sao khách quan tâm)
    - `CREATIVE tells us how to say it beautifully.` (Creative quyết định nói như thế nào cho hay)
  - **Ranh giới bất biến tối cao:** *"Insight may create relevance, but may not create evidence."* Tuyệt đối không bịa nhân khẩu học, hành vi cụ thể, bối cảnh thời gian hoặc công dụng sản phẩm để gán ghép insight.
  - **3 cấp độ bóc tách Insight:**
    - Cấp 1 (Explicit from brief): Khai thác dữ kiện khách hàng/thói quen có sẵn trong brief.
    - Cấp 2 (Relatable human truth as creative framing): Dùng sự thật đời thường phổ quát làm bối cảnh giả định (`[HYPOTHETICAL]`).
    - Cấp 3 (Product-only / sparse facts): Dùng human truth rất rộng về vai trò giải khát/nghỉ ngơi, không vẽ chuyện phức tạp.
  - **Chuỗi tư duy bán hàng tự nhiên:** `SITUATION → TENSION → DESIRE → PRODUCT ROLE` & `HOOK → WHY CARE → PRODUCT ROLE → CTA`.
  - **Xác định rõ vai trò sản phẩm (Product Role):** Giải pháp, phần thưởng nhỏ, món quen, lựa chọn tiết kiệm, món để chia sẻ, lý do ghé quán.
- **Tái cấu trúc và đồng bộ các tài liệu tham khảo:**
  - `references/psychology.md`: Tái cấu trúc xoay quanh chuỗi tâm lý bán hàng thực chiến `Attention → Relevance → Desire → Action`, bảo toàn 100% các ràng buộc chống bịa đặt số liệu (`khách ≠ ly`) và không tự phong best-seller.
  - `references/hooks.md`: Bổ sung 6 dạng Hook thấu cảm & khơi gợi lý do quan tâm (Recognition, Curiosity, Desire, Situation, Contrast, Identity, Direct Offer).
  - `references/formulas.md`: Bổ sung luồng tư duy bán hàng linh hoạt, thoát ly khỏi template cứng nhắc.
  - `SKILL.md`: Bổ sung tiêu chuẩn kiểm định chất lượng bán hàng tự nhiên (Sales Quality & Reason to Care) trong Silent QA [10].
- **Bổ sung 5 bài kiểm tra hồi quy Consumer Insight (`references/regression-fixtures.md` & `tests/core-tests.md`):**
  - Đưa 5 bài kiểm tra hồi quy chuẩn mực (`Test CI-1` đến `Test CI-5`) đánh giá khả năng tạo lý do mua hàng mà không vi phạm ranh giới dữ kiện.

### v4.8.0 (2026-09-16) — Provenance & Creative Boundary Edition
- **Ranh giới cốt lõi: Sáng tạo nghệ thuật ≠ Bịa đặt sự thật (Creative Freedom ≠ Factual Freedom):**
  - Đóng khung 2 nguyên tắc tối cao: *"When facts are sparse, increase creativity — not fabrication"* & *"Creative can imagine the feeling, not the fact."*
  - Cho phép tối đa tự do sáng tạo về mood, ẩn dụ, nhịp điệu, văn phong đời thường, góc nhìn cảm xúc; tuyệt đối ngăn chặn việc tự sáng tác các chi tiết mang hình thức factual claim.
- **Triệt tiêu các suy diễn tinh vi (Subtle Grounding Prohibitions):**
  - **Cấm suy diễn nhiệt độ từ hình ảnh:** Thấy đá viên $\rightarrow$ không tự suy diễn thành *"mát lạnh"*, *"đá lạnh"*, *"nóng hổi"*. Chỉ tả thị giác thuần túy (`đá viên`, `hạt sương đọng ngoài thành ly`).
  - **Cấm suy diễn không gian / âm thanh / thời gian không thấy trong ảnh:** Bỏ các chi tiết tự suy diễn từ ảnh tĩnh như *"ngoài hiên"*, *"tiếng nhạc êm êm"*, *"chỗ ngồi mát mẻ"*.
- **Bảo toàn chuẩn xác ngữ nghĩa số liệu (Semantic Fidelity):**
  - Quy tắc bất biến: `khách ≠ ly`, `số đơn ≠ số ly`, `lượt khách ≠ số đơn`, `doanh thu ≠ lợi nhuận`.
  - Cấm tự phong danh hiệu *"món bán chạy nhất"*, *"best-seller"* khi brief chỉ cung cấp số liệu bán hàng thông thường.
  - Bổ sung Cặp 4 trực diện trong BAD vs GOOD về bảo toàn `126 khách`.
- **Ngăn chặn ảo giác thay thế (No Replacement Hallucination):**
  - Khi chặn một claim không hợp lệ (y khoa, best seller ảo), model chuyển sang ngôn từ cảm xúc mộc mạc, tuyệt đối không bịa một fact khác để bù vào (như bịa quán đông nghẹt).
- **Không tự thêm điều kiện khuyến mãi ngoài brief:**
  - Sửa bài mẫu Mẫu 3 Text Brief và template `pricing.md`, loại bỏ việc tự gán thêm các điều kiện ràng buộc như `"chỉ áp dụng mua mang đi"` hay `"giảm trên mỗi ly"`.
- **Provenance là cơ chế ngầm (Internal Silent QA):**
  - Quy định rõ ràng: các nhãn `[OBSERVED]`, `[PROVIDED]`, `[CREATIVE]`, `[HYPOTHETICAL]` chỉ dùng cho Silent QA nội bộ, không in ra bài viết cho khách hàng.
- **Tích hợp 8 bài kiểm tra hồi quy ranh giới dữ kiện (`tests/core-tests.md`):**
  - Đưa đầy đủ 8 Regression Test Cases vào bộ kiểm thử chính thức với tiêu chí Pass/Fail rõ ràng.

### v4.7.0 (2026-09-16) — Zero-Contradiction & Provenance Edition
- **Nguyên tắc cốt lõi: Every Claim Must Have A Provenance (`SKILL.md`):** Tinh gọn Claim Check thành 4 nguồn gốc dữ liệu bắt buộc (`[OBSERVED]`, `[PROVIDED]`, `[CREATIVE]`, `[HYPOTHETICAL]`). Nếu factual claim không có provenance: BỎ HẲN hoặc VIẾT LẠI thành Creative/Hypothetical.
- **Thanh lọc toàn diện các bài mẫu Image $\rightarrow$ Caption (`references/examples.md`):**
  - Mẫu 1 (Cafe muối): Xóa bỏ suy diễn hành vi khách ("ngồi ngắm phố 15 phút") và tác động cảm xúc ("tự khắc thấy nhẹ nhõm"); chuyển sang 100% thị giác (`hai tầng rõ rệt`, `sương đá đọng li ti`) và lời mời giả định.
  - Mẫu 2 (Trà đào cam sả): Loại bỏ claim tác dụng "giải nhiệt", thay bằng cảm quan thị giác ("dịu mắt giữa trưa hè").
  - Mẫu 4 (Góc bàn gỗ): Loại bỏ fact vận hành tự bịa về giờ mở cửa ("Quán mở cửa tới 22h").
- **Triệt tiêu Factual Hallucination trong Text Brief (`references/examples.md`):**
  - Mẫu 3 (Giảm 5k bình cá nhân): Xóa bỏ claim tính năng sản phẩm ("Vừa giữ nhiệt cho ly nước của bạn ngon trọn vẹn suốt cả buổi").
  - Mẫu 5 (Bánh Croissant): Xóa bỏ fact vận hành không có trong brief ("Bánh mới ra lò mỗi sáng").
  - Mẫu Humor: Loại bỏ các từ khóa thể chất/chế độ ăn (`"giữ dáng"`, `"giảm cân"`), chuyển sang chuyện tiết kiệm ví tiền; loại bỏ `"xả stress"`, `"cho tỉnh người"`.
  - Mẫu Storytelling: Đóng khung 100% bối cảnh ngày mưa/không gian góc bàn thành `[HYPOTHETICAL Scene]`; bổ sung brief thực tế cho góc Craft (6h sáng mở quầy).
  - Cặp BAD vs GOOD: Loại bỏ claim tiện ích tự bịa ("quán có sẵn điều hòa mát mẻ") trong Cặp 3.
- **Chuyển đổi quy chuẩn nền tảng sang Soft Heuristics (`references/platforms.md`):**
  - Xóa bỏ giả định UI dễ thay đổi ("Chữ bị ẩn sau 3 dòng đầu").
  - Chuyển các định mức số (Facebook 3 dòng, Instagram hashtag, TikTok timing, Zalo từ) thành quy tắc gợi ý mềm (Soft Heuristics).
- **Anti-AI và Giọng văn không dạy model claim mặc định (`hooks.md`, `tones.md`):**
  - Loại bỏ các sensory claim mặc định trong bảng Anti-AI; luôn bổ sung phương án thị giác `[OBSERVED]` song song.
  - Loại bỏ các tag `[OBSERVED]` giả tạo trong các đề bài chỉ là text brief của `tones.md`.

### v4.6.0 (2026-09-16) — 100% Consistent Edition (Instruction & Demonstration Alignment)
- **Phân loại 3 tầng dữ liệu cho mọi ví dụ (`[OBSERVED]` / `[PROVIDED]` / `[CREATIVE]`):** Rà soát và gắn nhãn tường minh toàn bộ ví dụ trong `hooks.md`, `tones.md`, `psychology.md`, `pricing.md`. Không để bất kỳ ví dụ nào gây hiểu lầm thành fact tự sinh.
- **Chuyển đổi công thức sang khung Placeholder an toàn (`formulas.md`):** Hook-Value-CTA và PAS được chuyển 100% sang khung mẫu placeholder (`[Tên món]`, `[Thành phần đã cung cấp]`, `[Đặc điểm vị giác đã cung cấp]`, `[Giá]`), xóa bỏ câu văn hoàn chỉnh dễ gây rò rỉ fact.
- **Khóa chặt ranh giới Sáng tạo trong Kể chuyện (`storytelling.md`):** Cấm tự tạo nhân vật khách hàng, hội thoại, thời gian vận hành hoặc sự kiện cụ thể như chuyện có thật. Mọi câu chuyện sáng tạo bắt buộc phải dùng Hypothetical Framing.
- **Chuẩn hóa Claim Check theo cây quyết định 2 nhánh (`SKILL.md`):** `FACT? (YES: [PROVIDED] / [OBSERVED] | NO: [CREATIVE] / [HYPOTHETICAL])`. Tuyệt đối không biến câu văn Creative thành Fact chỉ vì nghe êm tai.
- **Xóa bỏ các số liệu/thống kê không có nguồn:** Xóa bỏ *"3 giây"* trong `hooks.md`, thay bằng *"người xem quyết định rất nhanh"*.

---

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
