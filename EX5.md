# 🚀 Smart-Farm IoT – Hệ thống tưới tiêu thông minh

# PHẦN 1. PHÂN TÍCH HỆ THỐNG

## 1.1. Xác định Input và Output

Dự án Smart-Farm tại trang trại Lan ứng dụng công nghệ IoT để thu thập dữ liệu môi trường, phân tích điều kiện canh tác và tự động điều khiển hệ thống tưới nước.

### Input – Dữ liệu đầu vào

* Cảm biến nhiệt độ: đo nhiệt độ môi trường tại trang trại.
* Cảm biến độ ẩm đất: xác định tình trạng khô hoặc ẩm của đất.
* Cảm biến độ ẩm không khí: hỗ trợ đánh giá điều kiện môi trường.
* Ngưỡng cấu hình: nhiệt độ và độ ẩm đất dùng để xác định thời điểm tưới.
* Nguồn điện và kết nối mạng: cung cấp năng lượng và hỗ trợ truyền dữ liệu giữa các thiết bị.

### Output – Dữ liệu đầu ra

* Bật hoặc tắt máy bơm thông qua module điều khiển phù hợp.
* Đóng hoặc mở van tưới tại khu vực trồng cây.
* Hiển thị nhiệt độ, độ ẩm và trạng thái tưới trên giao diện giám sát.
* Ghi nhật ký hoạt động để theo dõi và phát hiện sự cố.

## 1.2. Sơ đồ phối hợp phần cứng

![Sơ đồ hệ thống Smart-Farm IoT: Cảm biến nhiệt độ và độ ẩm gửi dữ liệu đến bộ điều khiển ESP32; bộ điều khiển xử lý dữ liệu và gửi lệnh đến module relay, máy bơm và van tưới; dữ liệu vận hành được chuyển đến hệ thống giám sát và nhật ký.](docs/smart-farm-architecture.png)

**Hình 1. Sơ đồ phối hợp phần cứng của hệ thống Smart-Farm.**

### Nguyên lý hoạt động

1. Cảm biến thu thập dữ liệu nhiệt độ và độ ẩm.
2. Bộ điều khiển ESP32 tiếp nhận và xử lý dữ liệu.
3. Chương trình so sánh dữ liệu với ngưỡng cấu hình.
4. Nếu đáp ứng điều kiện tưới, bộ điều khiển gửi tín hiệu đến module relay.
5. Relay điều khiển máy bơm hoặc van tưới.
6. Hệ thống ghi nhật ký và cập nhật trạng thái vận hành.

*Lưu ý: ESP32 chỉ là thiết bị điều khiển minh họa. Linh kiện và ngưỡng vận hành thực tế cần được xác nhận tại trang trại Lan.*

---

# PHẦN 2. TRIỂN KHAI FILE README.md

## 2.1. Mô tả dự án

**Smart-Farm** là hệ thống ứng dụng Internet of Things (IoT) nhằm giám sát môi trường và tự động hóa hoạt động tưới nước tại trang trại Lan.

Hệ thống thu thập dữ liệu từ cảm biến, phân tích điều kiện môi trường và đưa ra quyết định tưới phù hợp với ngưỡng đã cấu hình.

### Mục tiêu dự án

* Tiết kiệm nước và giảm công sức tưới cây thủ công.
* Theo dõi nhiệt độ và độ ẩm của môi trường.
* Tự động hóa hoạt động tưới nước.
* Ghi nhật ký để hỗ trợ kiểm tra và xử lý sự cố.
* Nâng cao hiệu quả quản lý và chăm sóc cây trồng.

## 2.2. Hướng dẫn cài đặt

### Yêu cầu hệ thống

* Bộ điều khiển IoT: ESP32 hoặc thiết bị tương đương.
* Cảm biến nhiệt độ và độ ẩm đất.
* Module relay, máy bơm và van tưới tương thích.
* Nguồn điện phù hợp.
* Máy tính có môi trường phát triển chương trình điều khiển.
* Kết nối mạng nếu cần giám sát từ xa.

