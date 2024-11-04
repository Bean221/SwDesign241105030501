# Phân tích Các Ca Sử Dụng trong Hệ Thống Payroll System

## Kiến Trúc Client-Server

### 1. Quản lý Nhân viên

#### a. Thêm Nhân viên
- **Mô tả**: Quản trị viên thêm thông tin của nhân viên mới vào hệ thống.
- **Thao tác**:
  1. Đăng nhập với quyền quản trị.
  2. Truy cập giao diện "Thêm Nhân viên".
  3. Nhập thông tin nhân viên (họ tên, mã nhân viên, ngày sinh, địa chỉ, phòng ban, vị trí, lương cơ bản).
  4. Nhấn "Lưu" để hoàn tất.
- **Kết quả**: Nhân viên mới được lưu vào hệ thống.

#### b. Cập nhật Thông tin Nhân viên
- **Mô tả**: Cập nhật thông tin của nhân viên hiện có.
- **Thao tác**:
  1. Đăng nhập vào hệ thống.
  2. Chọn "Danh sách Nhân viên".
  3. Tìm và chọn nhân viên cần cập nhật.
  4. Sửa đổi thông tin và nhấn "Cập nhật".
- **Kết quả**: Thông tin nhân viên được cập nhật.

#### c. Xóa Nhân viên
- **Mô tả**: Xóa thông tin nhân viên khỏi hệ thống.
- **Thao tác**:
  1. Đăng nhập với quyền quản trị.
  2. Chọn "Danh sách Nhân viên".
  3. Chọn nhân viên cần xóa.
  4. Nhấn "Xóa" và xác nhận.
- **Kết quả**: Nhân viên bị xóa khỏi hệ thống.

#### d. Xem Thông tin Nhân viên
- **Mô tả**: Xem thông tin chi tiết của một nhân viên.
- **Thao tác**:
  1. Đăng nhập vào hệ thống.
  2. Chọn "Danh sách Nhân viên".
  3. Chọn nhân viên để xem chi tiết.
- **Kết quả**: Thông tin chi tiết của nhân viên được hiển thị.

---

### 2. Quản lý Lương

#### a. Tính Lương
- **Mô tả**: Hệ thống tính lương cho nhân viên dựa trên dữ liệu nhập vào.
- **Thao tác**:
  1. Đăng nhập với quyền quản trị.
  2. Chọn "Tính Lương".
  3. Nhập thời gian làm việc, các khoản phụ cấp, khấu trừ, v.v.
  4. Nhấn "Tính toán".
- **Kết quả**: Hệ thống hiển thị kết quả lương cho từng nhân viên.

#### b. Cập nhật Thông tin Lương
- **Mô tả**: Điều chỉnh thông tin lương của nhân viên.
- **Thao tác**:
  1. Đăng nhập vào hệ thống.
  2. Chọn "Quản lý Lương".
  3. Chọn nhân viên và sửa đổi thông tin lương.
  4. Nhấn "Lưu".
- **Kết quả**: Thông tin lương của nhân viên được cập nhật.

#### c. Xem Bảng Lương
- **Mô tả**: Nhân viên xem bảng lương của mình.
- **Thao tác**:
  1. Nhân viên đăng nhập.
  2. Chọn "Xem Bảng Lương".
  3. Chọn tháng/năm muốn xem.
- **Kết quả**: Bảng lương hiển thị cho nhân viên.

---

### 3. Quản lý Nghỉ phép

#### a. Đăng ký Nghỉ phép
- **Mô tả**: Nhân viên gửi yêu cầu nghỉ phép.
- **Thao tác**:
  1. Nhân viên đăng nhập.
  2. Chọn "Đăng ký Nghỉ phép".
  3. Nhập thông tin (ngày bắt đầu, ngày kết thúc, lý do).
  4. Nhấn "Gửi yêu cầu".
- **Kết quả**: Yêu cầu nghỉ phép được gửi đến quản lý.

