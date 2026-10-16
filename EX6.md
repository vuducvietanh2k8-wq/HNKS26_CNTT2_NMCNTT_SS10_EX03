#  GreenTech – Công nghệ xanh cho tương lai bền vững

# PHẦN 1. PHÂN TÍCH VẤN ĐỀ

## 1.1. Những sai lầm trong tư duy của Nam

### Sai lầm 1: Sử dụng Microsoft Word để lưu trữ tài liệu dự án trên GitHub

Nam sử dụng tệp `.docx` để viết tài liệu giới thiệu dự án GreenTech. Tuy nhiên, Word là định dạng Rich Text, hỗ trợ nhiều kiểu định dạng, hình ảnh, bảng biểu và bố cục phức tạp.

Tệp `.docx` là một gói dữ liệu có cấu trúc, thường chứa các thành phần XML và tài nguyên được nén. Git khó so sánh trực tiếp nội dung của tệp này theo từng dòng văn bản.

Khi nhiều thành viên cùng chỉnh sửa, Git có thể không tự động hợp nhất các thay đổi trong tệp Word, dẫn đến xung đột và phải xử lý thủ công.

### Sai lầm 2: Cho rằng tài liệu Word thuận tiện để xem trực tiếp trên GitHub

Tệp `.docx` thường cần được tải xuống hoặc mở bằng phần mềm tương thích để xem và chỉnh sửa đầy đủ.

Trong khi đó, Markdown (`.md`) được GitHub hỗ trợ hiển thị trực tiếp trên trình duyệt. Các thành viên có thể đọc nội dung ngay trong repository mà không cần tải tệp về máy.

### Sai lầm 3: Chưa phân biệt tài liệu trình bày với tài liệu quản lý phiên bản

Word phù hợp với báo cáo cần trang bìa, bố cục phức tạp và định dạng in ấn.

Markdown phù hợp với README, tài liệu kỹ thuật, hướng dẫn cài đặt và nội dung dự án cần theo dõi lịch sử thay đổi bằng Git.

Vì vậy, Nam nên lựa chọn định dạng dựa trên mục đích sử dụng thay vì dùng Word cho mọi loại tài liệu.

## 1.2. So sánh Word và Markdown

| Tiêu chí             | Word (`.docx`)                                      | Markdown (`.md`)                                     |
| -------------------- | --------------------------------------------------- | ---------------------------------------------------- |
| Bản chất             | Gói tài liệu có cấu trúc, chứa XML và tài nguyên    | Văn bản thuần với cú pháp định dạng                  |
| Dung lượng           | Có thể lớn hơn khi chứa nhiều định dạng và hình ảnh | Thường nhẹ đối với tài liệu văn bản                  |
| Hiển thị trên GitHub | Thường cần tải xuống để xem đầy đủ                  | Hiển thị trực tiếp trên trình duyệt                  |
| Theo dõi thay đổi    | Git khó so sánh nội dung nhị phân                   | Git có thể so sánh từng dòng văn bản                 |
| Hợp nhất thay đổi    | Có thể khó xử lý khi nhiều người cùng sửa           | Thuận tiện hơn khi thay đổi nằm ở các dòng khác nhau |
| Công cụ sử dụng      | Microsoft Word hoặc phần mềm tương thích            | StackEdit, VS Code, GitHub                           |
| Khả năng di động     | Phụ thuộc mức độ tương thích định dạng              | Dễ đọc bằng nhiều trình soạn thảo văn bản            |

## 1.3. Bẫy dữ liệu: Mất 1 byte khi tải tệp

### Đối với Word (`.docx`)

* `.docx` là định dạng gói dữ liệu có cấu trúc, thường được đóng gói theo chuẩn ZIP.
* Nếu một byte bị mất hoặc thay đổi do lỗi truyền tải, dữ liệu nén, cấu trúc gói hoặc nội dung bên trong có thể bị lỗi.
* Tệp có thể không mở được hoặc một số thành phần bị hỏng.
* Tuy nhiên, không phải cứ mất một byte là toàn bộ tệp chắc chắn hỏng. Kết quả phụ thuộc vào vị trí byte bị lỗi và cơ chế phát hiện, sửa lỗi.

### Đối với Markdown (`.md`)

* Markdown là văn bản thuần, không phụ thuộc vào cấu trúc gói nhị phân phức tạp như `.docx`.
* Nếu một byte bị mất, thông thường chỉ một ký tự hoặc một phần nội dung bị ảnh hưởng; những phần văn bản còn lại vẫn có thể đọc được.
* Tuy nhiên, Markdown cũng không tự bảo đảm dữ liệu nguyên vẹn. Lỗi có thể làm hỏng cú pháp, ký tự tiếng Việt hoặc nội dung.

### Kết luận

Markdown nhẹ, dễ đọc và thuận tiện hơn cho Git vì lưu dưới dạng văn bản thuần. Tuy nhiên, cả hai định dạng đều cần cơ chế truyền tải đáng tin cậy, kiểm tra tính toàn vẹn và sao lưu dữ liệu.

---

# PHẦN 2. HOÀN THIỆN README.md BẰNG MARKDOWN

