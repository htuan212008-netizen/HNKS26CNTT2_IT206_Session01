# Bài 9: Kỹ thuật RAG Grounding Dập tắt Ảo giác Hợp đồng Thu mua
## Phần 1 (Phân tích nguyên nhân ảo giác)
- Bản chất LLM: Dự đoán từ dựa trên xác suất, không tự tra cứu dữ liệu nội bộ nếu thiếu ngữ cảnh.
- Nguyên nhân: Do thiếu tài liệu nguồn (Grounding Data), AI tự suy diễn các điều khoản phạt thông thường trên Internet (mức 20%, 30 ngày) thay vì hợp đồng thực tế của MartX.
## Phần 2 (Cấu trúc RAG Prompt hoàn chỉnh)
1. Văn bản hợp đồng chuẩn

Điều khoản xử lý vi phạm chất lượng hàng hóa MartX:
- "Phạt 5% giá trị lô bị dập nát và yêu cầu đổi hàng trong 24h."
2. Câu hỏi nghiệp vụ
Theo quy định MartX trong văn bản trên, nhà cung cấp giao rau bị dập nát trên 10% thì bị phạt bao nhiêu và xử lý thế nào?
3. Negative Constraint khóa an toàn
- Tuyệt đối chỉ sử dụng thông tin có sẵn trong `VĂN BẢN HỢP ĐỒNG CHUẨN`.
- Nếu không có, trả lời: "Không có dữ liệu trong tài liệu". Không tự suy đoán hoặc bịa số liệu ngoài văn bản.
