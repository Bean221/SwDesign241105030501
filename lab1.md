# Lab01 

# 1.Phân Tích Kiến Trúc

# Đề Xuất Kiến Trúc Client-Server

## 1. Phân chia trách nhiệm rõ ràng
Trong kiến trúc Client-Server:
- **Client** đảm nhiệm việc thu thập dữ liệu, hiển thị giao diện người dùng, và xử lý tương tác.
- **Server** chịu trách nhiệm xử lý nghiệp vụ, quản lý dữ liệu và xử lý các yêu cầu từ nhiều Client khác nhau.

Sự phân chia này giúp cải thiện tính rõ ràng và dễ bảo trì của hệ thống.

## 2. Khả năng mở rộng
Khi nhu cầu hệ thống tăng lên:
- Có thể tăng số lượng hoặc công suất của các server để đáp ứng nhu cầu.
- Bổ sung thêm các Client mà không cần thiết kế lại hệ thống từ đầu.

Điều này giúp kiến trúc Client-Server dễ dàng mở rộng theo nhu cầu thực tế.

## 3. Bảo mật tốt hơn
Dữ liệu thường được lưu trữ và quản lý tập trung ở phía Server, giúp:
- Dễ dàng quản lý truy cập và bảo vệ dữ liệu.
- Áp dụng các biện pháp bảo mật như xác thực, mã hóa, và tường lửa ở phía Server để bảo vệ toàn bộ hệ thống.

## 4. Tối ưu hóa hiệu năng
- Client không cần xử lý nhiều tác vụ phức tạp mà chỉ thực hiện yêu cầu với Server, giảm tải xử lý cho máy người dùng.
- Server được thiết kế mạnh mẽ, tối ưu cho xử lý khối lượng lớn dữ liệu, đảm bảo hiệu suất tổng thể của hệ thống.

## 5. Dễ dàng bảo trì và cập nhật
- Các cập nhật hay thay đổi chỉ cần triển khai ở phía Server, mà không ảnh hưởng đến Client.
- Điều này giúp đơn giản hóa quá trình triển khai và bảo trì, giảm chi phí quản lý.

## 6. Hỗ trợ môi trường phân tán
Mô hình Client-Server hỗ trợ:
- Nhiều Client kết nối với một hoặc nhiều Server từ các vị trí khác nhau.
- Phù hợp cho các hệ thống phân tán như hệ thống quản lý tập trung, các dịch vụ web, hoặc các ứng dụng doanh nghiệp.

---

Nhờ vào các ưu điểm trên, kiến trúc Client-Server là lựa chọn phù hợp cho nhiều ứng dụng yêu cầu khả năng mở rộng, tính bảo mật cao, và hiệu năng tối ưu trong môi trường kết nối nhiều người dùng.

Kiến trúc Client-Server với các thành phần như sau:

### Client Application (Ứng dụng phía khách hàng)

- **Giao diện người dùng**: Ứng dụng desktop trên nền Windows cho nhân viên nhập thẻ thời gian, đơn đặt hàng và tạo báo cáo.
- **Chức năng bảo mật**: Kiểm soát quyền truy cập, chỉ cho phép nhân viên truy cập thông tin của chính họ.

### Application Server (Máy chủ ứng dụng)

- **Logic xử lý**: Xử lý tính toán tiền lương, quản lý người dùng và logic tính toán hoa hồng.
- **API**: Cung cấp API để tương tác với cơ sở dữ liệu và DB2.

### Database Server (Máy chủ cơ sở dữ liệu)

- **Cơ sở dữ liệu nhân viên**: Lưu trữ thông tin nhân viên, thẻ thời gian và đơn đặt hàng.
- **Tích hợp với DB2**: Truy cập thông tin từ cơ sở dữ liệu DB2 mà không cần cập nhật.

### Scheduler Service (Dịch vụ lập lịch)

- **Tự động hóa quy trình**: Thực hiện quy trình trả lương tự động vào các ngày quy định (thứ Sáu và ngày cuối cùng của tháng).

## Lý Do Lựa Chọn Kiến Trúc

- **Khả năng mở rộng**: Dễ dàng mở rộng để thêm nhiều nhân viên hoặc tính năng mới.
- **Bảo mật**: Bảo vệ dữ liệu cá nhân của nhân viên thông qua kiểm soát truy cập chặt chẽ.
- **Tính tự động**: Giảm thiểu can thiệp thủ công và tự động hóa quy trình thanh toán.

### Biểu Đồ Package Mô Tả Kiến Trúc

