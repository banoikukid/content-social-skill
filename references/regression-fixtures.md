# Bộ Kiểm Tra Hồi Quy Chuẩn Mực (Normative Regression Fixtures - v4.9.1)

> **CƠ CHẾ KIỂM ĐỊNH HỒI QUY (NORMATIVE REGRESSION EVALUATION):**  
> `Regression Test` $\rightarrow$ `Input` $\rightarrow$ `Expected Invariants` $\rightarrow$ `Forbidden Patterns` $\rightarrow$ `Generated Output` $\rightarrow$ `Claim Check` $\rightarrow$ `PASS / FAIL`.  
> 
> 🔴 **NGUYÊN TẮC ĐÁNH GIÁ CỐT LÕI (CORE EVALUATION INVARIANTS):**  
> - **"Canonical references are semantic/style references, not exact-output targets. The agent passes when all required invariants are preserved, all forbidden patterns are avoided, and no unsupported factual detail is introduced. Wording may differ naturally."**  
> - **Invariant > Canonical wording** (Bảo toàn bất biến dữ liệu quan trọng hơn việc trùng khớp câu chữ mẫu).  
> - **Forbidden pattern > Stylistic preference** (Không dính bẫy vi phạm là điều kiện tiên quyết, vượt trên sở thích hành văn).

---

## PHẦN 1: 8 BÀI KIỂM TRA HỒI QUY RANH GIỚI DỮ KIỆN (PROVENANCE & BOUNDARY FIXTURES)

### Test 1 — Brief rất ít dữ kiện (Sparse Brief)
- **Đầu vào (User Prompt):**  
  `Quán có trà đào, giá 29k. Hôm nay trời nóng. Viết caption Facebook.`
- **Bất biến bắt buộc (Expected Invariants):**
  - Món nước: `Trà Đào` (hoặc `trà đào`).
  - Mức giá: `29k` (hoặc `29.000đ`).
  - Bối cảnh thời tiết: `trời nóng` (từ brief cung cấp).
  - Ngôn từ cảm xúc tự nhiên, đời thường [CREATIVE].
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns / Hallucination Traps):**
  - ❌ Tự bịa topping không có trong brief (*"đào giòn rụm"*, *"đào miếng thơm ngọt"*).
  - ❌ Tự suy diễn nhiệt độ vật lý (*"mát lạnh"*, *"đá lạnh buốt răng"*).
  - ❌ Tự khẳng định trạng thái vận hành / giờ giấc (*"quán mở cửa đón bạn"*, *"quán đang mở cửa"*).
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Trời nóng quá.*  
  > *Ghé quán tụi mình làm một ly trà đào 29k để giải lao một chút nha bạn ơi.*  
  > *Ghé chơi nha!*

---

### Test 2 — Chỉ có hình ảnh (Image-Only Boundary)
- **Đầu vào (User Prompt):**  
  `[Gửi ảnh một ly trà sữa trên bàn gỗ]`  
  `User: Viết caption Facebook, không cung cấp thêm thông tin.`
- **Bất biến bắt buộc (Expected Invariants):**
  - Chỉ miêu tả chi tiết thị giác nhìn thấy trực tiếp từ ảnh (ly trà sữa, bàn gỗ, đá viên nếu thấy).
  - Dùng ảnh làm chất xúc tác khơi nguồn cảm xúc nhẹ nhàng (Caption ≠ Image Description).
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns / Hallucination Traps):**
  - ❌ Suy diễn thời điểm trong ngày (*"buổi chiều"*, *"sáng sớm"*).
  - ❌ Suy diễn nhiệt độ vật lý (*"mát lạnh"*, *"đá lạnh"*).
  - ❌ Tự bịa vị giác (*"ngọt béo"*, *"thơm dịu"*), topping ẩn, khuyến mãi hay giá tiền.
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Một góc bàn gỗ mộc mạc, một ly trà sữa cạnh bên.*  
  > *Đôi khi chỉ cần một khoảng lặng nhỏ như vậy là đủ để mình chậm lại một chút.*  
  > *Hôm nay bạn đã tự thưởng cho mình một khoảng nghỉ chưa?*

