# Lab 2 Lê Minh Tuấn
# Các Phân Tích Còn Lại Trong Payroll System 
## 1. Select Payment

### Mô tả
Người dùng chọn phương thức thanh toán cho đơn hàng của họ trong quy trình mua sắm trực tuyến.

### Các bước thực hiện
1. **Khởi động**
   - Người dùng truy cập trang thanh toán sau khi đã thêm sản phẩm vào giỏ hàng.
   
2. **Hiển thị tùy chọn thanh toán**
   - Hệ thống hiển thị các phương thức thanh toán có sẵn (ví dụ: thẻ tín dụng, PayPal, chuyển khoản ngân hàng, tiền mặt khi nhận hàng).

3. **Người dùng chọn phương thức thanh toán**
   - Người dùng chọn một trong các phương thức thanh toán bằng cách nhấn vào lựa chọn tương ứng.

4. **Nhập thông tin cần thiết**
   - Nếu phương thức thanh toán yêu cầu thông tin bổ sung (ví dụ: số thẻ tín dụng, địa chỉ PayPal), người dùng nhập thông tin.

5. **Xác nhận lựa chọn**
   - Hệ thống hiển thị tóm tắt phương thức thanh toán đã chọn và thông tin nhập vào.
   - Người dùng xác nhận lựa chọn hoặc quay lại để chỉnh sửa.

6. **Xử lý thanh toán**
   - Hệ thống gửi yêu cầu thanh toán đến cổng thanh toán tương ứng.
   - Nhận phản hồi từ cổng thanh toán (thành công hoặc thất bại).

7. **Kết quả thanh toán**
   - Nếu thanh toán thành công:
     - Hiển thị thông báo thành công.
     - Cập nhật trạng thái đơn hàng.
   - Nếu thanh toán thất bại:
     - Hiển thị thông báo lỗi.
     - Cho phép người dùng chọn lại phương thức thanh toán hoặc thử lại.

### Các yếu tố liên quan
- **Người dùng**: Cá nhân thực hiện giao dịch.
- **Hệ thống**: Trang web hoặc ứng dụng hỗ trợ mua sắm.
- **Cổng thanh toán**: Dịch vụ xử lý giao dịch (ví dụ: Stripe, PayPal).

---

## 2. Create Employee

### Mô tả
Người quản trị thêm một nhân viên mới vào hệ thống.

### Các bước thực hiện
1. **Khởi động**
   - Quản trị viên truy cập trang quản lý nhân viên.

2. **Hiển thị form thêm nhân viên**
   - Hệ thống hiển thị form yêu cầu thông tin cần thiết (tên, địa chỉ, email, số điện thoại, vị trí, v.v.).

3. **Nhập thông tin nhân viên**
   - Quản trị viên nhập thông tin vào các trường tương ứng.

4. **Xác nhận thông tin**
   - Hệ thống hiển thị tóm tắt thông tin đã nhập.
   - Quản trị viên xác nhận hoặc chỉnh sửa thông tin.

5. **Lưu thông tin nhân viên**
   - Hệ thống lưu thông tin vào cơ sở dữ liệu.

6. **Thông báo thành công**
   - Hệ thống hiển thị thông báo "Nhân viên đã được tạo thành công."

### Các yếu tố liên quan
- **Người quản trị**: Người thực hiện thao tác.
- **Hệ thống**: Giao diện quản lý nhân viên.
- **Cơ sở dữ liệu**: Nơi lưu trữ thông tin nhân viên.

---

## 3. Maintain Purchase Order

### Mô tả
Người dùng cập nhật thông tin đơn hàng mua.

### Các bước thực hiện
1. **Khởi động**
   - Người dùng truy cập trang quản lý đơn hàng.

2. **Hiển thị danh sách đơn hàng**
   - Hệ thống hiển thị danh sách các đơn hàng hiện có.

3. **Chọn đơn hàng cần cập nhật**
   - Người dùng chọn đơn hàng muốn chỉnh sửa.

4. **Hiển thị thông tin đơn hàng**
   - Hệ thống hiển thị thông tin chi tiết của đơn hàng đã chọn.

5. **Chỉnh sửa thông tin**
   - Người dùng thay đổi các thông tin cần thiết (số lượng, giá cả, trạng thái, v.v.).

6. **Xác nhận thay đổi**
   - Hệ thống hiển thị tóm tắt các thay đổi.
   - Người dùng xác nhận hoặc quay lại chỉnh sửa.

7. **Lưu thông tin**
   - Hệ thống cập nhật thông tin trong cơ sở dữ liệu.

8. **Thông báo thành công**
   - Hệ thống hiển thị thông báo "Đơn hàng đã được cập nhật thành công."

