# Lab 5 thiết kế các hệ thống con trong hệ thống Payroll System
---
# Các Hệ Thống Con và Chức Năng

## 1. Payroll Processing Subsystem (Xử lý bảng lương)

**Chức năng chính:**
- Tính toán bảng lương dựa trên thông tin chấm công, lương cơ bản, tăng ca, khấu trừ.

**Các cơ chế mở rộng:**
- Giao diện đơn giản (ss interface).
- Bảo mật (Security).
- Tính toán phân tán (Distribution).
- Lưu trữ dữ liệu trong cơ sở dữ liệu hướng đối tượng (OODBMS Persistency).
- Tổng hợp tất cả các tính năng trong chế độ đầy đủ (everything).

**Các hệ thống con nhỏ:**
- **Calculation Engine**: Xử lý logic tính toán lương.
- **Security Manager**: Kiểm tra bảo mật khi xử lý.
- **Database Handler**: Lưu dữ liệu lương vào cơ sở dữ liệu.

---

## 2. Timecard Management Subsystem (Quản lý bảng chấm công)

**Chức năng chính:**
- Thu thập và quản lý thông tin chấm công của nhân viên.

**Các chế độ mở rộng tương tự Payroll Processing:**
- Giao diện cơ bản.
- Tích hợp bảo mật.
- Phân tán dữ liệu.
- Lưu trữ với cơ sở dữ liệu OODBMS.
- Tổng hợp với tất cả các tính năng.

**Các hệ thống con nhỏ:**
- **Timecard Input Handler**: Xử lý dữ liệu đầu vào từ nhân viên.
- **Validation Engine**: Kiểm tra và xác thực dữ liệu chấm công.
- **Attendance Tracker**: Theo dõi lịch trình và trạng thái làm việc.

---

## 3. Authentication Subsystem (Hệ thống xác thực)

**Chức năng chính:**
- Đăng nhập vào hệ thống Payroll.
- Hỗ trợ đăng nhập với cơ chế bảo mật nâng cao (Security).

**Các hệ thống con nhỏ:**
- **Login Handler**: Xử lý đăng nhập cơ bản.
- **Authentication Manager**: Kiểm tra thông tin tài khoản, quyền truy cập.
- **Security Module**: Xác minh các yếu tố bảo mật như mật khẩu, mã OTP.

---

## 4. Reporting Subsystem (Báo cáo)

**Chức năng chính:**
- Tạo báo cáo bảng lương, chấm công.
- Phân tích dữ liệu hiệu suất của nhân viên.
- Đưa ra thống kê về chi phí nhân sự.

**Các hệ thống con nhỏ:**
- **Report Generator**: Sinh báo cáo theo yêu cầu.
- **Data Analyzer**: Phân tích và trực quan hóa dữ liệu.
- **Export Module**: Xuất báo cáo ra các định dạng như PDF, Excel.

## Mô tả package và dependencies

Package Diagram