### Các bước tạo cấu trúc dự án

Mở terminal và thực hiện các lệnh sau:

```bash
# Bước 1: Tạo thư mục dự án
mkdir smart-farm
cd smart-farm

# Bước 2: Tạo các thư mục quản lý dữ liệu
mkdir config data logs docs

# Bước 3: Tạo file cấu hình mẫu
echo "temperature_threshold=35" > config/settings.txt
echo "soil_moisture_threshold=30" >> config/settings.txt
```

**Giải thích:**

* `mkdir`: tạo thư mục.
* `cd`: di chuyển vào thư mục dự án.
* `>`: tạo hoặc ghi đè nội dung vào file.
* `>>`: bổ sung nội dung vào cuối file.

Các ngưỡng `35°C` và `30%` chỉ là giá trị minh họa. Cần điều chỉnh theo loại cây trồng, đặc điểm cảm biến và điều kiện thực tế.

Các lệnh trên chỉ tạo cấu trúc thư mục và file cấu hình mẫu, chưa cài đặt hoặc khởi chạy chương trình IoT.

### Các bước khởi động

1. Kiểm tra nguồn điện và kết nối cảm biến.
2. Kiểm tra kết nối giữa bộ điều khiển, relay và máy bơm.
3. Nạp chương trình điều khiển đã được kiểm thử.
4. Kiểm tra dữ liệu cảm biến và trạng thái máy bơm.
5. Chạy thử ở chế độ an toàn trước khi sử dụng chế độ tự động.
6. Theo dõi nhật ký để xác nhận hệ thống hoạt động bình thường.

## 2.3. Tính năng chính

* [x] Thu thập dữ liệu nhiệt độ và độ ẩm.
* [x] So sánh dữ liệu với ngưỡng cấu hình.
* [x] Hỗ trợ điều khiển máy bơm và van tưới tự động.
* [x] Theo dõi trạng thái hoạt động của hệ thống.
* [x] Ghi nhật ký phục vụ kiểm tra và xử lý sự cố.
* [ ] Bổ sung cảnh báo từ xa khi cảm biến hoặc kết nối gặp lỗi.

*Các mục được đánh dấu hoàn thành mô tả chức năng mục tiêu của thiết kế; cần kiểm thử thực tế trước khi xác nhận hoàn thành.*

## 2.4. Bảng thông số hệ thống

| Thành phần         | Chức năng                      | Thông số theo dõi           |
| ------------------ | ------------------------------ | --------------------------- |
| Cảm biến nhiệt độ  | Đo nhiệt độ môi trường         | °C                          |
| Cảm biến độ ẩm đất | Đánh giá độ ẩm đất             | % hoặc giá trị hiệu chuẩn   |
| Bộ điều khiển IoT  | Xử lý dữ liệu và ra quyết định | CPU, RAM, kết nối           |
| Module relay       | Điều khiển thiết bị tưới       | Điện áp, dòng điện định mức |
| Máy bơm nước       | Cấp nước cho cây               | Lưu lượng, công suất        |
| Van tưới           | Điều tiết dòng nước            | Trạng thái đóng/mở          |
| Nhật ký hệ thống   | Lưu sự kiện và lỗi             | Thời gian, mức độ, nội dung |

## 2.5. Sơ đồ hệ thống Smart-Farm

![Sơ đồ kiến trúc Smart-Farm IoT: Cảm biến truyền dữ liệu đến bộ điều khiển; bộ điều khiển phân tích và gửi lệnh qua relay đến máy bơm và van tưới; hệ thống đồng thời ghi nhật ký và gửi dữ liệu đến giao diện giám sát.](docs/smart-farm-architecture.png)

**Hình 2. Luồng dữ liệu và điều khiển của hệ thống Smart-Farm.**

