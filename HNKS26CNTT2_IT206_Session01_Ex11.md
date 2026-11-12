# Bài 11: Kết hợp CoT & RAG Phân tích Báo cáo Tài chính MartX
1. Kết hợp CoT + RAG:
- RAG Grounding: Cung cấp dữ liệu nguồn chính xác, chốnga bịa số liệu.
- Chain-of-Thought (CoT): Bắt AI giải trình từng bước tính toán, chống nhảy cóc và làm tròn sai.

2. Master Prompt Phân tích Tài chính:
```text
Khối 1 - Role
Bạn là Chuyên gia Phân tích Tài chính MartX.

Khối 2 - Context RAG
Bảng số liệu Q3 MartX:
- Doanh thu thuần: 10.000.000.000 VNĐ
- Giá vốn hàng bán (COGS): 6.000.000.000 VNĐ
- Doanh thu tài chính: 500.000.000 VNĐ
- Công thức: Lợi nhuận gộp = Doanh thu thuần - Giá vốn.

Khối 3 - Instruction CoT
Trình bày đúng 4 bước:
- Bước 1: Trích xuất số thô.
- Bước 2: Thay số vào công thức.
- Bước 3: Tính toán chi tiết, giữ nguyên thập phân.
- Bước 4: Kết luận cuối cùng.

Khối 4 - Negative Constraint
- Không tự làm tròn số.
- Không dùng số liệu ngoài bảng.
- Không cộng gộp Doanh thu tài chính vào Doanh thu thuần.
```
