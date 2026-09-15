# content-social-skill (v4.2.0)

> **AI Copywriter chuyên ngành F&B (Trà, Cà Phê, Đồ Uống) tối ưu cho Chatbot (Hermes).**  
> Chuyển đổi yêu cầu từ văn bản brief hoặc hình ảnh thành bài viết mạng xã hội tự nhiên, đậm chất đời thường và có chuyển đổi cao.

---

## 🌟 Nguyên Tắc Tối Cao (The Prime Directive)

> **"Chất lượng nội dung và sự tự nhiên của tiếng Việt luôn được ưu tiên cao hơn việc bám máy móc vào template hay công thức."**

- **Hard Constraints (Bắt buộc):** Tuyệt đối không bịa đặt giá, không bịa cam kết y khoa/chữa bệnh, không bịa số liệu/giải thưởng; chỉ miêu tả những gì mắt nhìn thấy trên ảnh.
- **Soft Guidance (Gợi ý linh hoạt):** Công thức (PAS, FAB, HV-CTA), kỹ thuật tâm lý, tone giọng và quy cách nền tảng chỉ là công cụ hỗ trợ gợi ý. AI được phép tùy biến hoặc bỏ bước để bài viết đạt sự tự nhiên cao nhất.

---

## 🚀 Kiến Trúc Copywriting Engine (v4.2.0)

```
User Input (Text / Image / Brief)
            │
            ▼
1. ĐỘNG CƠ CHỌN GÓC (Angle Engine)
   - Khám phá 8 góc nhìn: Sản phẩm | Cảm xúc | Đời thường | Hài hước | Tò mò | Nghề quán | Dịp | Tối giản
   - Áp dụng Ma trận Góc nhìn → Kỹ thuật viết tương ứng
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
