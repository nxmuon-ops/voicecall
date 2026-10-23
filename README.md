# Care Agent — Trợ lý AI chăm sóc khách hàng bằng giọng nói

**Tự động hóa cuộc gọi chăm sóc khách hàng, cá nhân hóa hội thoại và ghi nhận phản hồi trong một quy trình thống nhất.**

Care Agent là ứng dụng Windows hỗ trợ doanh nghiệp thực hiện các cuộc gọi chăm sóc khách hàng bằng AI. Từ danh sách Excel, phần mềm lựa chọn khách đủ điều kiện, thực hiện cuộc gọi theo lịch, trao đổi dựa trên thông tin dịch vụ và cập nhật kết quả sau cuộc gọi.

Phiên bản hiện tại tích hợp **WhatsApp Desktop**, được thiết kế theo các thành phần tách biệt để thuận tiện phát triển thêm kênh giao tiếp và hệ thống nghiệp vụ trong tương lai.

## Bài toán giải quyết

Việc gọi điện hỏi thăm sau dịch vụ thường cần nhiều thao tác: đọc thông tin khách, tra cứu kịch bản, quay số, ghi nhận phản hồi và cập nhật kết quả. Khi số lượng khách tăng, doanh nghiệp khó duy trì cách chăm sóc nhất quán và dễ bỏ sót phản ánh cần xử lý.

Care Agent kết nối những bước này thành một luồng vận hành có sự kiểm soát của người dùng. AI đảm nhiệm phần trao đổi và ghi nhận ban đầu; nhân viên phụ trách tiếp nhận các trường hợp cần xử lý tiếp.

## Tính năng hiện có

### 1. Quản lý danh sách và kết quả bằng Excel

- Đọc số điện thoại, họ tên, lịch sử dịch vụ và cách xưng hô của khách.
- Kiểm tra tiêu đề cột, định dạng số điện thoại và dữ liệu trùng trước khi bắt đầu.
- Chỉ xử lý khách có trạng thái `ChuaGoi` trong danh sách.
- Cập nhật trạng thái, thời gian và tóm tắt phản hồi sau cuộc gọi.
- Cho phép người vận hành chủ động đưa khách vào lượt gọi lại bằng cách điều chỉnh trạng thái Excel theo nhu cầu; yêu cầu ngừng liên hệ cần được tôn trọng.

### 2. Hội thoại AI theo ngữ cảnh khách hàng

- Sử dụng tên khách, dịch vụ và cách xưng hô để cá nhân hóa nội dung.
- Giới thiệu rõ đây là trợ lý AI của doanh nghiệp.
- Nhận dạng tiếng Việt và tạo giọng nói bằng các thành phần xử lý âm thanh cục bộ.
- Duy trì ngữ cảnh trong từng cuộc gọi để trao đổi nhiều lượt.
- Hỗ trợ ngắt lời: khi phát hiện khách bắt đầu nói, Agent dừng phát và hủy phản hồi cũ đang chờ.
- Ghi nhận góp ý, khiếu nại và yêu cầu hỗ trợ vào phần tóm tắt kết quả.
- Xử lý yêu cầu ngừng liên hệ bằng trạng thái riêng.

### 3. Kịch bản và nghiệp vụ có thể bổ sung

Prompt chung quy định vai trò, phong cách giao tiếp và giới hạn của Agent. Các tài liệu nghiệp vụ được tổ chức thành file riêng, lựa chọn bằng mã dịch vụ trong Excel.

Ví dụ: mã `Implant_SauCayTru` liên kết với tài liệu chăm sóc tương ứng trong thư mục `NghiepVu`. Khi có mã hợp lệ, phần mềm nạp nội dung đã được duyệt vào ngữ cảnh cuộc gọi. Doanh nghiệp có thể bổ sung nghiệp vụ mới theo cấu trúc file quy định, không cần sửa luồng gọi chính.

Ứng dụng kiểm tra mã, nội dung và trạng thái phê duyệt trước khi gọi. Với lĩnh vực y tế, nội dung phải được người có chuyên môn phê duyệt; Agent hỗ trợ truyền đạt và ghi nhận, không thay thế bác sĩ.

### 4. Hàng đợi theo lịch, có người vận hành kiểm soát

- Cấu hình khung giờ hoạt động, chu kỳ quét và khoảng nghỉ giữa các cuộc.
- Thực hiện từng cuộc gọi tuần tự.
- Có nút bắt đầu, dừng và kết thúc cuộc gọi.
- Chạy tại khay hệ thống trong phiên Windows đã đăng nhập.
- Khởi động lại ứng dụng luôn ở trạng thái dừng, không tự tiếp tục quay số.
- Sau khi hết khách đủ điều kiện, hàng đợi có thể tiếp tục chờ lượt quét tiếp theo cho đến khi người dùng dừng.

### 5. Kiểm tra trước khi gọi và xử lý tình huống không rõ

