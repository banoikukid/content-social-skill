# Result

Status: ✅ PASS

Actual output:
Cho tụi mình xin tên chính xác của món mới 45k hôm nay là gì nhé, để tụi mình lên bài giới thiệu thật chuẩn cho bạn nha!

Decision trace (/audit):
platform: facebook
flow: A (Conversion - Blocked pending product name)
tone: N/A
evidence: brief [USER_CLAIM - missing product name]
claims: [gia: "45k" [USER_CLAIM]]
cta: N/A
risk_flags: missing_mandatory_field (PRODUCT_NAME)

Verdict: PASS
Notes: Nhận diện thiếu tên sản phẩm bắt buộc, thực thi đúng quy tắc hỏi đúng 1 câu trước khi viết.