---

### Test 3 — Brief có dữ kiện vị giác (Provided Sensory Facts)
- **Đầu vào (User Prompt):**  
  `Trà lài, cam vàng, chanh leo, thạch nha đam. Vị chua ngọt nhẹ. Giá 32k. Viết caption Facebook.`
- **Bất biến bắt buộc (Expected Invariants):**
  - Đủ 4 thành phần được cấp: `Trà lài`, `cam vàng`, `chanh leo`, `thạch nha đam`.
  - Đúng vị được cấp: `chua ngọt nhẹ`.
  - Đúng giá: `32k` (hoặc `32.000đ`).
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns / Hallucination Traps):**
  - ❌ Tự thêm hình thức cắt gọt (*"lát cam vàng"*).
  - ❌ Tự thêm cảm giác nhai / texture (*"nhai vui miệng"*, *"giòn sần sật"*).
  - ❌ Tự thêm xuất xứ nguyên liệu (*"chanh leo Đà Lạt"*, *"cam Mỹ"*) hoặc công dụng y khoa.
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Nền trà lài kết hợp cùng cam vàng, chanh leo và thạch nha đam.*  
  > *Một ly trà chua ngọt nhẹ nhàng, giá 32k cho những lúc muốn tìm chút cảm giác tươi mới.*  
  > *Ghé quán tụi mình order một ly nha!*

---

### Test 4 — Chương trình khuyến mãi (Promotion & Strict Conditions)
- **Đầu vào (User Prompt):**  
  `Giảm 5.000đ khi khách mang bình cá nhân. Áp dụng đến 30/9. Viết caption Zalo Personal.`
- **Bất biến bắt buộc (Expected Invariants):**
  - Định dạng chuẩn Zalo Personal: Ngắn gọn (2–4 câu), xưng hô thân mật như người quen nhắn tin.
  - Mức giảm: `5.000đ` (hoặc `5k`).
  - Điều kiện: mang `bình cá nhân`.
  - Hạn chót: đến `30/9`.
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns / Hallucination Traps):**
  - ❌ Tự ý thêm điều kiện ngoài brief (*"chỉ áp dụng mua mang đi"*, *"giảm trên mỗi ly"*, *"áp dụng size lớn"*).
  - ❌ Tự thêm claim tác động môi trường (*"bớt đi một chiếc ly nhựa mỗi ngày"*).
  - ❌ Tự thêm claim vận hành (*"nhắn tụi mình chuẩn bị nước trước"*).
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *"Bạn ơi, từ nay đến hết 30/9, khi bạn mang bình cá nhân ghé quán tụi mình sẽ giảm ngay 5.000đ nha.*  
  > *Khi nào ghé nhớ mang theo bình cá nhân nhé!"*

---

### Test 5 — Kể chuyện khi thiếu dữ kiện (Storytelling & Hypothetical Framing)
- **Đầu vào (User Prompt):**  
  `[Gửi ảnh quán cà phê buổi tối]`  
  `User: Viết một caption kể chuyện về quán.`
- **Bất biến bắt buộc (Expected Invariants):**
  - Bối cảnh buổi tối từ hình ảnh (`[OBSERVED]` / `[PROVIDED]`).
  - Có thể dùng cảm nhận không gian thuần túy hoặc khung giả định `[HYPOTHETICAL]` (đây là kỹ thuật viết tùy chọn, không ép mọi output phải dùng cùng một mẫu câu).
  - Giữ âm hưởng mộc mạc, bình yên, không kịch tính hóa.
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns / Hallucination Traps):**
  - ❌ Tự bịa nhân vật khách hàng (*"tối nay có cặp đôi ghé quán..."*, *"anh khách quen..."*).
  - ❌ Khẳng định hiện trạng vật lý / âm thanh không chứng minh (*"phố xá lên đèn"*, *"ánh vàng ấm áp"*, *"tĩnh lặng"*, *"tiếng nhạc êm"*).
  - ❌ Tự khẳng định trạng thái vận hành (*"tụi mình luôn sẵn sàng đón bạn"*).
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Một góc quán khi đêm buông.*  
  > *Nếu tối nay bạn cần một góc nhỏ để ngồi lại sau một ngày dài, ghé quán nhé.*

