
# 1. Bối cảnh

Cần sử dụng AI để phân tích đơn hàng, tính tổng tiền và xử lý dữ liệu sai bằng kỹ thuật Chain-of-Thought và Prompt Chaining.

# 2. Yêu cầu đầu ra

- Đề xuất 2 prompt: đơn giản và chi tiết.
- Lập bảng so sánh ưu, nhược điểm.
- Chọn phương án tối ưu và chạy thử.
- Đưa ra kết quả và nhận xét.

# 3. Bài làm

## Bước 1: Đề xuất 2 prompt

**Giải pháp 1: Prompt đơn giản**

"Hãy phân tích đơn hàng, tính tổng tiền và đưa ra kết quả. Nếu có lỗi dữ liệu thì thông báo."

**Giải pháp 2: Prompt chi tiết**

"Bạn là nhân viên xử lý đơn hàng. Hãy thực hiện:

1. Kiểm tra tên sản phẩm, số lượng và đơn giá.
2. Nếu dữ liệu thiếu hoặc sai, báo lỗi và dừng.
3. Tính thành tiền = số lượng × đơn giá.
4. Kiểm tra lại phép tính.
5. Xuất kết quả dưới dạng bảng Markdown.

Thực hiện lần lượt từng bước, không tự đoán dữ liệu thiếu. Nếu câu trả lời bị ngắt, tiếp tục từ phần chưa hoàn thành, không lặp lại nội dung cũ."

## Bước 2: So sánh Trade-off

| Tiêu chí | Giải pháp 1 | Giải pháp 2 |
|---|---|---|
| Độ dễ hiểu | Cao | Trung bình |
| Tốn token | Ít | Nhiều hơn |
| Kiểm soát lỗi | Trung bình | Tốt |
| Độ chính xác | Khó kiểm soát | Dễ kiểm tra |
| Xử lý dữ liệu thiếu | Chưa rõ ràng | Có quy định |
| Ưu điểm | Nhanh, đơn giản | Rõ ràng, ít sai sót |
| Nhược điểm | Dễ bỏ sót lỗi | Prompt dài hơn |

## Bước 3: Lựa chọn và chạy thử

**Phương án chọn:** Giải pháp 2.

**Lý do:** Có các bước xử lý rõ ràng, dễ kiểm tra lỗi và hạn chế AI tự suy đoán.

**Dữ liệu thử nghiệm:**

- Sản phẩm: Bút bi
- Số lượng: 5
- Đơn giá: 10.000 VNĐ

**Kết quả chạy thử:**

| Sản phẩm | Số lượng | Đơn giá | Thành tiền |
|---|---|---|---|
| Bút bi | 5 | 10.000 | 50.000 |

Tổng tiền: 50.000 VNĐ.

**Thử trường hợp lỗi:**

- Sản phẩm: Vở
- Số lượng: Không có
- Đơn giá: 15.000 VNĐ

Kết quả: "Lỗi: Thiếu số lượng sản phẩm, không thể tính tổng tiền."