![](https://www.planttext.com/api/plantuml/png/b9H1JiCm44NtESKeArZq2gYWI6oeMZMzmE0CgKNYLFQaA21Ene8ZSGLCWn1sOpjTP3Fp_e_cpyXV7vzBmwYvRvliWE8PQu9yWuFkcWRAmJ2rERnb07_DRQ_W5nWx0A91OvmENDc2L4pw2GLTvq7iHV8UIXAzbZoak48QrlAnPzcf5BjU5tUh4ZQaZLMH4abtEf8UU2zLVIBVi_zJhz1EOp_OoPO4wigR_QmVIs02ZkGGeiDfX1IfJ4AwQ38FNIsLbyPOEwjCZUcQRUdGQGPK5TmgR0QMmdZUzwH88nEChFENa-QLe436qTpQn-uI5ekRn4L6ko6zjvia4VAPtDXCBkJfR3DBN-xeC-DcPp1nBp-rULpSSph1I-YulvFcabJryv9-0m00__y30000)

# Luồng Hoạt Động Giữa Các Hệ Thống Con

## 1. Employee Management System (Hệ thống Quản Lý Nhân Viên)

**Chức năng:**
- Cung cấp thông tin nhân viên, bao gồm lương cơ bản, vai trò, và thông tin tài khoản ngân hàng.

**Luồng dữ liệu:**
- Cung cấp dữ liệu về **lương cơ bản**, **vai trò**, và **thông tin tài khoản ngân hàng** cho:
  - **Payroll Processing System**: Dùng để tính toán lương.
  - **Timecard Management System**: Để quản lý thông tin nhân viên khi chấm công.

---

## 2. Timecard Management System (Hệ thống Quản Lý Bảng Chấm Công)

**Chức năng:**
- Thu thập và quản lý thông tin chấm công của nhân viên (giờ làm việc, tăng ca, vắng mặt).

**Luồng dữ liệu:**
- Cung cấp thông tin **chấm công** (giờ làm việc, tăng ca, vắng mặt) cho:
  - **Payroll Processing System**: Để tính toán lương dựa trên thời gian làm việc.

---

## 3. Payroll Processing System (Hệ thống Xử Lý Bảng Lương)

**Chức năng:**
- Tính toán bảng lương dựa trên thông tin chấm công, thông tin nhân viên và các khoản khấu trừ thuế.

**Luồng dữ liệu:**
- Nhận thông tin từ:
  - **Employee Management System**: Lương cơ bản, vai trò, tài khoản ngân hàng.
  - **Timecard Management System**: Dữ liệu chấm công.
- Tính toán bảng lương và gửi kết quả cho:
  - **Payment Management System**: Để thực hiện thanh toán lương.

---

## 4. Payment Management System (Hệ thống Quản Lý Thanh Toán)

**Chức năng:**
- Thực hiện thanh toán lương cho nhân viên và ghi nhận các giao dịch thanh toán.

**Luồng dữ liệu:**
- Nhận thông tin từ **Payroll Processing System** và thực hiện các giao dịch thanh toán.
- Ghi nhận các giao dịch thanh toán cho **Reporting System**.

---

## 5. Reporting System (Hệ thống Báo Cáo)

**Chức năng:**
- Tổng hợp dữ liệu từ Payroll Processing, Timecard Management và Payment Management để tạo báo cáo.

**Luồng dữ liệu:**
- Nhận thông tin từ:
  - **Payroll Processing System**: Dữ liệu bảng lương.
  - **Timecard Management System**: Dữ liệu về chấm công.
  - **Payment Management System**: Dữ liệu về giao dịch thanh toán.
- Tổng hợp dữ liệu từ Payroll Processing, Timecard Management, và Payment Management để tạo báo cáo.

## Sequence Diagram: Run Payroll

![](https://www.planttext.com/api/plantuml/png/T9A_IiGm7CVtFiMFxhx03STjJeNGPd7CfQ4Dj4b9quEEJWu-HH4HX4C5ftPmADnxv0by1NzfhwZrN4B-VFBz4_8vVEngounjoY9Wt6e38M6jqKK14LCi4oO4LWE9WWefoMN5b8MGob9mPj8pL0fb9uwkk4MB6Cr5NKkLpNBa3-Obrceaeh-vM5GQbog3fAsjA2SgJeA0H72rHVSDt8pF3N3NFpMGkk452kc6Ezp9NVzO0X_VLHPGf14dY5FZ-WSukE7sVtmM9sG3rsuuIcY_BUnuL3aKfzTJvq4owo99fmEhnqx17Yqmya_AczD5p-RU1h0NJjbo3MtfEIQID7V36uVSnxk0RV4LBiXbacdVwvxdGPoiIk_7JcD379PaEw5I_n6-0000__y30000)


# **Payroll System Design Documentation**

## **I. Tổng quan hệ thống**

Hệ thống **Payroll System** được chia thành nhiều **subsystem** để xử lý các chức năng như tính toán bảng lương, quản lý thời gian làm việc, thanh toán, báo cáo và phân tích. Các subsystem này được thiết kế để hoạt động độc lập và dễ dàng mở rộng trong tương lai. Mỗi subsystem có thể được tích hợp với các hệ thống khác trong công ty như **HR Management** hay **Time Management Systems**.

---
# Payroll Processing Subsystem (Xử Lý Bảng Lương)

**Chức năng chính:**
- Tính toán các thành phần lương của nhân viên như:
  - Lương cơ bản
  - Phụ cấp
  - Thuế
  - Khấu trừ bảo hiểm xã hội, bảo hiểm y tế, phúc lợi
  - Các khoản thưởng
- Quản lý các bước phê duyệt bảng lương.
- Cập nhật lịch sử lương của nhân viên.

## Các lớp chính:

### Payroll:
- **Chức năng**: Tính toán và tạo bảng lương cuối cùng.

- **Các phương thức:**
  - `calculatePayroll()`: Tính toán tổng lương của nhân viên, bao gồm tất cả các thành phần.
  - `validatePayroll()`: Kiểm tra tính hợp lệ của bảng lương trước khi phê duyệt.
  - `approvePayroll()`: Phê duyệt bảng lương sau khi đã kiểm tra và tính toán xong.

### TaxCalculator:
- **Chức năng**: Tính toán thuế thu nhập cá nhân dựa trên các quy định của pháp luật.

- **Các phương thức:**
  - `calculateTax()`: Tính thuế thu nhập cá nhân dựa trên lương và các yếu tố liên quan.

### BenefitCalculator:
- **Chức năng**: Tính các khoản phúc lợi cho nhân viên.

- **Các phương thức:**
  - `calculateBenefits()`: Tính các khoản phúc lợi như bảo hiểm xã hội, bảo hiểm y tế, và các phúc lợi khác.

### BonusCalculator:
- **Chức năng**: Tính các khoản thưởng cho nhân viên.

- **Các phương thức:**
  - `calculateBonus()`: Tính thưởng theo hiệu suất, thành tích, hoặc các yếu tố khác như ngày lễ, thành tích cá nhân.

### DeductionCalculator:
- **Chức năng**: Tính các khoản khấu trừ từ lương.

- **Các phương thức:**
  - `calculateDeductions()`: Tính các khoản khấu trừ từ lương như bảo hiểm, khoản vay, nợ lương.

### PayrollHistory:
- **Chức năng**: Lưu trữ lịch sử bảng lương của nhân viên.

- **Chức năng chính**: Lưu trữ bảng lương của nhân viên theo từng kỳ và phục vụ cho các mục đích tra cứu và báo cáo.

---

## Quy Trình Hoạt Động:

1. **Payroll** nhận dữ liệu từ **Timecard Management Subsystem** và **Employee Management System** để xác định số giờ làm việc và mức lương cơ bản của nhân viên.
2. **TaxCalculator** tính toán thuế thu nhập cá nhân và các khoản khấu trừ theo quy định của pháp luật.
3. **BenefitCalculator** tính toán các khoản bảo hiểm xã hội, bảo hiểm y tế và các phúc lợi khác cho nhân viên.
4. **BonusCalculator** tính toán các khoản thưởng cho nhân viên, dựa trên hiệu suất, thành tích, hoặc các yếu tố khác.
5. **DeductionCalculator** tính toán các khoản khấu trừ, ví dụ như bảo hiểm, khoản vay, hoặc nợ lương.
6. **Payroll** sẽ tạo bảng lương cuối cùng và phê duyệt nó nếu mọi thứ hợp lệ.
7. **PayrollHistory** lưu trữ bảng lương của nhân viên sau khi phê duyệt, tạo thành một lịch sử các bảng lương cho nhân viên.

![](https://www.planttext.com/api/plantuml/png/V9913i8W44Ntd89qfOjUe0lJg0kN9ke19XGJ4eI6WSR6U38N7iahI9Mgj5YMVzwRv4zutEubMZ3MdIHX4X1fjeNMQ2apUY7KFmQIEGcMXtmsVyKDI56DKgXhevkVy4hwjNiuhy8gRKRB_JIYbrpnex0JHY0mrhHoE2LryyXOyyenAxIQi3vCh8QM6u5UQdiBeU4XUjFVW-RvOdI7WXwGun1ArFy33WkdiMJBD3fiLT2TRuJKQb9oLNKVvGa00F__0m00)

# Timecard Management Subsystem (Quản Lý Chấm Công)

**Chức năng chính:**
- Ghi nhận thông tin giờ làm việc, giờ làm thêm, nghỉ phép, và vắng mặt của nhân viên.
- Quản lý các loại ca làm việc như ca ngày, ca đêm, ca cuối tuần.
- Cung cấp dữ liệu cho **Payroll Processing Subsystem** để tính toán bảng lương.

## Các lớp chính:

### Timecard:
- **Chức năng**: Lớp chính để quản lý tất cả các thông tin chấm công của nhân viên.

- **Các phương thức:**
  - `addEntry()`: Thêm thông tin chấm công vào hệ thống.
  - `editEntry()`: Chỉnh sửa thông tin chấm công đã nhập.

### TimecardEntry:
- **Chức năng**: Lớp quản lý thông tin chấm công cho từng ngày làm việc.

- **Các thuộc tính:**
  - `day`: Ngày làm việc.
  - `workHours`: Số giờ làm việc trong ngày.
  - `overtimeHours`: Số giờ làm thêm trong ngày.

### HolidayManager:
- **Chức năng**: Quản lý các ngày lễ và nghỉ phép.

- **Các phương thức:**
  - `checkHoliday()`: Kiểm tra nếu ngày nghỉ có phải là ngày lễ hay không.

### TimecardValidator:
- **Chức năng**: Xác minh tính hợp lệ của thông tin chấm công.

- **Các phương thức:**
  - `validateWorkHours()`: Kiểm tra tính hợp lệ của số giờ làm việc (ví dụ, không vượt quá số giờ quy định).
  - `validateOvertime()`: Kiểm tra tính hợp lệ của số giờ làm thêm (ví dụ, không vượt quá số giờ cho phép).

---

## Quy Trình Hoạt Động:

1. **Timecard** nhận dữ liệu từ các nhân viên hoặc hệ thống chấm công tự động, ghi lại thông tin về giờ làm việc, giờ làm thêm và các ngày nghỉ phép.
2. **TimecardValidator** kiểm tra tính hợp lệ của thông tin chấm công, bao gồm:
   - Kiểm tra số giờ làm việc và giờ làm thêm có hợp lệ hay không.
   - Kiểm tra ngày nghỉ có phải là ngày lễ hay không thông qua **HolidayManager**.
3. Dữ liệu hợp lệ sẽ được lưu trữ và gửi tới **Payroll Processing Subsystem** để tính toán bảng lương cho nhân viên.



![](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bToJc9niO9II6PkQd9YKOgIGZMN0X0afgIuvfKKLMfeWhcfAPabC7uj5xeci0nCPqfY9PWkpo_AziWlBIe6y_BBKejAWCeX8WWZFF9pCe4wV1Fp4jDJYs1c96Ua9cT3fR3Q69O8aYl9X-ieWmYaXiDiXJeS9kuFjHzY6f9tTNNjC3nYfU2SdrUIc9bNZA4ItRrM2g75gPZAiBWJgj8XDIy55Eu00000__y30000)