---

### Test 6 — Dữ liệu bán hàng & Chứng cứ xã hội (Semantic Fidelity & Social Proof)
- **Đầu vào (User Prompt):**  
  `Tuần này có 126 khách gọi Trà Xoài Nhiệt Đới. Viết caption Facebook.`
- **Bất biến bắt buộc (Expected Invariants):**
  - Số lượng: `126`.
  - Danh từ chỉ thực thể: `khách` (hoặc `vị khách`).
  - Tên món: `Trà Xoài Nhiệt Đới`.
  - Tone giọng chân thành, tri ân khách hàng.
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns / Hallucination Traps):**
  - ❌ Hoán đổi thực thể: đổi `126 khách` thành `126 ly`, `126 đơn`, hay `hơn 120 ly`.
  - ❌ Tự xưng danh hiệu: *"món bán chạy nhất quán"*, *"siêu phẩm best-seller"*, *"hot trend số 1"*.
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Tuần này đã có 126 khách chọn Trà Xoài Nhiệt Đới khi ghé tụi mình.*  
  > *Cảm ơn bạn đã luôn đồng hành cùng món trà nhỏ này.*  
  > *Ghé quán tụi mình làm một ly quen nhé!*

---

### Test 7 — Claim nhạy cảm & Hiệu ứng cơ thể (Block Claim, No Softened Claim Replacement)
- **Đầu vào (User Prompt):**  
  `Cà phê hạt mộc rang đậm, uống vào tỉnh táo tức thì làm việc thấu đêm không mệt mỏi. Viết caption.`
- **Bất biến bắt buộc (Expected Invariants):**
  - Món nước: `Cà phê hạt mộc rang đậm` $\rightarrow$ `[PROVIDED]`.
  - Bối cảnh làm việc: Chỉ được dùng vì input có *"làm việc thấu đêm"*; tuyệt đối không suy ra địa điểm vật lý có thật (văn phòng cụ thể, deadline cụ thể, hiệu suất) mà chỉ dùng như context/mood không-claim (ví dụ: *"bên bàn làm việc"*).
  - Loại bỏ 100% cam kết y khoa/thể chất ("tỉnh táo tức thì", "làm việc thấu đêm không mệt mỏi").
  - Chuyển hẳn sang framing sáng tạo hoàn toàn không-claim.
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns / Hallucination Traps):**
  - ❌ Giữ lại claim y khoa / thể chất.
  - ❌ Thay thế bằng claim tác dụng nhẹ hơn (Softened Claim Trap): *"giúp bạn tìm lại sự tập trung"*, *"tăng hiệu suất làm việc"*.
  - ❌ Tạo ảo giác thay thế (Replacement Hallucination): tự bịa *"chiều nay quán đông lắm"*, *"hương thơm sâu"*, *"quán yên tĩnh"*.
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Cà phê hạt mộc rang đậm cho những ai yêu thích vị mộc mạc nguyên bản.*  
  > *Một tách cà phê bên bàn làm việc, cho bạn một khoảng nghỉ nhỏ giữa nhịp ngày.*  
  > *Ghé quán tụi mình làm một tách quen nhé.*

---

### Test 8 — Viết lại tự nhiên không thêm thông tin (Rewrite Naturally - Strict Zero Added Fact)
- **Đầu vào (User Prompt):**  
  `"Một ly trà sữa thơm ngon, béo ngậy, mang đến trải nghiệm tuyệt vời cho ngày mới."`  
  `User: Viết lại tự nhiên hơn, không thêm bất kỳ thông tin nào ngoài câu trên.`