Để hình ảnh hiển thị, hãy lưu tệp sơ đồ thực tế với tên `smart-farm-architecture.png` trong thư mục `docs`.

Alt Text được đặt trong cú pháp Markdown để hỗ trợ người đọc khi hình ảnh không tải được hoặc khi sử dụng trình đọc màn hình.

## 2.6. Chu kỳ Fetch–Decode–Execute khi nhận lệnh tưới

CPU thực hiện lệnh theo chu kỳ cơ bản gồm ba giai đoạn:

> **Fetch – Lấy lệnh:** CPU lấy lệnh tiếp theo từ bộ nhớ chương trình, chẳng hạn lệnh kiểm tra điều kiện tưới.

> **Decode – Giải mã:** CPU giải mã lệnh để xác định thao tác cần thực hiện, ví dụ đọc dữ liệu cảm biến và so sánh với ngưỡng cấu hình.

> **Execute – Thực thi:** CPU thực hiện phép so sánh và chạy logic điều khiển. Nếu điều kiện tưới được đáp ứng, chương trình gửi tín hiệu đến chân điều khiển relay để bật máy bơm. Nếu điều kiện không đáp ứng, máy bơm tiếp tục ở trạng thái tắt theo logic đã thiết kế.

**Lưu ý kỹ thuật:** CPU không trực tiếp cấp điện cho máy bơm. Bộ điều khiển phải sử dụng mạch giao tiếp hoặc relay tương thích, đáp ứng yêu cầu an toàn điện và công suất của thiết bị.

## 2.7. Mô hình kim tự tháp DIKW

DIKW là mô hình mô tả quá trình chuyển hóa từ dữ liệu thô thành thông tin, tri thức và hành động có ích.

### Sơ đồ kim tự tháp DIKW

### Các cấp độ DIKW trong Smart-Farm

**1. Data – Dữ liệu**

Cảm biến ghi nhận nhiệt độ môi trường là `36°C` và độ ẩm đất là `25%`.

**2. Information – Thông tin**

Dữ liệu cho thấy nhiệt độ đang cao và độ ẩm đất thấp so với ngưỡng cấu hình.

**3. Knowledge – Tri thức**

Kết hợp dữ liệu cảm biến với nhu cầu nước của cây trồng để nhận định khu vực có thể cần tưới.

**4. Wisdom – Trí tuệ**

Đánh giá điều kiện thực tế, kiểm tra các giới hạn an toàn và quyết định tưới lượng nước phù hợp. Sau đó, hệ thống tiếp tục theo dõi độ ẩm để tránh tưới quá mức.

*Các số liệu trên chỉ nhằm minh họa. Quyết định tưới thực tế cần xét loại cây, giai đoạn sinh trưởng, hiệu chuẩn cảm biến và điều kiện thời tiết.*

---

# PHẦN 3. KIỂM THỬ VÀ XỬ LÝ SỰ CỐ RAM ĐẦY

## 3.1. Tình huống

Giả định hệ thống Smart-Farm ghi quá nhiều dữ liệu nhật ký vào RAM. Bộ nhớ có thể tăng cao khiến chương trình chạy chậm, mất kết nối hoặc ngừng phản hồi.

## 3.2. Quy trình xử lý an toàn

1. **Kiểm tra bộ nhớ:** Theo dõi mức sử dụng RAM và xác định tiến trình hoặc bộ đệm nhật ký tiêu thụ nhiều bộ nhớ.
2. **Giới hạn bộ đệm:** Chỉ giữ lượng nhật ký cần thiết trong RAM, tránh lưu toàn bộ lịch sử trong bộ nhớ.
3. **Lưu nhật ký phù hợp:** Ghi dữ liệu theo từng phần vào bộ nhớ lưu trữ hoặc máy chủ nếu thiết bị hỗ trợ.
4. **Xoay vòng nhật ký:** Giới hạn dung lượng và thời gian lưu trữ, sao lưu những dữ liệu cần thiết trước khi xóa.
5. **Bảo vệ hệ thống tưới:** Không xóa file cấu hình, ngắt nguồn hoặc khởi động lại liên tục khi chưa đánh giá trạng thái máy bơm.
6. **Khôi phục có kiểm soát:** Kiểm tra cảm biến, kết nối và thiết bị chấp hành trước khi bật lại chế độ tự động.

