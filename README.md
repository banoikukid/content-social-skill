# content-social-skill (v4.6.0)

> **AI Copywriter chuyên ngành F&B (Trà, Cà Phê, Đồ Uống) tối ưu cho Chatbot (Hermes).**  
> Chuyển đổi yêu cầu từ văn bản brief hoặc hình ảnh thành bài viết mạng xã hội tự nhiên, đậm chất đời thường và có chuyển đổi cao.

---

## 🌟 Nguyên Tắc Tối Cao & Trụ Cột Sáng Tác (Consistent Craft)

> **"Chất lượng nội dung và sự tự nhiên của tiếng Việt luôn được ưu tiên cao hơn việc bám máy móc vào template hay công thức."**

1. **Một ý tưởng chủ đạo (One Dominant Idea):** Mỗi bài viết chỉ truyền tải 1 ý tưởng cốt lõi (Mood, Sản phẩm, Ưu đãi, hoặc Câu chuyện), không nhồi nhét lan man.
2. **Caption không thuần tả ảnh (Caption ≠ Image Description):** Không chỉ liệt kê những gì mắt thấy; dùng hình ảnh làm chất xúc tác/bằng chứng khơi nguồn cho một ý tưởng hay khoảnh khắc.
3. **Lời hứa & Lời giải (Hook $\rightarrow$ Promise $\rightarrow$ Payoff):** Hook là một lời hứa với người đọc; thân bài bắt buộc phải trả lời và giải quyết trọn vẹn lời hứa đó, không giật tít vượt quá nội dung.
4. **Tư duy tiếng Việt thuần thục (Native Vietnamese Craft):** Viết trực tiếp bằng ngôn ngữ đời thường của người Việt, không dịch máy móc cấu trúc câu tiếng Anh.
5. **Observation > Insight (Ưu tiên quan sát thật):** Lấy chi tiết quan sát làm điểm tựa; insight là tùy chọn, không ép AI tự vẽ ra insight sáo rỗng.
6. **Nhất quán 100% giữa Rule & Examples:** Mọi ví dụ đều được phân tầng dữ liệu rõ ràng (`[OBSERVED]`, `[PROVIDED]`, `[CREATIVE]`), không để bất kỳ ví dụ nào dạy model vi phạm Hard Constraints.

---

## 🚀 Kiến Trúc Copywriting Engine (v4.6.0)

```
User Input (Text / Image / Brief)
            │
            ▼
1. QUAN SÁT & CHỌN GÓC (Observation → Detail → Dominant Idea)
   - Quan sát chi tiết thị giác/input → Nhận diện 1 chi tiết thú vị đáng nói
   - Insight là TÙY CHỌN: Chỉ dùng khi thực sự giúp bài hay hơn (Observation > Insight)
   - Chọn 1 ý tưởng chủ đạo (One Dominant Idea) & 1 góc nhìn đắt giá (8 Angles)
   - Ngầm tạo 2–3 hook ứng viên → Chọn hook có "lời hứa" ăn nhập nhất
            │
            ▼
2. VIẾT BÀI VỚI VĂN PHONG TỰ NHIÊN & CÓ NHỊP ĐIỆU
   - Triệt tiêu 8 khuôn mẫu sáo rỗng AI (AI Cliché Patterns)
   - Kỹ thuật nhịp điệu (Sentence Rhythm Engineering): xen kẽ câu ngắn, câu dài, câu punchline
   - Ưu tiên chi tiết cụ thể hơn tính từ mơ hồ (Specificity > Generic Adjective)
   - Phân biệt Voice (bản sắc quán) vs Tone (tâm trạng bài viết)
   - Định dạng chuẩn theo nền tảng (User request ghi đè mặc định)
            │
            ▼
3. KIỂM ĐỊNH TIÊU CHUẨN XUẤT BẢN (Definition of Done QA — 10 Silent Checks)
   - Chạy thầm 10 câu hỏi kiểm tra nội bộ (KHÔNG in checklist ra ngoài chat):
     [1] Brief fit  [2] 1 Dominant Idea  [3] Angle rõ  [4] Hook Promise-Payoff  [5] Caption ≠ Image Desc
     [6] Specificity  [7] Claim Check (nguồn dữ kiện)  [8] Anti-AI / No slop  [9] Voice/Tone/Platform  [10] Natural CTA/Emoji
            │
            ▼
Output bài viết hoàn chỉnh ngay lập tức (KHÔNG tra khảo người dùng)
```

---

## 📂 Cấu Trúc Thư Mục Tinh Gọn

```
content-social-skill/
├── README.md                # Tài liệu giới thiệu tổng quan dự án (v4.5.0)
├── SKILL.md                 # Entry point, Prime Directive, Observation > Insight, 10 DoD Checks
├── MANIFEST.md              # Registry phiên bản & danh mục tài liệu (v4.5.0)
├── references/
│   ├── platforms.md         # Quy chuẩn 5 nền tảng: Facebook, Instagram, TikTok, Zalo OA, Zalo Personal
│   ├── tones.md             # 5 tone giọng F&B & Emoji Density Tendency (sạch claim)
│   ├── formulas.md          # 4 công thức viết bài: Hook-Value-CTA, PAS, FAB, Storytelling (sạch claim)
│   ├── hooks.md             # Mở bài 3s, 8 khuôn mẫu AI, Rhythm & Promise-Payoff (sạch claim)
│   ├── storytelling.md      # Động cơ 8 góc nhìn (Angle Engine), Ma trận kỹ thuật, Soft CTA
│   ├── psychology.md        # 7 kỹ thuật tâm lý thực chiến F&B (chống bịa hành vi, giả định tương lai)
│   ├── pricing.md           # Kỹ thuật viết giá & ưu đãi F&B dùng placeholder an toàn
│   └── examples.md          # Tuyển tập 28+ bài mẫu F&B chuẩn (Image/Brief, Rewrite, Bad vs Good)
└── tests/
    └── core-tests.md        # 10 kịch bản kiểm thử thực tế
```

---

## 💬 Hướng Dẫn Tích Hợp Cho Chatbot (Hermes)

- **Không tra khảo người dùng (Zero Interrogation):** Khi người dùng đưa brief ngắn (`"Viết bài trà đào 35k"`) hoặc chỉ gửi ảnh, bot lập tức áp dụng *Mặc định hợp lý* (Facebook + Gần gũi) để xuất bài hoàn chỉnh ngay từ lượt phản hồi đầu tiên.
- **Tương tác lặp tức thì:** Nếu người dùng yêu cầu chỉnh sửa (*"viết hài hơn"*, *"rút ngắn lại"*), bot viết lại ngay lập tức mà không tranh cãi.
- **Xử lý an toàn thông minh (Block Claim, Continue Content):** Khi người dùng đưa yêu cầu nhạy cảm (như cam kết y khoa), bot tự động loại bỏ claim rủi ro và tiếp tục viết bài hoàn chỉnh tập trung vào hương vị và trải nghiệm thư giãn.

---

## 📄 Bản Quyền & Giấy Phép

Dự án thuộc hệ sinh thái của Hermes Assistant. Phát triển bởi TeaRus Team.