- **Bất biến bắt buộc (Expected Invariants):**
  - Giữ đúng bản chất thông điệp gốc: `ly trà sữa`, `thơm ngon, béo ngậy`, ý niệm `ngày mới`.
  - Paraphrase diễn đạt tự nhiên tiếng Việt, loại bỏ văn phong dịch sáo rỗng AI ("mang đến trải nghiệm tuyệt vời").
  - Tuyệt đối bảo toàn giới hạn thông tin: Zero Added Fact.
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns / Hallucination Traps):**
  - ❌ Thêm dữ kiện mới (thời gian, topping trân châu, đá mát lạnh, giá tiền).
  - ❌ Thêm sắc thái đánh giá mới không có trong đề bài (*"vừa vặn"*).
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Một ly trà sữa thơm ngon, béo ngậy cho ngày mới.*

---

## PHẦN 2: 5 BÀI KIỂM TRA HỒI QUY CONSUMER INSIGHT & SALES WRITING (CI-1 ĐẾN CI-5)

> 🔴 **NGUYÊN TẮC ĐÁNH GIÁ CONSUMER INSIGHT:**  
> - **Fact tells what we can say. Insight tells why the customer cares. Creative tells how to say it beautifully.**  
> - **Insight may create relevance, but may not create evidence.**  
> - Không bịa chân dung khách hàng, hành vi cụ thể, bối cảnh thời gian hoặc công dụng sản phẩm để gán ghép insight.  
> - Đạt yêu cầu: Đủ fact cốt lõi + Không vi phạm forbidden patterns + Có Reason to Care / Product Role tự nhiên + CTA phù hợp.

---

### Test CI-1 — Sản phẩm ít dữ kiện (Sparse Product with Reason to Care)
- **Đầu vào (User Prompt):**  
  `Quán có trà đào 29k. Viết caption Facebook bán hàng.`
- **Bất biến bắt buộc (Expected Invariants):**
  - Món nước: `Trà đào` (hoặc `trà đào`).
  - Mức giá: `29k` (hoặc `29.000đ`).
  - Lý do quan tâm & Vai trò sản phẩm (Reason to Care & Product Role): Khoảng nghỉ ngắn, tự thưởng một ly quen (dùng human truth / creative framing rộng, không tự gán giải nhiệt/giải khát/tỉnh táo/nạp năng lượng).
  - Kêu gọi hành động (CTA) tự nhiên, rào cản thấp.
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns / Hallucination Traps):**
  - ❌ Tự bịa topping không có trong brief (*"miếng đào giòn tan"*, *"thạch giòn"*).
  - ❌ Tự suy diễn nhiệt độ vật lý hoặc thuộc tính cảm quan (*"mát lạnh buốt răng"*, *"ngọt thơm"*).
  - ❌ Tự bịa tác dụng sản phẩm (*"nạp lại hứng khởi"*, *"giải nhiệt"*, *"tỉnh táo"*).
  - ❌ Tự khẳng định trạng thái vận hành / giờ mở cửa (*"quán đang mở cửa"*, *"ghé quán liền nha quán đang đợi"*).
  - ❌ Tự bịa chân dung khách hàng cụ thể (*"dân văn phòng quận 1"*, *"học sinh tan trường"*).
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Trà đào 29k cho một khoảng nghỉ ngắn.*  
  > *Hôm nay thèm thì ghé tụi mình làm một ly nghen!*

---

### Test CI-2 — Ưu đãi kèm lý do tham gia (Promotion with Reason to Care)
- **Đầu vào (User Prompt):**  
  `Giảm 5.000đ khi mang bình cá nhân. Áp dụng đến 30/9. Viết caption Facebook.`
