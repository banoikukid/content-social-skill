# Result

Status: ✅ PASS

Actual output:
Hôm nay tụi mình có Trà Sữa 39k pha chậm từng ly theo yêu cầu.

Trà được ủ mới mỗi mẻ trong ngày, vị ngọt béo dịu nhẹ không gắt cổ. Tụi mình luôn pha trực tiếp tại quầy theo đúng khẩu vị đậm nhạt của bạn.

Nhắn tin cho tụi mình nha.

Decision trace (/audit):
platform: facebook
flow: A (Conversion)
tone: 6 (Gần gũi)
evidence: brief [USER_CLAIM]
claims: [ten_mon: "Trà Sữa" [USER_CLAIM/USER_ASSERTED], gia: "39k" [USER_CLAIM/USER_ASSERTED], social_proof: USER_ASSERTED (không có factual metrics)]
cta: "Nhắn tin cho tụi mình nha."
risk_flags: fake_social_proof (MEDIUM - handled via specificity fallback quy trình)

Verdict: PASS
Notes: Không bịa hành vi khách; thay thế bằng chi tiết quy trình pha theo order [USER_CLAIM].