## 2.1. Giới thiệu dự án

**GreenTech** là dự án của nhóm sinh viên PTIT hướng đến việc ứng dụng công nghệ để xây dựng các giải pháp thân thiện với môi trường, tiết kiệm tài nguyên và nâng cao nhận thức về phát triển bền vững.

Dự án tập trung vào việc tìm hiểu các vấn đề môi trường, đề xuất giải pháp công nghệ phù hợp và khuyến khích cộng đồng áp dụng lối sống xanh.

## 2.2. Mục tiêu dự án

* Nghiên cứu và đề xuất các giải pháp công nghệ xanh.
* Nâng cao nhận thức về tiết kiệm năng lượng và bảo vệ môi trường.
* Khuyến khích sử dụng tài nguyên hiệu quả.
* Phát triển kỹ năng làm việc nhóm và quản lý dự án của sinh viên.

## 2.3. Công nghệ và công cụ sử dụng

| Công cụ            | Mục đích                            |
| ------------------ | ----------------------------------- |
| Markdown           | Soạn thảo tài liệu dự án            |
| Git                | Theo dõi lịch sử thay đổi           |
| GitHub             | Lưu trữ mã nguồn và cộng tác nhóm   |
| StackEdit          | Viết và xem trước tài liệu Markdown |
| Visual Studio Code | Chỉnh sửa tài liệu và mã nguồn      |

## 2.4. Kế hoạch thực hiện

* [x] Xác định ý tưởng và mục tiêu dự án.
* [x] Xây dựng cấu trúc tài liệu giới thiệu.
* [ ] Phân công nhiệm vụ cho các thành viên.
* [ ] Nghiên cứu và phát triển giải pháp.
* [ ] Kiểm thử, đánh giá và hoàn thiện báo cáo.

## 2.5. Lợi ích của việc sử dụng Markdown

* Tài liệu nhẹ, dễ đọc và dễ chỉnh sửa.
* Git có thể theo dõi thay đổi theo từng dòng.
* Hỗ trợ cộng tác và xem lịch sử phiên bản thuận tiện.
* GitHub hiển thị nội dung trực tiếp trên trình duyệt.
* Dễ dàng chuyển đổi sang các định dạng tài liệu khác bằng công cụ phù hợp.

## 2.6. Kết luận dự án

GreenTech hướng đến việc kết hợp công nghệ với mục tiêu bảo vệ môi trường và phát triển bền vững. Việc sử dụng Markdown cùng GitHub giúp nhóm quản lý tài liệu rõ ràng, theo dõi thay đổi thuận tiện và cộng tác hiệu quả hơn.

**Đơn vị thực hiện:** Nhóm sinh viên PTIT

**Tên dự án:** GreenTech

**Định dạng tài liệu:** Markdown (`.md`)

---

# PHẦN 3. HƯỚNG DẪN CHUYỂN ĐỔI BẰNG STACKEDIT

## 3.1. Các bước thực hiện

1. Truy cập [StackEdit](https://stackedit.io/).
2. Tạo một tài liệu Markdown mới.
3. Sao chép nội dung Markdown ở Phần 2 và dán vào trình soạn thảo.
4. Quan sát phần xem trước để kiểm tra tiêu đề, bảng, danh sách và chữ in đậm.
5. Xuất hoặc tải tài liệu xuống định dạng Markdown (`.md`) nếu tùy chọn đó có trong giao diện.
6. Đặt tên tệp là `README.md`.
7. Đưa tệp vào repository GitHub của dự án GreenTech.

## 3.2. Cập nhật tài liệu lên GitHub

Mở terminal tại thư mục dự án và thực hiện:

```bash
git add README.md
git commit -m "Convert GreenTech documentation to Markdown"
git push
```

### Giải thích lệnh

* `git add README.md`: đưa tệp README vào vùng chuẩn bị commit.
* `git commit`: lưu lại phiên bản thay đổi ở máy tính.
* `git push`: đẩy các commit lên repository từ xa.

Nếu thành viên khác chỉnh sửa một phần nội dung, Git có thể hiển thị rõ các dòng được thêm, sửa hoặc xóa. Xung đột vẫn có thể xảy ra khi hai người cùng chỉnh sửa một dòng, nhưng thường dễ xác định và xử lý hơn so với tệp Word nhị phân.

---

# PHẦN 4. KẾT LUẬN CHUNG

Nam nên sử dụng Markdown cho tài liệu dự án được quản lý trên GitHub, đặc biệt là README và hướng dẫn kỹ thuật.

Word vẫn hữu ích cho báo cáo cần bố cục trang phức tạp. Tuy nhiên, Markdown phù hợp hơn với việc cộng tác nhóm, theo dõi lịch sử phiên bản, xem tài liệu trực tuyến và xử lý thay đổi bằng Git.

**Kết luận cuối cùng:** Lựa chọn đúng định dạng giúp nhóm GreenTech giảm khó khăn khi hợp nhất thay đổi, dễ dàng đọc tài liệu trên trình duyệt và quản lý lịch sử dự án hiệu quả hơn.

# QUY ĐỊ