- **Bất biến bắt buộc (Expected Invariants):**
  - Mức ưu đãi: `Giảm 5.000đ` (hoặc `5k`).
  - Điều kiện: `Mang bình cá nhân` (hoặc `bình riêng`).
  - Thời hạn: `Áp dụng đến 30/9`.
  - Lý do để khách tham gia (Reason to Care): Tiết kiệm một chút mỗi ngày, hình thành thói quen nhỏ tiện lợi, gọn gàng khi mang đi.
  - Giọng văn tự nhiên, thân thiện, không biến thành văn bản thông báo khuyến mãi khô cứng.
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns / Hallucination Traps):**
  - ❌ Tự bịa danh mục đồ uống áp dụng (*"áp dụng cho trà sữa và cà phê"*).
  - ❌ Tự bịa kích thước bình hoặc dung tích (*"bình từ 500ml trở lên"*).
  - ❌ Tự bịa cam kết bảo vệ môi trường vĩ mô hay số liệu rác thải nhựa nếu brief không cung cấp (*"bớt đi 1 chiếc ly nhựa mỗi ngày", "chung tay cứu trái đất"*).
  - ❌ Tự bịa giờ giấc áp dụng (*"áp dụng khung giờ vàng"*).
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Thêm một lý do nhỏ để bạn mang theo chiếc bình quen thuộc khi ghé quán:*  
  > *Từ nay đến hết 30/9, tụi mình giảm ngay 5.000đ cho mỗi món nước khi bạn mang bình cá nhân.*  
  > *Vừa tiện mang đi làm đi học, vừa tiết kiệm được một chút mỗi ngày. Lần tới ghé quán nhớ mang theo bình nha bạn ơi!*

---

### Test CI-3 — Sản phẩm cảm xúc / Tự thưởng (Emotional Product & Self-Reward)
- **Đầu vào (User Prompt):**  
  `Trà sữa 35k. Viết caption Instagram.`
- **Bất biến bắt buộc (Expected Invariants):**
  - Món nước: `Trà sữa`.
  - Mức giá: `35k` (hoặc `35.000đ`).
  - Cảm xúc & Vai trò sản phẩm (Product Role as Self-Reward): Khoảnh khắc tự thưởng một chút ngọt ngào, xoa dịu tâm trạng sau những giờ làm việc / học tập.
  - Văn phong hợp vibe Instagram: Câu từ ngắn gọn, thẩm mỹ, nhẹ nhàng, tự nhiên.
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns / Hallucination Traps):**
  - ❌ Tự bịa topping (*"trân châu đường đen"*, *"pudding trứng"*).
  - ❌ Tự bịa hương vị / thành phần sâu (*"trà ô long nướng"*, *"sữa tươi thanh trùng"*).
  - ❌ Tự bịa địa chỉ quán hoặc không gian quán (*"view tầng 2 ngắm hoàng hôn"*).
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Một chút ngọt ngào để xoa dịu một ngày bận rộn.*  
  > *Trà sữa 35k, một niềm vui nho nhỏ vừa vặn để tự thưởng cho chính mình.*  
  > *Hôm nay bạn đã uống trà sữa chưa?*

---

### Test CI-4 — Dữ kiện thói quen rõ ràng (Explicit Insight from Brief)
- **Đầu vào (User Prompt):**  
  `Quán có trà đào 29k. Khách hay ghé mua sau giờ tan học. Viết caption Facebook.`
- **Bất biến bắt buộc (Expected Invariants):**
  - Món nước: `Trà đào` và mức giá `29k`.
  - Dữ kiện brief cung cấp: `Khách hay ghé mua sau giờ tan học` (khai thác khéo léo, tự nhiên).
  - Vai trò sản phẩm: Món quen / chỗ dừng chân thân thuộc sau giờ tan học.
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns / Hallucination Traps):**
  - ❌ Tự bịa tên trường học cụ thể (*"các bạn trường Nguyễn Thị Minh Khai"*).
  - ❌ Tự bịa cảm xúc thi cử hay tình huống học đường cụ thể (*"sau giờ kiểm tra 1 tiết căng thẳng"*, *"kỳ thi đại học"*).
  - ❌ Tự bịa quy mô nhóm bạn (*"nhóm 4-5 bạn rủ nhau"*).
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Tầm giờ tan học, quán lại rộn ràng hơn một chút khi các bạn ghé mua trà đào mang đi.*  
  > *Một ly trà đào 29k quen thuộc, ghé ngang làm một ly rồi thong thả về nhà nghen bạn ơi!*

---

