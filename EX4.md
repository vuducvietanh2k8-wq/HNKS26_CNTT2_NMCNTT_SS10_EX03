
# BÀI TẬP: THIẾT KẾ PROMPT GIẢI THÍCH MÔ HÌNH IPO

## 1. Bối cảnh và bài toán

Bạn là sinh viên năm nhất PTIT đang tìm hiểu về **mô hình IPO trong trang trại thông minh**. Bạn gặp khó khăn khi hiểu các khái niệm Input, Process và Output.

Bạn cần thiết kế một Prompt để AI đóng vai trò là gia sư, giải thích kiến thức bằng ngôn ngữ đơn giản, dễ hiểu và có ví dụ thực tế.

## 2. Thiết kế kiến trúc Prompt hoàn chỉnh

### Phần 1: Bối cảnh

Bạn là một gia sư Công nghệ thông tin thân thiện, đang hướng dẫn sinh viên năm nhất PTIT tìm hiểu về mô hình IPO (Input - Process - Output) trong trang trại thông minh.

Người học chưa có nhiều kiến thức chuyên ngành nên cần được giải thích bằng ngôn ngữ đơn giản và ví dụ thực tế.

### Phần 2: Yêu cầu và ràng buộc

Hãy giải thích mô hình IPO trong trang trại thông minh theo các yêu cầu sau:

- [ ] Giải thích IPO là gì và nêu ý nghĩa của ba thành phần Input, Process, Output bằng tiếng Việt.
- [ ] Sử dụng ví dụ gần gũi về hệ thống tưới cây tự động trong trang trại.
- [ ] Trình bày rõ Input là dữ liệu đầu vào, Process là quá trình xử lý và Output là kết quả đầu ra.
- [ ] Mô tả quy trình hoạt động theo thứ tự Input → Process → Output.
- [ ] Đưa ra ví dụ cụ thể về độ ẩm đất thấp khiến hệ thống tự động bật máy bơm.
- [ ] Sử dụng tiêu đề Markdown, danh sách gạch đầu dòng và bảng khi cần thiết.
- [ ] Giới hạn câu trả lời trong khoảng 300–400 từ.
- [ ] Sử dụng câu ngắn, dễ hiểu và phù hợp với sinh viên năm nhất.
- [ ] Nếu xuất hiện thuật ngữ tiếng Anh, hãy giải thích nghĩa tiếng Việt ngay bên cạnh.
- [ ] Cuối bài, tóm tắt kiến thức bằng 3 ý chính và đưa ra 2 câu hỏi ôn tập ngắn.

### Phần 3: Không cần

- Không sử dụng thuật ngữ kỹ thuật chuyên sâu nếu không thực sự cần thiết.
- Không giải thích chi tiết về lập trình, thuật toán, cảm biến điện tử hoặc cấu tạo phần cứng.
- Không mở rộng sang các mô hình xử lý dữ liệu khác ngoài IPO.
- Không đưa thông tin ngoài chủ đề hoặc ví dụ quá phức tạp.
- Không viết quá dài hoặc sử dụng quá nhiều từ tiếng Anh chuyên ngành.

## 3. Kết quả sau khi áp dụng Prompt

### 3.1. Khái niệm IPO

**IPO** là viết tắt của *Input – Process – Output*, nghĩa là **Đầu vào – Xử lý – Đầu ra**.

Đây là mô hình mô tả cách một hệ thống nhận dữ liệu, xử lý dữ liệu và tạo ra kết quả.

### 3.2. Ba thành phần của mô hình IPO

| Thành phần | Ý nghĩa | Ví dụ trong trang trại thông minh |
|---|---|---|
| **Input** | Đầu vào: dữ liệu hệ thống nhận được | Cảm biến đo độ ẩm đất |
| **Process** | Xử lý: phân tích dữ liệu và đưa ra quyết định | Bộ điều khiển so sánh độ ẩm với ngưỡng đã cài đặt |
| **Output** | Đầu ra: kết quả hoặc hành động của hệ thống | Máy bơm tự động bật để tưới cây |

