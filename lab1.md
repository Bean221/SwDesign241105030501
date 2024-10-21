## lab01
Đề Xuất Kiến Trúc
Kiến trúc Client-Server với các thành phần như sau:

Client Application (Ứng dụng phía khách hàng)

Giao diện người dùng: Ứng dụng desktop trên nền Windows cho nhân viên nhập thẻ thời gian, đơn đặt hàng và tạo báo cáo.
Chức năng bảo mật: Kiểm soát quyền truy cập, chỉ cho phép nhân viên truy cập thông tin của chính họ.
Application Server (Máy chủ ứng dụng)

Logic xử lý: Xử lý tính toán tiền lương, quản lý người dùng và logic tính toán hoa hồng.
API: Cung cấp API để tương tác với cơ sở dữ liệu và DB2.
Database Server (Máy chủ cơ sở dữ liệu)

Cơ sở dữ liệu nhân viên: Lưu trữ thông tin nhân viên, thẻ thời gian và đơn đặt hàng.
Tích hợp với DB2: Truy cập thông tin từ cơ sở dữ liệu DB2 mà không cần cập nhật.
Scheduler Service (Dịch vụ lập lịch)

Tự động hóa quy trình: Thực hiện quy trình trả lương tự động vào các ngày quy định (thứ Sáu và ngày cuối cùng của tháng).
Lý Do Lựa Chọn Kiến Trúc
Khả năng mở rộng: Dễ dàng mở rộng để thêm nhiều nhân viên hoặc tính năng mới.
Bảo mật: Bảo vệ dữ liệu cá nhân của nhân viên thông qua kiểm soát truy cập chặt chẽ.
Tính tự động: Giảm thiểu can thiệp thủ công và tự động hóa quy trình thanh toán.
![Biểu Đồ Package Mô Tả Kiến Trúc](https://www.planttext.com/api/plantuml/png/R55BRiCW4DrpYb7ssVG0LUmu2wGkB4LUHLbCoJH1nM01ZXH5ELaMFLAlK3wnGwiYWPWFxpDytxzMpgFrOwyO6r1yuf5WiLQIj8Tg69GKwANH2xWo26lNERB0jIVxWOBsW0uwNfGg8SWvM1ljhL6fdbFiLX0KoB0bUoOx4zIZapf2l9cZ50aWtNArQdd6RFalm0OzlgEZlsYRVb3cGWHJGtezPPiwTpNroqDbAeVm7yrRSQB3g8B7o245pIGjNe9N1TNeJPzCPOrp674w3ilbwpICnvXY9hjBP-u8ri9EzqBeb7gAAvuycTYAz27-vWy0003__mC0)