- Xác minh đúng người nhận trước khi bấm gọi.
- Chỉ phát lời chào sau khi xác nhận cuộc gọi đã được nhấc máy.
- Hỗ trợ tự chọn và xác minh thiết bị âm thanh WhatsApp theo chính sách của hàng đợi.
- Có chức năng gọi thử và checklist nghiệm thu cấu hình.
- Dừng để kiểm tra khi mất thiết bị, khóa phiên Windows hoặc không xác định được trạng thái giao diện.
- Phân biệt hội thoại hoàn tất với cuộc gọi gián đoạn, thay vì coi mọi lần quay số là thành công.

### 6. Lưu kết quả bền vững

SQLite lưu lịch sử lần gọi và kết quả đang chờ ghi Excel. Workbook không bị giữ mở trong suốt cuộc gọi.

Nếu Excel đang bị khóa hoặc ghi file thất bại, kết quả được giữ lại để xuất sau. Phần mềm không gọi lại khách chỉ vì chưa ghi được kết quả vào file. Khi khôi phục sau sự cố, lần gọi chưa chốt được đưa vào trạng thái cần kiểm tra.

## Quy trình sử dụng

1. **Chuẩn bị dữ liệu:** nhập khách đã đồng ý nhận cuộc gọi vào Excel; điền thông tin dịch vụ và cách xưng hô nếu có.
2. **Thiết lập nội dung:** cấu hình doanh nghiệp, prompt và tài liệu nghiệp vụ đã duyệt.
3. **Kiểm chứng môi trường:** đăng nhập WhatsApp Desktop, chọn tuyến âm thanh và thực hiện cuộc gọi thử.
4. **Bật hàng đợi:** Agent xử lý các dòng `ChuaGoi` trong khung giờ được cấu hình.
5. **Theo dõi kết quả:** xem trạng thái, thời gian và ghi chú trong Excel; tiếp nhận các trường hợp cần nhân viên hỗ trợ.

### Cấu trúc dữ liệu Excel

| Cột | Nội dung |
|---|---|
| `SDT` | Số điện thoại, lưu dạng văn bản để giữ số 0 đầu và mã quốc gia |
| `HoTen` | Tên khách hàng |
| `LichSuDichVu` | Mô tả dịch vụ hoặc mã nghiệp vụ được hỗ trợ |
| `TrangThai` | Điều kiện gọi và kết quả xử lý |
| `ThoiGianGoi` | Thời điểm thực hiện cuộc gọi |
| `GhiChu` | Tóm tắt trao đổi, góp ý hoặc yêu cầu hỗ trợ |
| `XungHo` | Cột tùy chọn: Anh, Chị, Cô, Chú… |

### Các trạng thái chính

| Trạng thái | Ý nghĩa |
|---|---|
| `ChuaGoi` | Chờ xử lý theo hàng đợi |
| `DaGoi` | Hội thoại đã được chốt hoàn tất và đáp ứng điều kiện kết thúc của ứng dụng |
| `KhongTraLoi` | Hết thời hạn đổ chuông hoặc kênh gọi xác nhận không trả lời |
| `MayBan` | Kênh gọi xác nhận máy bận |
| `Loi` | Lỗi ở bước chuẩn bị trước khi quay số |
| `CanKiemTra` | Gián đoạn, trạng thái không rõ hoặc chưa chốt được hội thoại |
| `TuChoiLienHe` | Khách yêu cầu ngừng liên hệ |

## Kiến trúc và nền tảng kỹ thuật

Ứng dụng sử dụng **C# / .NET 8, WPF**, với các thành phần chính:

| Thành phần | Vai trò |
|---|---|
| WPF Desktop | Giao diện cấu hình, giám sát và điều khiển |
| ClosedXML | Đọc, kiểm tra và cập nhật Excel |
| SQLite | Lưu lịch sử và kết quả chờ xuất |
| FlaUI UIA3 | Điều khiển và đọc trạng thái WhatsApp Desktop |
| NAudio / WASAPI | Thu, phát và định tuyến âm thanh |
| PhoWhisper / Whisper | Nhận dạng tiếng Việt cục bộ |
| Dialogue Agent | Xử lý ngữ cảnh và tạo phản hồi hội thoại |
| Windows TTS | Tổng hợp giọng nói tiếng Việt |

Luồng xử lý chính:

```text
Excel → Hàng đợi → Xác minh người nhận → Cuộc gọi WhatsApp
                                           ↕
                     Nhận dạng tiếng Việt ↔ Agent ↔ Giọng nói
                                           ↓
                              Kết quả → SQLite → Excel
```

Nhận dạng và tổng hợp giọng nói được xử lý cục bộ. Văn bản hội thoại cùng ngữ cảnh cần thiết được gửi đến dịch vụ mô hình đối thoại qua bộ tích hợp hiện tại; đây không phải giải pháp hoạt động hoàn toàn ngoại tuyến.

