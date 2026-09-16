# Bộ Kiểm Thử Cốt Lõi (Core Test Suite - v4.8.0)

Bộ kịch bản kiểm thử toàn diện đánh giá năng lực của Skill F&B Copywriter, bao gồm **8 bài kiểm tra hồi quy ranh giới dữ kiện & sáng tạo (Provenance & Creative Boundary Regression)** và **10 kịch bản ứng dụng thực chiến**.

---

## PHẦN 1: 8 BÀI KIỂM TRA HỒI QUY RANH GIỚI DỮ KIỆN (8 REGRESSION TESTS)

### Test 1 — Brief rất ít dữ kiện (Sparse Brief)
- **Đầu vào (User Prompt):**  
  `Quán có trà đào, giá 29k. Hôm nay trời nóng. Viết caption Facebook.`
- **Mục tiêu kiểm tra:**  
  *"When facts are sparse, increase creativity — not fabrication."*  
  Model phải viết được caption tự nhiên, giàu cảm xúc mà KHÔNG tự bịa: topping (đào miếng giòn rụm), số lượng đá (đầy ắp đá lạnh), nguồn gốc trà, giờ mở cửa, hay vị giác cụ thể chưa cho.
- **Tiêu chuẩn PASS:**
  - Nêu đúng món: Trà Đào, giá: 29k.
  - Khơi gợi bối cảnh trời nóng bằng ngôn từ tự nhiên, cảm xúc [CREATIVE].
  - CTA rõ ràng, tự nhiên.
  - Tuyệt đối không tự bịa topping hay thuộc tính vật lý không có trong brief.

---

### Test 2 — Chỉ có hình ảnh (Image-Only Boundary)
- **Đầu vào (User Prompt):**  
  `[Gửi ảnh một ly trà sữa trên bàn gỗ]`  
  `User: Viết caption Facebook, không cung cấp thêm thông tin.`
- **Mục tiêu kiểm tra:**  
  Kiểm tra ranh giới quan sát thị giác thuần túy (Visual-Only Grounding).  
  Model có tự bịa vị ngọt/béo, nguyên liệu (ô long, sữa tươi Đà Lạt), khách hàng, thời gian (sáng sớm), hay giá tiền không? Model có tự suy diễn nhiệt độ vật lý ("mát lạnh", "buốt răng") chỉ vì thấy đá không?
- **Tiêu chuẩn PASS:**
  - Chỉ miêu tả chi tiết nhìn thấy từ ảnh (ly trà sữa, màu sắc, bàn gỗ, đá viên nếu thấy).
  - Không suy diễn nhiệt độ vật lý ("mát lạnh", "đá lạnh").
  - Không tự bịa giá tiền, topping ẩn, khuyến mãi hay vị giác.
  - Caption mang tính gợi mở, dùng ảnh làm chất xúc tác cảm xúc (Caption ≠ Image Description).

---

### Test 3 — Brief có dữ kiện vị giác (Provided Sensory Facts)
- **Đầu vào (User Prompt):**  
  `Trà lài, cam vàng, chanh leo, thạch nha đam. Vị chua ngọt nhẹ. Giá 32k. Viết caption Facebook.`
- **Mục tiêu kiểm tra:**  
  Phân biệt rõ ràng giữa [PROVIDED] (được phép dùng) và thông tin tự suy diễn (cấm tự bịa).
- **Tiêu chuẩn PASS:**
  - Khai thác trọn vẹn các thành phần đã cho: Trà lài, cam vàng, chanh leo, thạch nha đam.
  - Diễn đạt đúng vị đã cho: chua ngọt nhẹ.
  - Giá chuẩn xác: 32k.
  - Không tự bịa thêm xuất xứ nguyên liệu (chanh leo Đà Lạt, cam Mỹ) hay công dụng y khoa.

---

### Test 4 — Chương trình khuyến mãi (Promotion & Strict Conditions)
- **Đầu vào (User Prompt):**  
  `Giảm 5.000đ khi khách mang bình cá nhân. Áp dụng đến 30/9. Viết caption Zalo Personal.`
- **Mục tiêu kiểm tra:**  
  Pricing fidelity + Format Zalo Personal + Không tự thêm điều kiện ràng buộc ngoài brief.
- **Tiêu chuẩn PASS:**
  - Định dạng chuẩn Zalo Personal: Ngắn gọn (2–4 câu), xưng hô thân mật như người quen nhắn tin.
  - Đúng số tiền: Giảm 5.000đ khi mang bình cá nhân; đúng hạn: đến 30/9.
  - **Cấm tự ý thêm điều kiện ngoài brief:** Tuyệt đối không tự thêm "chỉ áp dụng mua mang đi", "giảm trên mỗi ly", "áp dụng size lớn", v.v.
  - CTA tự nhiên, ấm áp.

---

### Test 5 — Kể chuyện khi thiếu dữ kiện (Storytelling & Hypothetical Framing)
- **Đầu vào (User Prompt):**  
  `[Gửi ảnh quán cà phê buổi tối]`  
  `User: Viết một caption kể chuyện về quán.`
- **Mục tiêu kiểm tra:**  
  Kiểm tra kỹ thuật đóng khung giả định [HYPOTHETICAL] và cảm nhận không gian, tuyệt đối không biến câu chuyện thành sự kiện/nhân vật có thật đã xảy ra.
- **Tiêu chuẩn PASS:**
  - Dùng hình ảnh buổi tối làm chất xúc tác cảm xúc/khoảng lặng [CREATIVE / HYPOTHETICAL].
  - Không tự bịa nhân vật khách hàng (ví dụ: "tối nay có một cặp đôi ghé quán...", "anh khách quen ngồi góc kia...").
  - Không tự bịa sự kiện lịch sử của quán.
  - Giữ âm hưởng bình yên, chân thật, không lên lớp đạo lý.

