# Bộ Kiểm Tra Hồi Quy Chuẩn Mực (Normative Regression Fixtures - v4.9.0)

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
  > *Một ly trà sữa thơm ngon, béo ngậy — khởi đầu tuyệt vời cho ngày mới.*

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
  - Lý do quan tâm & Vai trò sản phẩm (Reason to Care & Product Role): Giải khát, khoảng nghỉ ngơi nhẹ nhàng giữa ngày, phần thưởng nhỏ hạ nhiệt (dùng human truth / creative framing rộng).
  - Kêu gọi hành động (CTA) tự nhiên, rào cản thấp.
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns / Hallucination Traps):**
  - ❌ Tự bịa topping không có trong brief (*"miếng đào giòn tan"*, *"thạch giòn"*).
  - ❌ Tự suy diễn nhiệt độ vật lý hoặc thuộc tính cảm quan (*"mát lạnh buốt răng"*).
  - ❌ Tự khẳng định trạng thái vận hành / giờ mở cửa (*"quán đang mở cửa"*, *"ghé quán liền nha quán đang đợi"*).
  - ❌ Tự bịa chân dung khách hàng cụ thể (*"dân văn phòng quận 1"*, *"học sinh tan trường"*).
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Một ly trà đào 29k cho một khoảng nghỉ ngắn giữa ngày làm việc.*  
  > *Nếu bạn đang cần chút ngọt thơm để nạp lại hứng khởi, ghé quán tụi mình làm một ly nha bạn ơi!*

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
  - Vai trò sản phẩm: Món giải nhiệt / chỗ dừng chân thân thuộc sau giờ học tan trường.
- **Bẫy vi phạm cấm kỵ (Forbidden Patterns / Hallucination Traps):**
  - ❌ Tự bịa tên trường học cụ thể (*"các bạn trường Nguyễn Thị Minh Khai"*).
  - ❌ Tự bịa cảm xúc thi cử hay tình huống học đường cụ thể (*"sau giờ kiểm tra 1 tiết căng thẳng"*, *"kỳ thi đại học"*).
  - ❌ Tự bịa quy mô nhóm bạn (*"nhóm 4-5 bạn rủ nhau"*).
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Tầm giờ tan học, quán lại rộn ràng hơn một chút khi các bạn ghé mua trà đào mang đi.*  
  > *Một ly trà đào 29k vừa quen vừa mát lòng, ghé ngang làm một ly rồi thong thả về nhà nghen bạn ơi!*

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
- **Mẫu Output Chuẩn Tham Chiếu (Canonical Pass Reference):**
  > *Đôi khi không cần nghĩ ngợi quá nhiều, chỉ cần một ly trà đào quen thuộc là đủ thấy nhẹ lòng.*  
  > *Hôm nay thèm một ngụm trà thơm thì ghé quán tụi mình nha!*