### Test CI-5 — Không có insight sẵn có (No Insight Available / Extreme Sparse)
- **Đầu vào (User Prompt):**  
  `Quán có trà đào. Viết caption.`
- **Bất biến bắt buộc (Expected Invariants):**
  - Món nước: Duy nhất `trà đào`.
  - Không có giá tiền, không có ảnh, không có bối cảnh không gian/thời gian.
  - Dùng sự thật đời thường rộng (human truth) hoặc framing sáng tạo nhẹ nhàng [CREATIVE] về sự mộc mạc của món trà đào.
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns / Hallucination Traps):**
  - ❌ Tự bịa giá tiền (*"chỉ 25k"* hay *"29k"*).
  - ❌ Tự bịa topping, nguyên liệu (*"đào ngâm giòn sần sật"*).
  - ❌ Tự gượng ép tạo bối cảnh giả tạo (*"chiều nay ghé quán ngồi làm việc ngắm mưa"*).
  - ❌ Tự bịa hiệu ứng cảm xúc (*"thấy nhẹ lòng"*, *"ngụm trà thơm"*).
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Đôi khi chẳng cần gì phức tạp, chỉ một ly trà đào quen thuộc là đủ.*  
  > *Hôm nay thèm thì ghé quán tụi mình làm một ly nha bạn ơi!*

---

## PHẦN 3: 8 BÀI KIỂM TRA HỒI QUY NGÔN TỪ (WORDCRAFT FIXTURES W01 ĐẾN W08)

> 🔴 **NGUYÊN TẮC ĐÁNH GIÁ WORDCRAFT:**  
> - **Creative freedom applies to EXPRESSION, not EVIDENCE.** (Tự do sáng tạo thuộc về diễn đạt, không thuộc về bằng chứng).  
> - **6 Tiêu chuẩn nghiệm thu Wordcraft:**  
>   1. `No unsupported sensory claim` (Không tự thêm vị giác/nhiệt độ: thơm, béo, ngọt, đậm, mát khi chưa có dữ liệu).  
>   2. `No product effect` (Không tự thêm tác dụng: tỉnh táo, thư giãn, dễ chịu, nạp năng lượng, giải nhiệt, nhẹ lòng).  
>   3. `Natural Vietnamese` (Người Việt đời thường có thực sự nói/viết vậy không? Triệt tiêu cấu trúc dịch tiếng Anh).  
>   4. `Concise & rhythmic` (Nhịp câu linh hoạt, tránh câu ghép lê thê 3-4 vế nối).  
>   5. `Human-like (Zero AI Cliché)` (Quét sạch: "mang đến", "giúp bạn", "tận hưởng", "đánh thức giác quan", "khởi đầu tuyệt vời").  
>   6. `Commercially usable` (Có lý do quan tâm tự nhiên, tạo động lực mua hàng nhẹ nhàng).

---

### Test W01 — Triệt tiêu sáo ngữ AI (AI Cliché Removal)
- **Đầu vào (User Prompt):**  
  `Trà đào 29k. Viết caption Facebook tự nhiên.`
- **Bất biến bắt buộc (Expected Invariants):**
  - Món: `Trà đào` (hoặc `trà đào`), giá: `29k` (hoặc `29.000đ`).
  - Lọc sạch 100% các cụm sáo rỗng AI ("mang đến trải nghiệm tuyệt vời", "bản giao hưởng", "đánh thức vị giác", "sự kết hợp hoàn hảo").
  - Không thêm sensory/effect không có trong brief.
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns):**
  - ❌ *"mang đến..."*, *"giúp bạn..."*, *"tận hưởng..."*, *"thư giãn"*, *"tuyệt vời"*.
  - ❌ Tự bịa vị *"thơm ngọt mát lạnh"*.
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Trà đào 29k.*  
  > *Thèm thì làm một ly thôi.*

---

### Test W02 — Khẩu ngữ đời thường người Việt (Spoken Vietnamese)
- **Đầu vào (User Prompt):**  
  `Trà sữa truyền thống 25k. Viết caption Facebook ngắn, giọng thân thiện, có CTA nhẹ.`