Phiên đối thoại được duy trì riêng cho từng cuộc gọi để giảm chi phí khởi tạo giữa các lượt. Thời gian phản hồi còn phụ thuộc thiết bị, độ dài câu nói, mạng và dịch vụ mô hình; không cam kết độ trễ cố định.

## Khả năng mở rộng

Các interface `ICustomerRepository`, `ICallController`, `IAudioBridge`, `IVoiceSession` và `ICallQueue` tách trách nhiệm dữ liệu, kênh gọi, âm thanh, hội thoại và điều phối. Cách tổ chức này tạo nền tảng để bổ sung adapter mới và tái sử dụng phần nghiệp vụ chung.

**Các hướng dưới đây là lộ trình phát triển, chưa phải tính năng tích hợp sẵn của bản hiện tại.**

| Hướng mở rộng | Giá trị dự kiến | Công việc cần triển khai |
|---|---|---|
| **Zalo, Viber, Messenger** | Tiếp cận khách trên thêm kênh giao tiếp | Khảo sát khả năng tích hợp được nền tảng cho phép; xây adapter điều khiển, xác minh người nhận, trạng thái và âm thanh |
| **CRM / hệ thống quản lý khách hàng** | Đồng bộ hồ sơ, lịch hẹn và kết quả CSKH | Bổ sung repository, ánh xạ dữ liệu, xác thực và cơ chế đồng bộ |
| **Ticket / Helpdesk** | Chuyển phản ánh thành yêu cầu có người phụ trách | Tích hợp tạo ticket, phân công và theo dõi trạng thái |
| **Tổng đài / SIP** | Phát triển kênh gọi điện thoại chuyên dụng | Tích hợp nền tảng thoại, tín hiệu cuộc gọi và quản lý phiên |
| **TTS chuyên dụng** | Thêm lựa chọn giọng đọc, gồm giọng miền Nam | Tích hợp engine giọng nói, đo độ trễ và kiểm chứng chất lượng |
| **Dashboard và báo cáo** | Theo dõi kết quả theo chiến dịch, dịch vụ, thời gian | Bổ sung mô hình báo cáo, thống kê và giao diện phân tích |
| **Web API / Webhook** | Kết nối quy trình tự động với ứng dụng khác | Thiết kế API, phân quyền, hàng đợi sự kiện và xử lý lỗi |

Mỗi nền tảng có cơ chế gọi, quyền truy cập và điều khoản riêng. Việc mở rộng cần được đánh giá và kiểm chứng độc lập; không đơn thuần thay tên ứng dụng hoặc một bộ selector. Bản hiện tại chưa cung cấp HTTP API, tích hợp các kênh trên hay chuyển cuộc gọi trực tiếp cho nhân viên.

## Quyền riêng tư và vận hành

- Chỉ sử dụng danh sách khách đã đồng ý nhận cuộc gọi và tôn trọng yêu cầu ngừng liên hệ.
- Ứng dụng không tự lưu bản ghi âm hoặc transcript đầy đủ lâu dài; lưu kết quả và tóm tắt trong Excel/SQLite.
- Người vận hành kiểm soát nội dung prompt, tài liệu nghiệp vụ và quyền truy cập thư mục dữ liệu.
- WhatsApp Desktop RPA phụ thuộc giao diện và phiên bản ứng dụng; cần kiểm chứng lại khi môi trường thay đổi.
- Phần điều khiển giao diện chạy trong phiên Windows đã đăng nhập. Khóa màn hình hoặc mất điều kiện vận hành có thể khiến hàng đợi dừng.
- Khoảng nghỉ giữa cuộc gọi không bảo đảm tránh giới hạn hay khóa tài khoản của nền tảng.

## Video demo

[![Xem video demo Care Agent trên YouTube](https://img.youtube.com/vi/-NBVqjuH4jk/hqdefault.jpg)](https://youtu.be/-NBVqjuH4jk)

**[▶ Xem video demo trên YouTube](https://youtu.be/-NBVqjuH4jk)**

Nhấn vào ảnh để xem video minh họa trải nghiệm vận hành và hội thoại của ứng dụng. Khi chia sẻ bản demo, nên dùng hồ sơ thử nghiệm và người tham gia đồng ý được ghi hình, ghi âm.

## Định hướng sản phẩm

Care Agent hướng đến một nền tảng trợ lý CSKH giọng nói có thể cấu hình theo doanh nghiệp: bắt đầu từ quy trình Excel quen thuộc, chuẩn hóa nội dung chăm sóc và từng bước kết nối thêm kênh giao tiếp, CRM và hệ thống hỗ trợ.

**Trọng tâm của sản phẩm là cá nhân hóa hội thoại, ghi nhận kết quả có cấu trúc và giữ quyền kiểm soát cho người vận hành.**
