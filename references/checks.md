# Post-Write Checks

Chạy 4 test này SAU khi viết xong. Không in kết quả ra, tự sửa nếu fail.

---

## 1. Hook Check
**Câu đầu tiên có thể đứng độc lập không?**
- Đọc mình câu đó — người chưa biết gì có bị kéo không?
- Fail nếu: câu mở bằng "Hôm nay chúng tôi xin giới thiệu", "Đến với [tên quán]", hoặc bắt đầu bằng tên sản phẩm trần trụi

---

## 2. Sáo Check
**Từ có gợi được hình ảnh hoặc cảm giác cụ thể không?**
- Sáo = từ không gợi được gì dù quen hay lạ: ngon, chất lượng, tuyệt vời, hấp dẫn, đặc biệt, cao cấp
- Không phải sáo = từ phổ biến nhưng vẫn gợi được cảm giác: "nhịp sống trôi chậm", "đắng nhẹ ở cuối"
- Từ phổ biến + hay → dùng được
- **Storytelling: bỏ qua Sáo Check hoàn toàn**

---

## 3. Bịa Check
**Có claim không có SOURCE + VERIFICATION hợp lệ không?**
- Không bịa: số lượng khách, hành vi khách, giải thưởng, thứ hạng, thành phần chưa được confirm
- Comparative claims ("ngon hơn", "organic", "không chất bảo quản") cần `CATALOG/VERIFIED` — `USER_ASSERTED` → MEDIUM risk, báo người dùng
- Achievement claims ("số 1", "giải thưởng") cần `CATALOG/VERIFIED` — thiếu → HIGH risk, dừng
- `DEFAULT` chỉ dùng như gợi ý ngôn ngữ chung, **không** khẳng định thuộc tính sản phẩm cụ thể
- `IMAGE_OBSERVED` chỉ dùng cho visual (màu, hình dạng, kết cấu nhìn thấy) — không dùng cho vị/mùi
- Ví dụ ĐÚNG: "màu cam trong ảnh" `[IMAGE_OBSERVED/VERIFIED]` ✅
- Ví dụ SAI: "vị ngọt thơm" từ ảnh → không verify được từ ảnh ❌

---

## 4. Platform Check
**Format có đúng nền tảng không?**
- Facebook: hook trong 3 dòng đầu, đoạn văn ngắn, có CTA cuối
- TikTok/Reels: dạng script, câu ngắn, hook 0-3s rõ ràng
- Zalo OA: ≤150 từ, không hashtag, có link/SĐT nếu cần đặt hàng

---

## 5. Pain-Solution Check (Vá lỗi logic)
**Mọi nỗi đau (pain point) được đưa ra ở Hook có được giải quyết triệt để ở Body/CTA không?**
- Đọc lại Hook: Nếu Hook đề cập đến sự mệt mỏi, buồn ngủ, cô đơn, nắng nóng kẹt xe...
- Check lại Body/CTA: Sản phẩm hoặc deal có thực sự giải quyết được cảm giác đó không?
- Biện pháp: Nếu Hook khơi gợi nỗi đau nhưng Body đi vào mô tả sản phẩm lan man không giải quyết nỗi đau đó → buộc phải điều chỉnh Body hoặc CTA để đóng kín vòng lặp (close the loop).

---

## 6. CTA Single-Action Check (Machine-Readable Verification)
**CTA có đảm bảo count == 1 không?**
- Kiểm tra cấu trúc `cta`:
  - `action`: Chỉ được chứa đúng 1 hành động duy nhất (`message`, `comment`, `visit`, hoặc `click_link`).
  - `count`: Bắt buộc bằng 1.
- Nếu câu CTA thực tế chứa ≥ 2 hành vi (ví dụ: *"Ghé quán HOẶC nhắn tin"*, *"Inbox ĐỂ ĐƯỢC tư vấn rồi ghé"*...) → `count: 2` → **FAIL CHECK**. Bắt buộc rút gọn về đúng 1 hành vi duy nhất trước khi gửi.

---

## 7. Cross-Brand Contamination Check (Multi-Tenant Isolation)
**Nội dung có bị rò rỉ dữ liệu hoặc nhận diện từ brand/branch khác không?**
- **Pronouns & Persona:** Bài viết có dùng đúng bảng đại từ xưng hô của `brand_id` trong envelope không? (Ví dụ: `tearus` dùng "mình/tụi mình" — nếu xuất hiện "tôi/chúng tôi" của brand khác → sửa lại).
- **Catalog & Pricing:** Món ăn, nguyên liệu, mức giá và chính sách có thuộc đúng `brand_id` và `branch_id` đang kích hoạt không?
- **Brand Name Leak:** Tên thương hiệu khác (nếu có trong brief để so sánh) có bị vô tình viết như thể thuộc về quán không?
- Nếu phát hiện rò rỉ → **BẮT BUỘC SỬA HOẶC XÓA BỎ NGAY TRƯỚC KHI TRẢ VỀ CHO HERMES**.
