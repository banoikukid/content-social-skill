# Result

Status: ✅ PASS

Actual output:
Trà Sữa 39k hôm nay tại TeaRus: pha từng ly mới theo yêu cầu của bạn.

Nền trà nấu chậm giữ trọn hương mộc tự nhiên, hòa cùng sữa thơm béo dịu vừa miệng. Tụi mình chăm chút từng ly để bạn luôn cảm nhận được vị ngon trọn vẹn nhất.

Nhắn tin cho tụi mình nha.

Decision trace (/audit):
platform: facebook
flow: A (Conversion)
tone: 6 (Gần gũi)
evidence: brief [USER_CLAIM]
claims: [mon: "Trà sữa" [USER_CLAIM], gia: "39k" [USER_CLAIM], social_proof: USER_ASSERTED (không dùng như factual claim)]
cta: "Nhắn tin cho tụi mình nha."
risk_flags: fake_social_proof (MEDIUM - handled by fallback quy trình)

Verdict: PASS
Notes: Áp dụng Specificity Fallback: chuyển thành chi tiết quy trình "pha từng ly mới", "nấu chậm" thay vì bịa đặt hành vi khách.
