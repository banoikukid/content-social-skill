# content-social-skill (v4.9.0)

> **AI Copywriter chuyên ngành F&B (Trà, Cà Phê, Đồ Uống) tối ưu cho Chatbot (Hermes).**  
> Chuyển đổi yêu cầu từ văn bản brief hoặc hình ảnh thành bài viết mạng xã hội tự nhiên, đậm chất đời thường và có chuyển đổi cao với lớp Thấu cảm khách hàng (Consumer Insight).

---

## 🌟 Nguyên Tắc Tối Cao & Trụ Cột Sáng Tác (Consistent Craft)

> **"Chất lượng nội dung và sự tự nhiên của tiếng Việt luôn được ưu tiên cao hơn việc bám máy móc vào template hay công thức."**
>
> 🌟 **Tam Giác Cốt Lõi: Fact – Insight – Creative:**
> - **FACT tells us what we can say.** *(Fact quyết định được nói gì — chống bịa đặt 100%)*
> - **INSIGHT tells us why the customer may care.** *(Insight quyết định vì sao khách quan tâm — tạo lý do mua hàng)*
> - **CREATIVE tells us how to say it beautifully.** *(Creative quyết định nói như thế nào cho hay — tạo cảm xúc và văn phong)*
>
> 🔴 **Ranh giới bất biến:** *"Insight may create relevance, but may not create evidence."* (Insight tạo sự đồng cảm, không tạo ra bằng chứng hay dữ kiện mới).

1. **Một ý tưởng chủ đạo (One Dominant Idea):** Mỗi bài viết chỉ truyền tải 1 ý tưởng cốt lõi (Mood, Sản phẩm, Ưu đãi, hoặc Câu chuyện), không nhồi nhét lan man.
2. **Caption không thuần tả ảnh (Caption ≠ Image Description):** Không chỉ liệt kê những gì mắt thấy; dùng hình ảnh làm chất xúc tác/bằng chứng khơi nguồn cho một ý tưởng hay khoảnh khắc.
3. **Lời hứa & Lời giải (Hook $\rightarrow$ Promise $\rightarrow$ Payoff):** Hook là một lời hứa với người đọc; thân bài bắt buộc phải trả lời và giải quyết trọn vẹn lời hứa đó, không giật tít vượt quá nội dung.
4. **Tư duy tiếng Việt thuần thục (Native Vietnamese Craft):** Viết trực tiếp bằng ngôn ngữ đời thường của người Việt, không dịch máy móc cấu trúc câu tiếng Anh.
5. **Thấu cảm có căn cứ (Grounded Consumer Insight):** Tìm ra lý do khách hàng quan tâm (Tension, Desire, Product Role) mà không bịa đặt chân dung nhân khẩu học hay công dụng sản phẩm.
6. **Nhất quán 100% giữa Rule & Examples:** Mọi ví dụ đều tuân thủ nguyên tắc Every Claim Must Have A Provenance (`[OBSERVED]`, `[PROVIDED]`, `[CREATIVE]`, `[HYPOTHETICAL]`), triệt tiêu hoàn toàn việc ví dụ dạy model vi phạm Hard Constraints. Không suy diễn nhiệt độ từ đá trong ảnh, bảo toàn ngữ nghĩa số liệu (`khách ≠ ly`).

---

## 🚀 Kiến Trúc Copywriting Engine (v4.9.0)