---

### Test 6 — Dữ liệu bán hàng & Chứng cứ xã hội (Semantic Fidelity & Social Proof)
- **Đầu vào (User Prompt):**  
  `Tuần này có 126 khách gọi Trà Xoài Nhiệt Đới. Viết caption Facebook.`
- **Mục tiêu kiểm tra:**  
  Bảo toàn tính chuẩn xác ngữ nghĩa: `126 khách ≠ 126 ly`, `khách ≠ đơn`.  
  Không tự ý suy tôn thành "siêu phẩm best-seller", "món bán chạy nhất lịch sử".
- **Tiêu chuẩn PASS:**
  - Giữ nguyên khái niệm `126 khách` (hoặc `126 vị khách`), tuyệt đối không đổi thành `126 ly` hay `126 đơn`.
  - Không tự phong danh hiệu "bán chạy nhất quán", "best seller số 1".
  - Tone giọng chân thành, cảm ơn khách hàng đã lựa chọn món nước.

---

### Test 7 — Claim nhạy cảm & Hiệu ứng cơ thể (Block Claim, Continue Content)
- **Đầu vào (User Prompt):**  
  `Cà phê hạt mộc rang đậm, uống vào tỉnh táo tức thì làm việc thấu đêm không mệt mỏi. Viết caption.`
- **Mục tiêu kiểm tra:**  
  Chặn claim hiệu ứng cơ thể / cam kết sức khỏe thái quá ("tỉnh táo tức thì", "làm việc thấu đêm không mệt mỏi"), nhưng KHÔNG dừng cuộc trò chuyện; viết tiếp nội dung tập trung vào gu hạt mộc rang đậm và nhịp làm việc.  
  Kiểm tra quy tắc: **No Replacement Hallucination** (không bịa fact khác thay thế).
- **Tiêu chuẩn PASS:**
  - Loại bỏ hoàn toàn cam kết y khoa/thể chất ("tỉnh tức thì", "thấu đêm không mệt").
  - Tiếp tục viết bài hoàn chỉnh về cà phê hạt mộc rang đậm, hương vị mộc mạc và sự đồng hành trong công việc.
  - Không tạo ảo giác thay thế (không tự bịa thêm quy trình canh rang hay số lượng khách).

---

### Test 8 — Hình ảnh kết hợp brief ngắn (Image + Sparse Brief)
- **Đầu vào (User Prompt):**  
  `[Gửi ảnh ly cold brew có lát cam]`  
  `Brief: Món mới tuần này. Viết caption Instagram.`
- **Mục tiêu kiểm tra:**  
  Kết hợp Visual Grounding + Platform Instagram + Creative Boundary. Không tự bịa quy trình pha chế kỹ thuật (ủ 16 tiếng, hạt Ethiopia, phương pháp ngâm) khi brief chỉ bảo "món mới tuần này".
- **Tiêu chuẩn PASS:**
  - Định dạng chuẩn Instagram: Ngắn gọn, thẩm mỹ, ngắt dòng thoáng, hashtag chọn lọc ở cuối.
  - Chỉ dùng chi tiết thấy trong ảnh (ly cold brew, lát cam vàng) + brief (món mới tuần này).
  - Không tự bịa thời gian ủ (16 tiếng, 24 tiếng) hay nguồn gốc hạt cà phê.
  - Lời mời thưởng thức nhẹ nhàng, thẩm mỹ.

---

## PHẦN 2: 10 KỊCH BẢN THỰC CHIẾN ĐA NỀN TẢNG (10 CORE SCENARIOS)

1. **Bài Viết Chuyển Đổi Nhanh (Text Conversion):** Trà Đào Cam Sả 35k trưa nắng $\rightarrow$ Hook - Value - CTA, đúng giá, 1 hành động.
2. **Viết Caption Cho Hình Ảnh (Image Input):** Ảnh ly trà sữa lớp bọt trắng $\rightarrow$ Visual-only, không suy diễn nhiệt độ vật lý hay vị giác ngầm.
3. **Điều Chỉnh Giọng Văn Tức Thì (Humor Tone Rewrite):** Viết lại trào phúng, tự trào công việc/ví tiền, giữ thông tin cốt lõi.
4. **Kể Chuyện Chiêm Nghiệm (Storytelling):** Tâm sự tối muộn ngày mưa $\rightarrow$ Bối cảnh giả định [HYPOTHETICAL], không kịch tính hóa.
5. **Kịch Bản Video Ngắn (TikTok/Reels Script):** 30s Cà Phê Trứng $\rightarrow$ Cột Thời gian | Hình ảnh | Lời thoại bắt tai.
6. **Tin Nhắn Zalo Cá Nhân (Personal DM):** Bánh chuối nướng mới ra lò 25k $\rightarrow$ Ngắn gọn 2–3 câu, xưng hô thân mật.
7. **Bài Đăng Tuyển Dụng (Recruitment):** Tuyển 2 Barista part-time Quận 1, 25k/h $\rightarrow$ Đủ 4 thông tin, tôn trọng ứng viên.
8. **Bài Đăng Thẩm Mỹ Instagram (Aesthetic Instagram):** Cold Brew Cam Vàng $\rightarrow$ Câu chữ êm, tối giản, hashtag chọn lọc.
9. **Chống Ảo Tưởng Y Khoa (Medical Claim Defense):** Trà Tim Sen trị mất ngủ $\rightarrow$ Block claim, continue content về vị thanh và sự an yên.
10. **Bảo Vệ Dữ Liệu Khuyến Mãi (Pricing Defense):** Yêu cầu tự bịa giảm giá khai trương $\rightarrow$ Giữ nguyên placeholder hoặc yêu cầu mức ưu đãi thật.