### 3.3. Ví dụ thực tế: Hệ thống tưới cây tự động

Giả sử trang trại có hệ thống tưới cây tự động. Khi độ ẩm đất thấp hơn mức quy định, hệ thống sẽ bật máy bơm để tưới nước.

Quy trình hoạt động như sau:

1. **Input – Đầu vào:** Cảm biến đo được độ ẩm đất là 20%.
2. **Process – Xử lý:** Bộ điều khiển so sánh mức 20% với ngưỡng cài đặt là 30%. Vì 20% thấp hơn 30%, hệ thống quyết định cần tưới nước.
3. **Output – Đầu ra:** Máy bơm được bật để tưới cây.

Khi độ ẩm đạt mức phù hợp, hệ thống có thể tắt máy bơm theo quy tắc đã cài đặt.

### 3.4. Sơ đồ mô hình IPO

```text
INPUT
Độ ẩm đất
    |
    v
PROCESS
Kiểm tra độ ẩm
    |
    v
OUTPUT
Bật máy bơm tưới cây
```

Có thể ghi nhớ mô hình IPO bằng công thức:

**Input → Process → Output**

Nói cách khác, hệ thống **nhận dữ liệu → xử lý dữ liệu → tạo ra kết quả**.

### 3.5. Tóm tắt kiến thức

- **Input:** Dữ liệu đầu vào mà hệ thống nhận được.
- **Process:** Quá trình xử lý dữ liệu để đưa ra quyết định.
- **Output:** Kết quả hoặc hành động được tạo ra sau khi xử lý.

### 3.6. Câu hỏi ôn tập

**Câu 1:** Trong hệ thống tưới cây tự động, cảm biến đo độ ẩm đất thuộc thành phần nào của mô hình IPO?

- A. Input
- B. Process
- C. Output

**Đáp án:** A. Input.

**Giải thích:** Cảm biến cung cấp dữ liệu độ ẩm đất cho hệ thống.

**Câu 2:** Nếu độ ẩm đất thấp hơn ngưỡng đã cài đặt, đầu ra của hệ thống có thể là gì?

- A. Xóa dữ liệu cảm biến.
- B. Bật máy bơm tưới cây.
- C. Ngừng thu thập dữ liệu.

**Đáp án:** B. Bật máy bơm tưới cây.

**Giải thích:** Sau khi xử lý dữ liệu và xác định đất đang khô, hệ thống bật máy bơm để tưới cây.

## 4. Phân tích trường hợp kiểm thử (Edge Case)

Nếu AI trả lời quá dài hoặc sử dụng quá nhiều thuật ngữ tiếng Anh chuyên môn, cần bổ sung các ràng buộc vào Prompt:

- **Giới hạn độ dài:** Yêu cầu câu trả lời từ 300–400 từ.
- **Giới hạn ngôn ngữ:** Ưu tiên tiếng Việt đơn giản; giải thích nghĩa tiếng Việt ngay sau thuật ngữ tiếng Anh.
- **Giới hạn độ khó:** Chỉ sử dụng kiến thức phù hợp với sinh viên năm nhất.
- **Giới hạn phạm vi:** Không mở rộng sang lập trình, thuật toán hoặc phần cứng chuyên sâu khi không cần thiết.
- **Yêu cầu trình bày:** Sử dụng tiêu đề, danh sách, bảng và ví dụ thực tế để nội dung dễ đọc.

Những ràng buộc này giúp kiểm soát độ dài, ngôn ngữ và mức độ phức tạp của câu trả lời.

## 5. Kết luận

Việc sử dụng Prompt theo cấu trúc ba phần **Bối cảnh – Yêu cầu và ràng buộc – Không cần** giúp AI hiểu rõ nhiệm vụ, tạo câu trả lời có tổ chức và hạn chế nội dung không cần thiết.

Markdown hỗ trợ trình bày kiến thức bằng tiêu đề, bảng, danh sách, sơ đồ và danh sách kiểm tra. Nhờ đó, tài liệu dễ đọc, dễ chỉnh sửa và thuận tiện lưu trữ trong StackEdit hoặc VS Code.