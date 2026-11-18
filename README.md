Dưới đây là thiết kế giải pháp và câu lệnh Prompt hoàn chỉnh áp dụng kỹ thuật Chain-of-Thought (CoT) để giải quyết bài toán lập kế hoạch tài chính cá nhân một cách minh bạch, chính xác tuyệt đối và không bị sai sót số học.

## Phần 1: Prompt lập kế hoạch tài chính cá nhân bằng Chain-of-Thought
1. Prompt hoàn chỉnh gồm 5 thành phần :

Bạn là chuyên gia tư vấn tài chính cá nhân, làm việc cẩn thận và minh bạch từng con số.

a, DỮ LIỆU ĐẦU VÀO
- Thu nhập (biến động): [liệt kê 3–6 tháng gần nhất, VD: 18.000.000; 24.000.000; 21.000.000]
- Thuế/khấu trừ: [VD: 5% thu nhập]
- Chi phí cố định bắt buộc: [liệt kê từng khoản + số tiền]
- Các khoản nợ: [tên nợ, số tiền trả tối thiểu/tháng, lãi suất, hạn thanh toán]
- Mục tiêu tiết kiệm: [VD: tối thiểu 20% thu nhập, trong đó quỹ dự phòng X]

b, CHỈ THỊ

Hãy suy nghĩ từng bước một và tính toán chi tiết trước khi đưa ra quyết định.

c, QUY TRÌNH LẬP LUẬN (làm tuần tự, không bỏ bước)
Bước 0 – Chuẩn hóa thu nhập: Lấy trung bình các tháng đã cho làm thu nhập lập kế hoạch
         (nêu rõ: tổng ÷ số tháng = kết quả).
Bước 1 – Thu nhập khả dụng = Thu nhập − Thuế − Chi phí cố định bắt buộc.
Bước 2 – Phân bổ trả nợ tối thiểu, ưu tiên khoản đến hạn gần/lãi cao. Số dư = Bước 1 − Tổng nợ tối thiểu.
Bước 3 – Trích tiết kiệm = Thu nhập × tỷ lệ cam kết (≥ 20%), tách rõ quỹ dự phòng và tiết kiệm/đầu tư.
         Số dư = Bước 2 − Tiết kiệm.
Bước 4 – Chia số dư còn lại theo quy tắc 50/30/20 cải tiến:
         thiết yếu linh hoạt / mong muốn cá nhân / trả nợ thêm (tỷ lệ do bạn đề xuất, nêu lý do).

d, RÀNG BUỘC BẮT BUỘC
1. Viết đầy đủ từng phép tính dạng: "A + B − C = kết quả". Không nhảy cóc.
2. Sau mỗi bước, ghi "Số dư còn lại: ..." để kiểm soát dòng tiền.
3. Tỷ lệ % tính trên thu nhập lập kế hoạch (Bước 0), làm tròn 2 chữ số thập phân; tổng phải đúng 100,00%.
   Nếu lệch do làm tròn, điều chỉnh vào hạng mục "Mong muốn" và nêu rõ.
4. Nếu số dư ở bất kỳ bước nào < 0: DỪNG, báo thâm hụt và đề xuất cách cắt giảm trước khi đi tiếp.
5. Không dùng code, chỉ dùng suy luận bằng văn bản.

e, BƯỚC KIỂM TRA CUỐI (bắt buộc)
- Cộng lại toàn bộ hạng mục, so với thu nhập lập kế hoạch (phải bằng nhau).
- Cộng tất cả tỷ lệ % (phải = 100,00%).
- Xác nhận tiết kiệm ≥ 20% và mọi khoản nợ đều được trả đúng hạn.

# ĐỊNH DẠNG ĐẦU RA

 # Phần 1: Nhật ký suy luận (Reasoning Steps)
Trình bày Bước 0 → 4 + Bước kiểm tra, mỗi bước có công thức và số liệu trung gian.

 # Phần 2: Bảng phân bổ ngân sách cuối cùng
Markdown Table, cột: | Hạng mục | Số tiền | Tỷ lệ % | Ghi chú |
Dòng cuối là "TỔNG" = 100,00%.
 2. Ví dụ chạy thử (kiểm chứng số liệu)

Đầu vào: Thu nhập 3 tháng: 18.000.000 / 24.000.000 / 21.000.000. Thuế 5%. Chi phí cố định: thuê nhà 5.000.000, điện nước-internet 1.200.000, đi lại 1.500.000, bảo hiểm 800.000. Nợ: thẻ tín dụng tối thiểu 1.200.000, vay trả góp 2.000.000. Tiết kiệm ≥ 20%.

Phần 1: Nhật ký suy luận

Bước 0 – Thu nhập lập kế hoạch
(18.000.000 + 24.000.000 + 21.000.000) ÷ 3 = 63.000.000 ÷ 3 = 21.000.000

Bước 1 – Thu nhập khả dụng

Thuế: 21.000.000 × 5% = 1.050.000
Chi phí cố định: 5.000.000 + 1.200.000 + 1.500.000 + 800.000 = 8.500.000
Khả dụng: 21.000.000 − 1.050.000 − 8.500.000 = 11.450.000

Bước 2 – Nợ tối thiểu

1.200.000 + 2.000.000 = 3.200.000
Số dư: 11.450.000 − 3.200.000 = 8.250.000

Bước 3 – Tiết kiệm 20%

21.000.000 × 20% = 4.200.000, chia đôi: quỹ dự phòng 2.100.000 + đầu tư/mục tiêu 2.100.000
Số dư: 8.250.000 − 4.200.000 = 4.050.000

Bước 4 – Chia phần còn lại (60% / 25% / 15%)
Do chi phí cố định và nợ đã chiếm tỷ trọng lớn, nhu cầu thiết yếu được ưu tiên hơn mức 50% chuẩn.

Thiết yếu linh hoạt: 4.050.000 × 60% = 2.430.000
Mong muốn: 4.050.000 × 25% = 1.012.500
Trả nợ thêm: 4.050.000 × 15% = 607.500
Kiểm tra: 2.430.000 + 1.012.500 + 607.500 = 4.050.000 ✔

Kiểm tra cuối
1.050.000 + 8.500.000 + 3.200.000 + 4.200.000 + 2.430.000 + 1.012.500 + 607.500 = 21.000.000 ✔
Tổng %: 5,00 + 40,48 + 15,24 + 20,00 + 11,57 + 4,82 + 2,89 = 100,00% ✔

## Phần 2: Bảng phân bổ ngân sách

| Hạng mục | Số tiền (VNĐ) | Tỷ lệ % | Ghi chú |
|---:|---:|---:|---:|
| Thuế/khấu trừ | 1.050.000 | 5,00% | 5% thu nhập |
| Chi phí cố định | 8.500.000 | 40,48% | Nhà, điện nước, đi lại, bảo hiểm |
| Nợ tối thiểu | 3.200.000 | 15,24% | Thẻ tín dụng + vay trả góp, trả đúng hạn |
| Quỹ dự phòng | 2.100.000 | 10,00% | Mục tiêu 3–6 tháng chi phí |
| Tiết kiệm/đầu tư | 2.100.000 | 10,00% | Tổng tiết kiệm đạt 20% |
| Thiết yếu linh hoạt | 2.430.000 | 11,57% | Ăn uống, sinh hoạt |
| Mong muốn cá nhân | 1.012.500 | 4,82% | Giải trí, mua sắm |
| Trả nợ thêm | 607.500 | 2,89% | Ưu tiên nợ lãi cao nhất |
| **TỔNG** | **21.000.000** | **100,00%** | Khớp thu nhập lập kế hoạch |