**Không nên:** Xóa toàn bộ thư mục dữ liệu hoặc nhật ký một cách tùy tiện. Cần xác định nguyên nhân, bảo toàn dữ liệu quan trọng và xử lý theo chính sách lưu trữ.

## 3.3. Bảng kiểm thử

| Mã kiểm thử | Thao tác                       | Kết quả mong đợi                                                                  |
| ----------- | ------------------------------ | --------------------------------------------------------------------------------- |
| TC01        | Ghi lượng nhật ký lớn liên tục | Bộ đệm có giới hạn, RAM không tăng vô hạn                                         |
| TC02        | Giả lập bộ nhớ gần đầy         | Hệ thống cảnh báo và thực hiện cơ chế giảm tải                                    |
| TC03        | Kiểm tra xoay vòng nhật ký     | Nhật ký cũ được xử lý theo chính sách lưu trữ                                     |
| TC04        | Mất mạng trong khi tưới        | Hệ thống xử lý theo chế độ an toàn đã thiết kế                                    |
| TC05        | Khởi động lại sau sự cố        | Cấu hình được đọc lại và trạng thái thiết bị được kiểm tra trước khi tưới tự động |

## 3.4. Các sự cố thường gặp

| Sự cố                     | Cách xử lý                                                             |
| ------------------------- | ---------------------------------------------------------------------- |
| Cảm biến không có dữ liệu | Kiểm tra dây nối, nguồn điện và kết nối                                |
| Máy bơm không hoạt động   | Kiểm tra nguồn, relay, đường ống và bảo vệ quá tải                     |
| Nhiệt độ bất thường       | Kiểm tra vị trí lắp đặt và hiệu chuẩn cảm biến                         |
| RAM sử dụng quá cao       | Giới hạn bộ đệm, xoay vòng nhật ký và kiểm tra rò rỉ bộ nhớ            |
| Mất kết nối mạng          | Kiểm tra mạng và duy trì chế độ vận hành an toàn tại chỗ nếu có hỗ trợ |

---

# KẾT LUẬN

Smart-Farm giúp trang trại Lan theo dõi điều kiện môi trường và hỗ trợ tự động hóa hoạt động tưới tiêu. Việc sử dụng README.md giúp người vận hành nắm được cấu trúc hệ thống, quy trình cài đặt, nguyên lý điều khiển và cách xử lý sự cố.

Quản lý bộ nhớ và nhật ký đúng cách giúp hệ thống hoạt động ổn định, an toàn và dễ bảo trì.

**Thông tin tài liệu:**

* **Tên dự án:** Smart-Farm IoT
* **Tên tệp:** `README.md`
* **Đối tượng sử dụng:** Người vận hành và quản lý trang trại Lan
* **Định dạng:** Markdown
* **Công cụ xem trước:** StackEdit

# QUY ĐỊNH NỘP BÀI

1. Lưu nội dung trên thành tệp `README.md`.
2. Mở tệp bằng StackEdit và kiểm tra các tiêu đề, bảng, danh sách, blockquote và khối mã.
3. Đặt ảnh sơ đồ tại đường dẫn `docs/smart-farm-architecture.png` để hình ảnh hiển thị đúng.
4. Kiểm tra Alt Text của ảnh để bảo đảm có mô tả thay thế.
5. Kiểm tra nội dung hướng dẫn xử lý RAM đầy và bảng kiểm thử trước khi nộp bài.