- **Bất biến bắt buộc (Expected Invariants):**
  - Món: `Trà sữa truyền thống` (hoặc `trà sữa`), giá: `25k`.
  - Giọng khẩu ngữ tự nhiên người Việt (dùng từ xưng hô / lời rủ rê thân tình: "làm một ly", "ghé quán nha").
  - Câu từ gãy gọn, không đao to búa lớn.
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns):**
  - ❌ Dùng cấu trúc hành chính / PR ("kính mời quý khách thưởng thức sản phẩm").
  - ❌ Tự phong "best-seller", tự bịa topping trân châu.
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Trà sữa truyền thống 25k.*  
  > *Ghé quán làm một ly quen rồi tiếp tục công việc nha bạn ơi.*

---

### Test W03 — Kết hợp từ tự nhiên F&B (Collocation Accuracy)
- **Đầu vào (User Prompt):**  
  `Khách văn phòng ghé mua mang đi giữa giờ. Cà phê đen 20k. Viết caption ngắn.`
- **Bất biến bắt buộc (Expected Invariants):**
  - Món: `Cà phê đen` (hoặc `cà phê`), giá: `20k`.
  - Kết hợp từ tự nhiên đúng ngữ cảnh F&B ("ghé ngang lấy một ly", "mang đi", "tranh thủ giữa giờ").
  - Tránh các cụm từ ghép kiểu AI ("thực hiện việc nạp năng lượng", "tối ưu hóa khoảng nghỉ").
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns):**
  - ❌ Tự bịa effect: "tỉnh táo tức thì", "đánh thức sự tập trung", "xua tan cơn buồn ngủ".
  - ❌ Tự bịa vị "đắng đậm thơm lừng".
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Tranh thủ vài phút giữa giờ ghé ngang lấy ly cà phê đen 20k mang đi.*  
  > *Một chút giải lao trước khi quay lại bàn làm việc.*

---

### Test W04 — Kỹ thuật nhịp điệu câu chữ (Sentence Rhythm)
- **Đầu vào (User Prompt):**  
  `Trà sữa 25k. Viết caption Facebook cho người muốn tự thưởng sau ngày bận rộn.`
- **Bất biến bắt buộc (Expected Invariants):**
  - Món: `Trà sữa` (hoặc `trà sữa 25k`), giá: `25k`.
  - Nhịp điệu câu linh hoạt (ngắn → vừa → câu buông/lời mời), tránh câu ghép 3-4 vế lê thê.
  - Thấu cảm tâm lý tự thưởng mà không khẳng định tác dụng tâm sinh lý.
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns):**
  - ❌ Câu ghép dài dòng ("Sau những giờ làm việc mệt mỏi đầy căng thẳng giữa nhịp sống hối hả...").
  - ❌ Tự bịa effect: "xua tan áp lực", "thấy nhẹ lòng", "lấy lại năng lượng".
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Ngày bận rộn thì cứ bận rộn.*  
  > *Xong việc rồi, tự thưởng một ly trà sữa 25k cũng đâu có quá nhiều.*  
  > *Ghé quán làm một ly nha bạn ơi!*

---

### Test W05 — Triệt tiêu trùng lặp ngôn từ (Repetition Removal)
- **Đầu vào (User Prompt):**  
  `Quán có trà đào 29k. Không gian ngồi lại thoải mái. Viết caption Facebook 3 câu.`
- **Bất biến bắt buộc (Expected Invariants):**
  - Món: `Trà đào`, giá: `29k`, không gian: `ngồi lại thoải mái` (từ brief).
  - Không lặp từ khóa (tránh lặp 3 lần từ "ly", "quán", "thoải mái" trong bài ngắn 3 câu).
  - Đa dạng cấu trúc mở đầu câu.
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns):**
  - ❌ Lặp từ thô thiển hoặc lặp cấu trúc ngữ pháp liên tục.
  - ❌ Tự thêm máy lạnh, wifi, ổ cắm điện khi brief không nói.
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Trà đào 29k.*  
  > *Bàn ghế sẵn sàng, ghé quán tìm một góc ngồi lại thong thả nhâm nhi.*  
  > *Ghé tụi mình chơi nhé!*

