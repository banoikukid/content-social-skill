# content-social-skill (v4.4.0)

> **AI Copywriter chuyên ngành F&B (Trà, Cà Phê, Đồ Uống) tối ưu cho Chatbot (Hermes).**  
> Chuyển đổi yêu cầu từ văn bản brief hoặc hình ảnh thành bài viết mạng xã hội tự nhiên, đậm chất đời thường và có chuyển đổi cao.

---

## 🌟 Nguyên Tắc Tối Cao & 4 Trụ Cột Sáng Tác (Golden Craft Principles)

> **"Chất lượng nội dung và sự tự nhiên của tiếng Việt luôn được ưu tiên cao hơn việc bám máy móc vào template hay công thức."**

1. **Một ý tưởng chủ đạo (One Dominant Idea):** Mỗi bài viết chỉ truyền tải 1 ý tưởng cốt lõi (Mood, Sản phẩm, Ưu đãi, hoặc Câu chuyện), không nhồi nhét lan man.
2. **Caption không thuần tả ảnh (Caption ≠ Image Description):** Không chỉ liệt kê những gì mắt thấy; dùng hình ảnh làm chất xúc tác/bằng chứng khơi nguồn cho một ý tưởng hay khoảnh khắc.
3. **Lời hứa & Lời giải (Hook $\rightarrow$ Promise $\rightarrow$ Payoff):** Hook là một lời hứa với người đọc; thân bài bắt buộc phải trả lời và giải quyết trọn vẹn lời hứa đó, không giật tít vượt quá nội dung.
4. **Tư duy tiếng Việt thuần thục (Native Vietnamese Craft):** Viết trực tiếp bằng ngôn ngữ đời thường của người Việt, không dịch máy móc cấu trúc câu tiếng Anh.

---

## 🚀 Kiến Trúc Copywriting Engine (v4.4.0)

```
User Input (Text / Image / Brief)
            │
            ▼
1. ĐỘNG CƠ INSIGHT & CHỌN GÓC (Insight & Angle Engine)
   - Quan sát chi tiết thị giác → Tìm điểm thú vị & insight người đọc
   - Khám phá 8 góc nhìn: Sản phẩm | Cảm xúc | Đời thường | Hài hước | Tò mò | Nghề quán | Dịp | Tối giản
   - Ngầm tạo 2–3 hook ứng viên → Chọn hook có "lời hứa" ăn nhập nhất
            │
            ▼
2. VIẾT BÀI VỚI VĂN PHONG TỰ NHIÊN & CÓ NHỊP ĐIỆU
   - Triệt tiêu 8 khuôn mẫu sáo rỗng AI (AI Cliché Patterns)
   - Kỹ thuật nhịp điệu (Sentence Rhythm Engineering): xen kẽ câu ngắn, câu dài, câu punchline
   - Ưu tiên chi tiết cụ thể hơn tính từ mơ hồ (Specificity > Generic Adjective)
   - Đại từ linh hoạt theo phong cách quán (Adaptive Voice)
            │
            ▼
3. KIỂM ĐỊNH SÁNG TẠO NỘI BỘ (Creative QA)
   - Kiểm tra thầm 8 điểm: Brief fit | Angle | Specificity | Rhythm | Natural Vietnamese | Anti-AI | Platform/CTA | Read-aloud
            │
            ▼
Output bài viết hoàn chỉnh (KHÔNG tra khảo người dùng)
```

---

## 📂 Cấu Trúc Thư Mục Tinh Gọn

```
content-social-skill/
├── README.md                # Tài liệu giới thiệu tổng quan dự án
├── SKILL.md                 # Entry point, Prime Directive, Hard vs Soft rules, Angle Engine
├── MANIFEST.md              # Registry phiên bản & danh mục tài liệu (v4.2.0)
├── references/
│   ├── platforms.md         # Quy chuẩn 5 nền tảng: Facebook, Instagram, TikTok, Zalo OA, Zalo Personal
│   ├── tones.md             # 5 tone giọng F&B & Adaptive Voice theo từng phong cách quán
│   ├── formulas.md          # 4 công thức viết bài: Hook-Value-CTA, PAS, FAB, Story (Soft Guidance)
│   ├── hooks.md             # Mở bài 3s, 8 khuôn mẫu AI, Kỹ thuật nhịp điệu (Rhythm) & Specificity
│   ├── storytelling.md      # Động cơ 8 góc nhìn (Angle Engine), Ma trận kỹ thuật, Soft CTA
│   ├── psychology.md        # 7 kỹ thuật tâm lý thực chiến F&B (chống bịa hành vi, giả định tương lai)
│   └── pricing.md           # Kỹ thuật viết giá & ưu đãi F&B dùng placeholder an toàn
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