![Biểu Đồ Package Mô Tả Kiến Trúc](https://www.planttext.com/api/plantuml/png/R55BRiCW4DrpYb7ssVG0LUmu2wGkB4LUHLbCoJH1nM01ZXH5ELaMFLAlK3wnGwiYWPWFxpDytxzMpgFrOwyO6r1yuf5WiLQIj8Tg69GKwANH2xWo26lNERB0jIVxWOBsW0uwNfGg8SWvM1ljhL6fdbFiLX0KoB0bUoOx4zIZapf2l9cZ50aWtNArQdd6RFalm0OzlgEZlsYRVb3cGWHJGtezPPiwTpNroqDbAeVm7yrRSQB3g8B7o245pIGjNe9N1TNeJPzCPOrp674w3ilbwpICnvXY9hjBP-u8ri9EzqBeb7gAAvuycTYAz27-vWy0003__mC0)
# 2.Cơ Chế Phân Tích

Dưới đây là danh sách các cơ chế cần giải quyết trong hệ thống cùng lý do cho mỗi cơ chế:

## Cơ Chế Kiểm Soát Truy Cập

- **Giải thích**: Đảm bảo rằng mỗi nhân viên chỉ có quyền truy cập và chỉnh sửa thông tin của chính họ, bảo vệ dữ liệu cá nhân và thông tin nhạy cảm.

## Cơ Chế Tính Toán Tiền Lương

- **Giải thích**: Cần phát triển logic để tính toán tiền lương cho nhân viên theo giờ, lương cố định, và hoa hồng. Điều này bao gồm việc xử lý giờ làm thêm và các quy tắc thanh toán khác nhau.

## Cơ Chế Xử Lý Đơn Đặt Hàng

- **Giải thích**: Đối với nhân viên có hoa hồng, cần có cơ chế để nhập và xử lý đơn đặt hàng nhằm tính toán hoa hồng chính xác.

## Cơ Chế Tạo Báo Cáo

- **Giải thích**: Cung cấp khả năng cho nhân viên tạo và truy cập các báo cáo về giờ làm việc, tổng lương, và thời gian nghỉ phép. Cơ chế này cần dễ sử dụng và nhanh chóng.

## Cơ Chế Tự Động Hóa Quy Trình

- **Giải thích**: Thiết lập lịch trình cho các quy trình tự động như tính toán tiền lương và phát hành phiếu lương để giảm thiểu can thiệp thủ công.

## Cơ Chế Tích Hợp Cơ Sở Dữ Liệu

- **Giải thích**: Thiết lập API an toàn để truy cập thông tin từ cơ sở dữ liệu DB2 mà không gây ảnh hưởng đến tính toàn vẹn của dữ liệu.

## Cơ Chế Bảo Mật Dữ Liệu

- **Giải thích**: Mã hóa thông tin nhạy cảm như dữ liệu ngân hàng và địa chỉ để đảm bảo an toàn cho dữ liệu cá nhân.
# 3. Ca Sử Dụng: Payment

### Các Lớp Phân Tích

- **Employee**: Nhân viên nhận thanh toán.
- **PayrollSystem**: Hệ thống xử lý tiền lương.
- **PaymentProcessor**: Xử lý các giao dịch thanh toán.
- **Bank**: Đối tác thực hiện thanh toán.

### Biểu Đồ Sequence

![Biểu Đồ Package Mô Tả Kiến Trúc](https://www.planttext.com/api/plantuml/png/V53B3S8m3Brd2Y_00ZcW2iGLLLGC4BMkLE749NOEcQq7Hc855AbKBGYkx-Vt_9mUbQYBcZmPS_8ZSKQ4tHvgboCJDLaKlOKBtXEA5jXZKBEXPtqXwiWjYd2qS7JK9dAAQzD6Ktm75suMPcXH5lH7AeT-YFvlvaVtwzYjMa2ZJfDyBtYljt1c7Vgyd30LXguyw0K00F__0m00)

---

# 4. Ca Sử Dụng: Maintain Timecard

### Các Lớp Phân Tích

- **Employee**: Nhân viên nhập thẻ thời gian.
- **Timecard**: Đại diện cho thẻ thời gian.
- **TimecardManager**: Quản lý các thẻ thời gian.
- **Database**: Nơi lưu trữ dữ liệu thẻ thời gian.

### Biểu Đồ Sequence

![Biểu Đồ Package Mô Tả Kiến Trúc](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3XUNQsv1JdvbQgg2hfr2I6PkQd9YKOflObvYUcgHbO9hNabg4LoO2qqUMOkLWdDHQc99Abm0fBUe4fiMbyIInAJ4ubGhXU34CeG6BfWuLfSuv-UbPHRbWhLWCnJc3Ii5l_oIpBHAXU3IvEJKuc8kBeVKl1IGJm40003__mC0)
## Tóm Tắt

Cả hai ca sử dụng đều hướng tới việc cải thiện quy trình quản lý và thanh toán, với các lớp phân tích cụ thể giúp đảm bảo tính chính xác và hiệu quả trong việc xử lý thông tin. Hệ thống cần được thiết kế để tự động hóa và tối ưu hóa cả hai quy trình này, từ việc thanh toán cho nhân viên đến việc quản lý thời gian làm việc của họ.