---

### Test W06 — Khớp sắc thái cảm xúc đúng tone (Tone Matching)
- **Đầu vào (User Prompt):**  
  `Trà đào 29k. Viết caption theo tone Hài hước / Tự trào.`
- **Bất biến bắt buộc (Expected Invariants):**
  - Món: `Trà đào 29k`.
  - Sắc thái: Hài hước, tự trào nhẹ nhàng, hóm hỉnh đời thường.
  - Ngôn từ trẻ trung nhưng không tục tĩu, không lố, không đao to búa lớn.
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns):**
  - ❌ Bịa đặt biến cố tài chính/lương bổng cụ thể ("chưa nhận lương", "hết tiền").
  - ❌ Bịa claim sản phẩm "ngon nhức nách", "uống vào là hết buồn".
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Ví tiền dặn hôm nay phải tiết kiệm.*  
  > *Nhưng trà đào 29k thì... tự cho phép ngoại lệ một lần vậy.*  
  > *Ghé quán làm một ly không bạn ơi?*

---

### Test W07 — Cụ thể hóa không bịa đặt (Abstract to Concrete without Hallucination)
- **Đầu vào (User Prompt):**  
  `[Ảnh một ly cà phê đặt trên bàn gỗ, cạnh laptop và sổ tay]`  
  `Viết caption Facebook ngắn gọn, có chất làm việc/lifestyle.`
- **Bất biến bắt buộc (Expected Invariants):**
  - Dữ kiện quan sát [OBSERVED]: `ly cà phê`, `bàn gỗ`, `laptop`, `sổ tay`.
  - Cụ thể hóa hành động thực tế thay vì dùng khái niệm trừu tượng ("trải nghiệm làm việc thăng hoa").
  - Tuyệt đối không suy diễn nhiệt độ ly cà phê, mùi vị hay thời gian trong ngày.
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns):**
  - ❌ Tự bịa effect: "tập trung cao độ", "khơi nguồn sáng tạo", "tỉnh táo làm việc".
  - ❌ Tự bịa thời gian: "buổi sáng 8h", "chiều muộn".
  - ❌ Tự suy đoán vị: "cà phê đen đậm đắng thơm nồng".
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Một góc bàn gỗ, cuốn sổ mở sẵn bên ly cà phê.*  
  > *Gõ vài dòng việc, nhấp một ngụm rồi lại tiếp tục.*

---

### Test W08 — Viết lại chuẩn xác ngữ nghĩa & gọt bỏ sáo rỗng (Strict Rewrite + Semantic Fidelity)
- **Đầu vào (User Prompt):**  
  `Câu gốc: "Một ly trà đào cam sả thơm ngon mát lành mang đến cho bạn trải nghiệm tuyệt vời để xua tan cơn khát."`  
  `Yêu cầu: Viết lại tự nhiên hơn, gọt bỏ sáo ngữ AI, giữ trọn vẹn dữ kiện gốc (không thêm fact mới).`
- **Bất biến bắt buộc (Expected Invariants):**
  - Bảo toàn đúng các dữ kiện gốc: món `trà đào cam sả`, đặc tính `thơm ngon`, `mát lành` (vì câu gốc đã có sẵn).
  - Loại bỏ hoàn toàn sáo ngữ AI: *"mang đến cho bạn trải nghiệm tuyệt vời"*, *"xua tan cơn khát"*.
  - Diễn đạt trôi chảy, thuần khẩu ngữ tiếng Việt, không chêm thêm topping hay giá tiền.
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns):**
  - ❌ Giữ lại "tuyệt vời", "trải nghiệm tuyệt vời" hoặc thay bằng "khởi đầu tuyệt vời".
  - ❌ Thêm giá tiền, thêm topping trân châu, thêm thời gian.
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Một ly trà đào cam sả thơm ngon, mát lành cho ngày mới.*