### Các yếu tố liên quan
- **Người dùng**: Người quản lý đơn hàng.
- **Hệ thống**: Giao diện quản lý đơn hàng.
- **Cơ sở dữ liệu**: Nơi lưu trữ thông tin đơn hàng.

---

## 4. Login

### Mô tả
Người dùng đăng nhập vào hệ thống.

### Các bước thực hiện
1. **Khởi động**
   - Người dùng truy cập trang đăng nhập.

2. **Hiển thị form đăng nhập**
   - Hệ thống hiển thị các trường nhập (tên đăng nhập, mật khẩu).

3. **Nhập thông tin đăng nhập**
   - Người dùng nhập tên đăng nhập và mật khẩu.

4. **Xác thực thông tin**
   - Hệ thống kiểm tra thông tin với cơ sở dữ liệu.

5. **Đăng nhập thành công**
   - Nếu thông tin đúng, chuyển đến trang chính.
   - Nếu thông tin sai, hiển thị thông báo lỗi.

6. **Thông báo trạng thái**
   - Hệ thống thông báo "Đăng nhập thành công" hoặc "Tài khoản không hợp lệ."

### Các yếu tố liên quan
- **Người dùng**: Người cần truy cập hệ thống.
- **Hệ thống**: Giao diện đăng nhập.
- **Cơ sở dữ liệu**: Nơi lưu trữ thông tin tài khoản.

---

## 5. Create Administrative Report

### Mô tả
Người quản trị tạo báo cáo hành chính.

### Các bước thực hiện
1. **Khởi động**
   - Quản trị viên truy cập trang tạo báo cáo.

2. **Chọn loại báo cáo**
   - Hệ thống hiển thị các loại báo cáo có sẵn (báo cáo doanh thu, báo cáo nhân sự, v.v.).

3. **Nhập thông tin báo cáo**
   - Quản trị viên nhập các thông tin cần thiết cho báo cáo (ngày, dữ liệu cần báo cáo).

4. **Tạo báo cáo**
   - Hệ thống xử lý và tạo báo cáo dựa trên thông tin đã nhập.

5. **Xem và lưu báo cáo**
   - Hệ thống hiển thị báo cáo đã tạo.
   - Quản trị viên có thể lưu hoặc in báo cáo.

6. **Thông báo hoàn thành**
   - Hệ thống hiển thị thông báo "Báo cáo đã được tạo thành công."

### Các yếu tố liên quan
- **Người quản trị**: Người tạo báo cáo.
- **Hệ thống**: Giao diện tạo báo cáo.
- **Cơ sở dữ liệu**: Nơi truy xuất thông tin báo cáo.

---

## 6. Maintain Employee Info

### Mô tả
Quản trị viên cập nhật thông tin của nhân viên.

### Các bước thực hiện
1. **Khởi động**
   - Quản trị viên truy cập trang quản lý nhân viên.

2. **Hiển thị danh sách nhân viên**
   - Hệ thống hiển thị danh sách nhân viên hiện có.

3. **Chọn nhân viên cần cập nhật**
   - Quản trị viên chọn nhân viên muốn chỉnh sửa.

4. **Hiển thị thông tin nhân viên**
   - Hệ thống hiển thị thông tin chi tiết của nhân viên đã chọn.

5. **Chỉnh sửa thông tin**
   - Quản trị viên thay đổi thông tin cần thiết (địa chỉ, số điện thoại, vị trí công việc, v.v.).

6. **Xác nhận thay đổi**
   - Hệ thống hiển thị tóm tắt các thay đổi.
   - Quản trị viên xác nhận hoặc quay lại chỉnh sửa.

7. **Lưu thông tin**
   - Hệ thống cập nhật thông tin trong cơ sở dữ liệu.

8. **Thông báo thành công**
   - Hệ thống hiển thị thông báo "Thông tin nhân viên đã được cập nhật thành công."

### Các yếu tố liên quan
- **Người quản trị**: Người thực hiện thao tác.
- **Hệ thống**: Giao diện quản lý nhân viên.
- **Cơ sở dữ liệu**: Nơi lưu trữ thông tin nhân viên.

---

## 7. Run Payroll

### Mô tả
Quản trị viên thực hiện quy trình thanh toán lương cho nhân viên.

### Các bước thực hiện
1. **Khởi động**
   - Quản trị viên truy cập trang thanh toán lương.

2. **Hiển thị danh sách nhân viên**
   - Hệ thống hiển thị danh sách nhân viên có lương cần thanh toán.

3. **Xác nhận thông tin lương**
   - Quản trị viên kiểm tra và xác nhận thông tin lương của nhân viên.

4. **Chọn kỳ thanh toán**
   - Quản trị viên chọn kỳ thanh toán (hàng tháng, hàng quý).

5. **Chạy quy trình thanh toán**
   - Hệ thống tính toán tổng lương dựa trên thông tin