#### b. Duyệt Nghỉ phép
- **Mô tả**: Quản lý xem xét và phê duyệt yêu cầu nghỉ phép.
- **Thao tác**:
  1. Quản lý đăng nhập.
  2. Chọn "Danh sách yêu cầu Nghỉ phép".
  3. Xem chi tiết yêu cầu.
  4. Nhấn "Phê duyệt" hoặc "Từ chối".
- **Kết quả**: Trạng thái yêu cầu nghỉ phép được cập nhật.

#### c. Xem Lịch Sử Nghỉ phép
- **Mô tả**: Nhân viên xem lịch sử nghỉ phép của mình.
- **Thao tác**:
  1. Nhân viên đăng nhập.
  2. Chọn "Xem Lịch sử Nghỉ phép".
- **Kết quả**: Danh sách các lần nghỉ phép trước đó được hiển thị.

---

### 4. Báo cáo và Phân tích

#### a. Tạo Báo cáo Lương
- **Mô tả**: Quản trị viên tạo báo cáo tổng hợp về chi phí lương.
- **Thao tác**:
  1. Đăng nhập vào hệ thống.
  2. Chọn "Tạo Báo cáo".
  3. Chọn tiêu chí báo cáo (theo phòng ban, thời gian).
  4. Nhấn "Tạo báo cáo".
- **Kết quả**: Báo cáo lương được tạo và có thể tải về hoặc xem trực tiếp.

#### b. Phân tích Dữ liệu Nhân sự
- **Mô tả**: Hệ thống cung cấp báo cáo về hiệu suất làm việc của nhân viên.
- **Thao tác**:
  1. Quản trị viên đăng nhập.
  2. Chọn "Phân tích Dữ liệu".
  3. Chọn các tiêu chí phân tích.
  4. Nhấn "Xem Báo cáo".
- **Kết quả**: Báo cáo phân tích dữ liệu nhân sự được hiển thị.

---

### 5. Quản lý Người dùng

#### a. Đăng nhập
- **Mô tả**: Người dùng đăng nhập vào hệ thống.
- **Thao tác**:
  1. Mở giao diện đăng nhập.
  2. Nhập tên đăng nhập và mật khẩu.
  3. Nhấn "Đăng nhập".
- **Kết quả**: Người dùng được chuyển đến giao diện chính của hệ thống.

#### b. Đăng xuất
- **Mô tả**: Người dùng đăng xuất khỏi hệ thống.
- **Thao tác**:
  1. Nhấn nút "Đăng xuất".
- **Kết quả**: Người dùng được chuyển về giao diện đăng nhập.

#### c. Quên Mật khẩu
- **Mô tả**: Hệ thống hỗ trợ khôi phục mật khẩu.
- **Thao tác**:
  1. Nhấn "Quên Mật khẩu?".
  2. Nhập địa chỉ email đã đăng ký.
  3. Nhận email hướng dẫn để đặt lại mật khẩu.
- **Kết quả**: Người dùng có thể thiết lập lại mật khẩu mới.

---

### 6. Tích hợp và Bảo mật

#### a. Xác thực Người dùng
- **Mô tả**: Hệ thống kiểm tra thông tin đăng nhập của người dùng.
- **Thao tác**:
  1. Người dùng nhập tên và mật khẩu.
  2. Hệ thống xác thực và chuyển hướng đến giao diện phù hợp.
- **Kết quả**: Người dùng được xác thực thành công hoặc thông báo lỗi.

#### b. Quản lý Quyền Truy cập
- **Mô tả**: Quản trị viên thiết lập quyền truy cập cho người dùng.
- **Thao tác**:
  1. Quản trị viên đăng nhập.
  2. Chọn "Quản lý Người dùng".
  3. Chọn người dùng và điều chỉnh quyền truy cập.
  4. Nhấn "Lưu".
- **Kết quả**: Quyền truy cập của người dùng được cập nhật.

---

## Kết luận
Phân tích chi tiết các ca sử dụng này giúp xác định rõ chức năng và quy trình trong hệ thống Payroll System. Điều này tạo điều kiện thuận lợi cho việc thiết kế, phát triển và kiểm thử hệ thống. Nếu bạn cần thêm thông tin hoặc muốn tập trung vào một phần cụ thể nào, hãy cho tôi biết!
