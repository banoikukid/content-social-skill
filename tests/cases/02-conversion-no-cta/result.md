# Result

Status: ✅ PASS

Actual output:
Hôm nay tụi mình có Trà Sữa Matcha 45k thơm béo đậm vị.

Lớp matcha sánh mịn hòa cùng trà sữa béo thơm vừa vặn, uống lạnh giải nhiệt cực đã cho ngày dài làm việc.

Nhắn tin cho tụi mình nha.

Decision trace (/audit):
platform: facebook
flow: A (Conversion)
tone: 6 (Gần gũi)
evidence: brief [USER_CLAIM]
claims: [ten_mon: "Trà Sữa Matcha" [USER_CLAIM/USER_ASSERTED], gia: "45k" [USER_CLAIM/USER_ASSERTED]]
cta: "Nhắn tin cho tụi mình nha." (fallback CTA platform schema)
risk_flags: none (LOW)

Verdict: PASS
Notes: Thiếu CTA đã được tự động điền bằng CTA Platform Schema (Facebook: 1 action), không có delivery, không fake urgency.
