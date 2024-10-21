# lab01

# Phân Tích Kiến Trúc

## Đề Xuất Kiến Trúc

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

![Biểu Đồ Package Mô Tả Kiến Trúc](https://www.planttext.com/api/plantuml/png/R55BRiCW4DrpYb7ssVG0LUmu2wGkB4LUHLbCoJH1nM01ZXH5ELaMFLAlK3wnGwiYWPWFxpDytxzMpgFrOwyO6r1yuf5WiLQIj8Tg69GKwANH2xWo26lNERB0jIVxWOBsW0uwNfGg8SWvM1ljhL6fdbFiLX0KoB0bUoOx4zIZapf2l9cZ50aWtNArQdd6RFalm0OzlgEZlsYRVb3cGWHJGtezPPiwTpNroqDbAeVm7yrRSQB3g8B7o245pIGjNe9N1TNeJPzCPOrp674w3ilbwpICnvXY9hjBP-u8ri9EzqBeb7gAAvuycTYAz27-vWy0003__mC0)
# Cơ Chế Phân Tích

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