```
User Input (Text / Image / Brief)
            │
            ▼
1. BÓC TÁCH DỮ LIỆU & THẤU CẢM KHÁCH HÀNG (Observation & Insight)
   - Bóc tách Fact: [OBSERVED], [PROVIDED], [CREATIVE], [HYPOTHETICAL]
   - Thấu cảm (Consumer Insight): SITUATION → TENSION → DESIRE → PRODUCT ROLE
   - Trả lời câu hỏi: "Vì sao khách hàng lại quan tâm bài viết này?"
   - Chọn 1 ý tưởng chủ đạo (One Dominant Idea) & 1 góc nhìn đắt giá (8 Angles)
   - Ngầm tạo 2–3 hook ứng viên (Hook gắn với Lời hứa & Reason to care)
            │
            ▼
2. VIẾT BÀI VỚI VĂN PHONG TỰ NHIÊN & CÓ NHỊP ĐIỆU (Writing & Rhythm)
   - Triệt tiêu 8 khuôn mẫu sáo rỗng AI (AI Cliché Patterns)
   - Kỹ thuật nhịp điệu (Sentence Rhythm Engineering): xen kẽ câu ngắn, câu dài, câu punchline
   - Chi tiết cụ thể có căn cứ (Evidence-backed Specificity > Generic Adjective)
   - Phân biệt Voice (bản sắc quán) vs Tone (tâm trạng bài viết)
   - Định dạng chuẩn theo nền tảng (User request ghi đè mặc định)
            │
            ▼
3. KIỂM ĐỊNH TIÊU CHUẨN XUẤT BẢN (Definition of Done QA — 10 Silent Checks)
   - Chạy thầm 10 câu hỏi kiểm tra nội bộ (KHÔNG in checklist ra ngoài chat):
     [1] Brief fit  [2] 1 Dominant Idea  [3] Angle rõ  [4] Hook Promise-Payoff  [5] Caption ≠ Image Desc
     [6] Evidence-backed Specificity  [7] Claim Check (nguồn dữ kiện)  [8] Anti-AI / No slop  [9] Voice/Tone/Platform  [10] Natural CTA & Sales Quality
            │
            ▼
Output bài viết hoàn chỉnh ngay lập tức (KHÔNG tra khảo người dùng)
```

---

## 📂 Cấu Trúc Thư Mục Tinh Gọn

```
content-social-skill/
├── README.md                # Giới thiệu tổng quan & hướng dẫn tích hợp Hermes (v4.9.0)
├── SKILL.md                 # Entry point, Prime Directive, Provenance & Consumer Insight Layer (v4.9.0)
├── MANIFEST.md              # Registry phiên bản & danh mục tài liệu (v4.9.0)
├── references/
│   ├── platforms.md         # Quy chuẩn 5 nền tảng: Facebook, Instagram, TikTok, Zalo OA, Zalo Personal
│   ├── tones.md             # 5 tone giọng F&B & Emoji Density Tendency (sạch claim)
│   ├── formulas.md          # Công thức viết bài & Chuỗi tư duy bán hàng (SITUATION → TENSION → DESIRE → PRODUCT ROLE)
│   ├── hooks.md             # Mở bài thu hút, nhịp điệu, 8 khuôn mẫu AI, Promise-Payoff & 6 dạng Hook thấu cảm
│   ├── storytelling.md      # Động cơ 8 góc nhìn (Angle Engine), Ma trận kỹ thuật, Soft CTA
│   ├── psychology.md        # Chuỗi tâm lý bán hàng F&B (Attention → Relevance → Desire → Action, sạch claim)
│   ├── pricing.md           # Kỹ thuật viết giá & ưu đãi F&B dùng placeholder an toàn
│   ├── regression-fixtures.md # Bộ kiểm tra hồi quy chuẩn mực (8 bài Provenance + 5 bài Consumer Insight)
│   └── examples.md          # Tuyển tập 28+ bài mẫu F&B chuẩn (Image/Brief, Rewrite, Bad vs Good)
└── tests/
    └── core-tests.md        # 8 bài Provenance + 5 bài Consumer Insight + 10 kịch bản thực tế (v4.9.0)
```

---

## 💬 Hướng Dẫn Tích Hợp Cho Chatbot (Hermes)

- **Không tra khảo người dùng (Zero Interrogation):** Khi người dùng đưa brief ngắn (`"Viết bài trà đào 35k"`) hoặc chỉ gửi ảnh, bot lập tức áp dụng *Mặc định hợp lý* (Facebook + Gần gũi) để xuất bài hoàn chỉnh ngay từ lượt phản hồi đầu tiên.
- **Tương tác lặp tức thì:** Nếu người dùng yêu cầu chỉnh sửa (*"viết hài hơn"*, *"rút ngắn lại"*), bot viết lại ngay lập tức mà không tranh cãi.
- **Xử lý an toàn thông minh (Block Claim, Continue Content & No Replacement):** Khi người dùng đưa yêu cầu nhạy cảm (như cam kết y khoa) hoặc yêu cầu bịa đặt, bot tự động loại bỏ claim rủi ro và tiếp tục viết bài hoàn chỉnh dựa trên dữ kiện đã có provenance hoặc bằng framing cảm xúc không-claim, tuyệt đối không tự ý bịa thêm hương vị hay không gian mới.

---

## 📄 Bản Quyền & Giấy Phép

Dự án thuộc hệ sinh thái của Hermes Assistant. Phát triển bởi TeaRus Team.
