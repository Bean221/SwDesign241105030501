# Lab 4 Payroll System - Use Case Descriptions
---
## Thiết kế các ca sử dụng trong lab 2 và lab 3
---
file 1
---
## **1. Use Case: Login**
![](https://www.planttext.com/api/plantuml/png/X95D2i8m48NtESNGVI_WGYgrYwvBtSgGZbXeKybCXPxDXKVo2fhq5mowoxptFfWtUJsU2GjQwTj6ePREGibafsTqwELAHcgDKdS6Ye65sWYGmJdZg5JFf949eim8MKWjLGx2XdsqJC_UsEWhSiAchb0eHCrU43pMV6jmWABNcdXXfl4xbrdRsMKVDoZbga8SxuCh1hGv6reiB7jYlHNiO7DI-WMjNJvGVW6V-mFuMcCyDtSF96GgzxTl0000__y30000)

### Mô tả
Chức năng `Login` cho phép người dùng xác thực thông tin đăng nhập để truy cập hệ thống. Quy trình bao gồm việc nhập thông tin, xác thực thông qua hệ thống xác thực và phản hồi kết quả.

### Các thành phần chính
- **Actors**:
  - **User**: Người dùng muốn truy cập hệ thống.
  - **Authentication System**: Hệ thống xác thực thông tin đăng nhập.

- **Use Cases**:
  1. **Enter Credentials**: Người dùng nhập tên đăng nhập và mật khẩu.
  2. **Validate Credentials**: Hệ thống xác thực thông tin đăng nhập qua `Authentication System`.
  3. **Display Success**: Hiển thị thông báo thành công nếu thông tin hợp lệ.
  4. **Display Error**: Hiển thị lỗi nếu thông tin không hợp lệ.

### Luồng hoạt động
1. Người dùng nhập thông tin đăng nhập vào hệ thống.  
2. Hệ thống xác thực thông tin bằng cách gửi yêu cầu tới `Authentication System`.  
3. Nếu thông tin hợp lệ, hệ thống hiển thị thông báo thành công.  
4. Nếu thông tin không hợp lệ, hệ thống thông báo lỗi và yêu cầu nhập lại.


---
## **2. Use Case: Maintain Timecard**
![](https://www.planttext.com/api/plantuml/png/TD9DJiCm40NWlKynoZuNO86A88Yk-xD5etW0gubJsTEYd8q5H-8AnDFORjrs5StpbzZFoj_Fxy8pEZxqdSAM1mTDl--6aMWUgxNfQKUqD_OJLgDdwYj03o4-ZKeTFBNe2QgjeMzPQT5fBsxp_1xIR9wq5WADPJT6CwKoPzTempTWY0kvnSvev0B6jC0hF1Om90LwGwkxYJatkBHn69IArmDr_PZApK_9yiN00xmIjr_mWenNBwR6vK9kUARITXUjplLTSH54bKfFXrn-W9YxMAgVuD8U8ysVkAejbooj5sHr-BV-0G00__y30000)

### Mô tả
Chức năng `Maintain Timecard` cho phép nhân viên quản lý phiếu chấm công, bao gồm việc xem, thêm, chỉnh sửa và lưu dữ liệu chấm công.

### Các thành phần chính
- **Actors**:
  - **Employee**: Nhân viên quản lý thông tin chấm công.
  - **Timekeeping System**: Hệ thống ghi nhận dữ liệu chấm công.

- **Use Cases**:
  1. **View Timecards**: Nhân viên xem danh sách phiếu chấm công.  
  2. **Add Time Entry**: Nhân viên thêm thông tin chấm công mới.  
  3. **Edit Time Entry**: Nhân viên chỉnh sửa thông tin chấm công đã có.  
  4. **Validate Entry**: Xác thực dữ liệu chấm công mới hoặc chỉnh sửa.  
  5. **Save Entry**: Lưu thông tin chấm công vào hệ thống nếu dữ liệu hợp lệ.  
  6. **Handle Error**: Xử lý lỗi nếu dữ liệu không hợp lệ.

### Luồng hoạt động
1. Nhân viên yêu cầu xem danh sách phiếu chấm công và hệ thống hiển thị dữ liệu từ `Timekeeping System`.  
2. Nhân viên thêm hoặc chỉnh sửa thông tin chấm công.  
3. Hệ thống xác thực thông tin: nếu dữ liệu hợp lệ, thông tin sẽ được lưu; nếu không hợp lệ, hệ thống thông báo lỗi.  
4. Dữ liệu hợp lệ được lưu trữ vào hệ thống `Timekeeping System`. 

---
## **3. Use Case: Run Payroll**

![](https://www.planttext.com/api/plantuml/png/T99DJWCn38NtEOKr-rvW5gZGKkWEGUaMcOaB4PaCSfAYdeq5H-8ApEIdQGhixESlbjzJlZ-_vjOXEzzhWPqR62vbhqogcpiyyA0rF1oiexu1j92ag6Jk2isRCY-dN98I9xob3Yr1ioBNlS96zMFFqWRsSV4Kv49jKIk9Zc293ZEJnKahw09rv_N4fjCoVXmKzeOCyOJUq_l0BfEnAzXIMSVgsV_UMIQ5laKZDS4ryy2P2uqG8KoOpIwAnLm4jGeJsl6iSJlje-qQFVT_rcUcfD72UWS1-OyDHqPkRVQPB1iIbj8vLa6FpbhOAlf8QTPkJvAgkZ2lFiUuPSDex8uOLjv8-yU3-jg2ez9MpCd8wGF_0000__y30000)

### Mô tả
Chức năng `Run Payroll` thực hiện quy trình trả lương cho nhân viên, bao gồm tính toán bảng lương, tạo báo cáo và phân phối tiền lương qua hệ thống ngân hàng.

### Các thành phần chính
- **Actors**:
  - **Admin**: Người quản lý khởi chạy và kiểm tra quá trình trả lương.  
  - **Payroll System**: Hệ thống xử lý dữ liệu lương.  
  - **Banking System**: Hệ thống ngân hàng chịu trách nhiệm chuyển khoản lương.  

- **Use Cases**:
  1. **Fetch Timecards**: Lấy thông tin chấm công từ hệ thống.  
  2. **Validate Data**: Xác thực dữ liệu chấm công để đảm bảo tính hợp lệ.  
  3. **Calculate Payroll**: Tính toán tiền lương dựa trên dữ liệu chấm công và thông tin nhân viên.  
  4. **Generate Report**: Tạo báo cáo bảng lương để Admin kiểm tra.  
  5. **Distribute Payroll**: Phân phối lương qua `Banking System`.  
  6. **Handle Error**: Xử lý lỗi nếu phát sinh trong quá trình trả lương.  

### Luồng hoạt động
1. Admin khởi động quy trình trả lương bằng cách yêu cầu hệ thống lấy dữ liệu chấm công.  
2. Hệ thống xác thực dữ liệu chấm công để đảm bảo không có lỗi.  
3. Tiến hành tính toán bảng lương dựa trên dữ liệu hợp lệ.  
4. Hệ thống tạo báo cáo và gửi đến Admin để kiểm tra.  
5. Sau khi xác nhận, hệ thống thực hiện phân phối lương qua `Banking System`.  
6. Nếu xảy ra lỗi trong quá trình chuyển khoản, hệ thống ghi lại lỗi và thông báo cho Admin.

---
## **1. Login - Use Case Realization**

![](https://www.planttext.com/api/plantuml/png/R94zRiCm38LtdOB8tWjqA88OAL2WGz4WtGcQIGNhnw3emMVhq2Fr2fKK98xWJ1B9xr7lGNy_lzkaA3fvPv0q2XmJYnbpov8TCIXitkFPXjSeVWEOu5Qrq0VE4fthOj1oibHurMr5Up-wE3DNzbgqo65EohvpaOQte2mdf0jUMosxmp1S-4eifJ4b5JozBExX6VPb7v1mpq4jkcIMQKPNthFa2vtjKRbHhS6ilgR9ekwRQO2fEB3X5CrjbB57yRBaaobA3wxu0RMU7pzodwRU8Kr4d9BPSkZBd_u3003__mC0)

### Mô tả
Quy trình hiện thực hóa cho trường hợp sử dụng `Login` thể hiện cách các thành phần trong hệ thống phối hợp để xử lý yêu cầu đăng nhập của người dùng.

### Các thành phần chính
- **Actors**:
  - **User**: Người dùng thực hiện đăng nhập.
- **Participants**:
  - **LoginForm**: Biểu mẫu nơi người dùng nhập thông tin đăng nhập.
  - **PayrollController**: Bộ điều khiển chịu trách nhiệm xác thực và xử lý logic liên quan.
  - **Employee**: Thành phần đại diện thông tin người dùng trong hệ thống.
  - **SystemClockInterface**: Ghi nhận thời gian đăng nhập.
  - **BankSystem**: Mặc dù không trực tiếp liên quan, có thể được tham chiếu trong quy trình bảo mật đăng nhập.

### Luồng hoạt động
1. Người dùng nhập thông tin đăng nhập vào `LoginForm`.  
2. `LoginForm` chuyển thông tin đến `PayrollController` để xác thực.  
3. `PayrollController` truy vấn thông tin từ đối tượng `Employee` để kiểm tra dữ liệu.  
4. Nếu thông tin hợp lệ, `SystemClockInterface` ghi lại thời gian đăng nhập của người dùng.  
5. Kết quả được trả về cho `LoginForm` để thông báo đăng nhập thành công.

---
## **2. Maintain Timecard - Use Case Realization**

![](https://www.planttext.com/api/plantuml/png/T94zhW8n38JxdCAYH_GK2CHFXq3YYTua5WJbP-MOXpWR1KVY2cHNInOGb3FpsHx9z-jjd0HPJjufr18PvhvoyKAagcnRRIiC0hq_wqaZcqLatmDCK1kr-8vDOn2EpX4NkBE-ZnIm5k_8ckEHj2mnu9uy1PcXu0uJDJFhvLCgzImF_L5f24DOLHJARcXgbxGbktgPdnWpc1ih83c1V90lwWDgnvg5GzYYimRbbMsIJ7NrChV1Vu8CuezrRT_D8PuXdRIcb23_X9WZgp45K__f0G00__y30000)

### Mô tả
Quy trình hiện thực hóa cho trường hợp sử dụng `Maintain Timecard` mô tả cách nhân viên thêm hoặc chỉnh sửa dữ liệu chấm công thông qua hệ thống.

### Các thành phần chính
- **Actors**:
  - **Employee**: Nhân viên quản lý thông tin chấm công của mình.
- **Participants**:
  - **TimecardForm**: Biểu mẫu cho phép nhân viên nhập và chỉnh sửa thông tin chấm công.
  - **TimecardController**: Bộ điều khiển quản lý logic thêm/sửa thông tin.
  - **Timecard**: Thành phần chứa dữ liệu chấm công cụ thể.
  - **ProjectManagementDatabase**: Cơ sở dữ liệu lưu trữ dữ liệu chấm công.

### Luồng hoạt động
1. Nhân viên mở `TimecardForm` để truy cập biểu mẫu chấm công.  
2. `TimecardForm` gửi yêu cầu thêm hoặc chỉnh sửa dữ liệu tới `TimecardController`.  
3. `TimecardController` xác thực thông tin thông qua đối tượng `Timecard`.  
4. Nếu dữ liệu hợp lệ, `Timecard` lưu trữ thông tin vào `ProjectManagementDatabase`.  
5. Hệ thống phản hồi kết quả (thành công hoặc lỗi) cho nhân viên qua `TimecardForm`.

---
## **3. Run Payroll - Use Case Realization**
![](https://www.planttext.com/api/plantuml/png/T99DRWCX38NtdCBAlXV8eaeQgLLtLPCBM8oZGG63Z2VIdAsB7gbNACmqoW_J3SZF_lomnS_NzoOhYWx16xGQ1RPTS6nIqPnr2LbXzO6ZHEztaRNU92l038rw3nrS88lIFL2jt7ZPdkpfOZ45zoKloAVzc9N2L7GD7pg9OoLvhySHBSqTPz6OQKnuUcx7W3Ly3WnfrasRBr0xHQ5UIMqF-fU23XNDGk4DNgr8nT6PW4BoSII2FWwIbsql-oZS3hqTF2hLXmPYNIQkoodCGP3piIGoUYok_xdCEoh06p59zH1AKJIR3N5Nlyel0000__y30000)

### Mô tả
Quy trình hiện thực hóa cho trường hợp sử dụng `Run Payroll` thể hiện cách hệ thống xử lý bảng lương từ việc lấy dữ liệu chấm công đến tính toán lương và phân phối qua ngân hàng.

### Các thành phần chính
- **Actors**:
  - **Admin**: Người khởi chạy và giám sát quá trình xử lý bảng lương.
- **Participants**:
  - **PayrollController**: Thành phần điều khiển chính cho quy trình trả lương.
  - **TimecardController**: Thành phần phụ trách quản lý và cung cấp dữ liệu chấm công.
  - **Paycheck**: Thành phần xử lý và lưu trữ thông tin thanh toán.
  - **BankSystem**: Hệ thống ngân hàng thực hiện chuyển khoản lương.
  - **PrinterInterface**: Tạo và in báo cáo bảng lương.

### Luồng hoạt động
1. Admin yêu cầu `PayrollController` chạy quy trình trả lương.  
2. `PayrollController` gửi yêu cầu đến `TimecardController` để lấy dữ liệu chấm công của nhân viên từ `Timecard`.  
3. `PayrollController` sử dụng dữ liệu để tính toán số tiền lương qua đối tượng `Paycheck`.  
4. Sau khi tính toán, lương được chuyển tới tài khoản nhân viên thông qua `BankSystem`.  
5. `PayrollController` sử dụng `PrinterInterface` để tạo báo cáo bảng lương và cung cấp cho Admin.

---
## file 2   
---
## **1. Subsystem Context Diagram - BankSystem Subsystem**
![](https://www.planttext.com/api/plantuml/png/P99BJiGm38RtEONL5In6xBj00sY4a10Q3Lp0IjqIsYR5SP4YnCbOS2IkGDBNj68LFpuxlvtyVl_ilI1BtpOAjJY6cw8rTh8FRTUuG3IvsItQ6fw35sepG0_97rsbEjGrLWJP4GExfbcuJmMWNTivIrQMz9spaaxYeTCK_OVgLzBrJ0pE5ZamEtvqLHNxg2-b1lMmkvuRGWuFreX18UYcKCTEa_TgHaPwQ1xnUxB44px41d3CHl8yScHV6AqlYS5ZWsp8grLw8oAEMnfkhqxqHbf0Kc5Sgd5sBMCrJQo91b2AUBWm9Q0Dbsju73M79oUc312VKNglrFnciDi8ED5xJrv6fG4A4ZJDQWVfzhaoXoEx3rESTx3mUx95-Yj_0000__y30000)


### Mô tả
Sơ đồ này mô tả cách hệ thống `Payroll System` tương tác với `Bank System` để xử lý trả lương. `Bank System` chịu trách nhiệm xác thực và xử lý các giao dịch chuyển khoản tiền lương cho nhân viên.

### Thành phần chính
- **Admin**: Người quản trị khởi tạo quá trình trả lương.  
- **Bank System**: Hệ thống ngân hàng xử lý chuyển khoản.  
- **Employee**: Người nhận tiền lương.  

### Luồng hoạt động
1. Quản trị viên khởi động quy trình trả lương.  
2. Hệ thống tạo các bảng lương và gửi yêu cầu thanh toán đến `Bank System`.  
3. `Bank System` xử lý giao dịch và phản hồi trạng thái (thành công hoặc thất bại).  
4. Trong trường hợp lỗi, hệ thống ghi lại thông tin lỗi và thông báo cho Admin.  

---
## **2. Subsystem Context Diagram - PrintService Subsystem**

![](https://www.planttext.com/api/plantuml/png/T99DJiGm38NtFeNL_LnW5cZG225sY9uWIjrHHFD3ugAf42TZmP6u0awJL1J1fccSBo_lEVdw-3mbLf5dEu7Ix2FU3jQu-dzdm-GNeZhj7gDnJ14VydTKcZfK2MiL82Zzh2uad5gYdoRibyHaEtm3HErjy8uSRyjdxpYF58jCgUxH9me-yZqvYaeih62f_PBC7dgAhqPCmJl06WCFDqqMZrXL24CjnIBK286BjB1daJOJuK2iP1mgcw0IMVZ7aRAZ9zSe7ALP8IyRTu4Tr_P94uzosijCYGkAT2Kzi_4E6d4GkkJ8XjneejraKQwDvmJGxcYVjKcpkcOtDlsPSkj8m_wFjqubtoeh_LZfasJEB-SR003__mC0)

### Mô tả
Sơ đồ này thể hiện quy trình tạo báo cáo bảng lương và in biểu mẫu thuế qua `PrintService`.

### Thành phần chính
- **Admin**: Yêu cầu tạo và in báo cáo bảng lương.  
- **Printer Interface**: Thực hiện quá trình in từ hệ thống.  
- **Employee**: Yêu cầu in biểu mẫu thuế cá nhân.  

### Luồng hoạt động
1. Admin yêu cầu hệ thống tạo báo cáo bảng lương.  
2. Báo cáo được gửi đến `Printer Interface` để in.  
3. Kết quả in được xác nhận và phản hồi lại cho Admin.  
4. Nhân viên cũng có thể yêu cầu in biểu mẫu thuế thông qua hệ thống.  


---
## **3. Subsystem Context Diagram - ProjectManagementDatabase Subsystem**

![](https://www.planttext.com/api/plantuml/png/R58xRiCm3Drr2i9xBf2XAD3F5Y1eYkwCp2QgzN4fEe5Hz6GTUgHUeLHWv-kH3-z7Idy_l_TPaAKBtg2LnF0KMfzwec5SOCGDyJ1LIquVP6M00qM1HnHSOwOACCDoCOx6j6WR9K7rwW8rHAsB6rZrMIXKy6K0R0fjYiNZGB78zKEAmibxueDTWK_GjEH8BCCbvGszgr5SYYlYdRDKcMzZnWrXTdSL07DOTUlW14HnK0_kpHL5HJUsgXimWctgECC-SKErkMNEfa9FD63AdPU9qDDbIqlS4Uo6oFgyxHbDHSTLvw1kxuu3v2BDdRMKip73yqwUueK-Eye2UwB6zwe90IVlSL7jcSHk3utAUu0Mn8jIoXz3TG-AzMYigxU9nTmhLhxZFm000F__0m00)

### Mô tả
Sơ đồ này trình bày cách lưu trữ thông tin chấm công vào hệ thống `Project Management Database` thông qua `Timekeeping System`.

### Thành phần chính
- **Employee**: Nộp phiếu chấm công.  
- **Manager**: Yêu cầu báo cáo thời gian làm việc.  
- **Project Management Database**: Lưu trữ dữ liệu chấm công.  

### Luồng hoạt động
1. Nhân viên nộp thông tin chấm công qua hệ thống.  
2. Dữ liệu được xác minh bởi dịch vụ xác thực (`ValidationService`).  
3. Thông tin hợp lệ được lưu trữ vào cơ sở dữ liệu `Project Management Database`.  
4. Quản lý có thể yêu cầu báo cáo tổng hợp từ hệ thống.  


---
## **4. Analysis-Class-to-Design-Element Map**

![](https://www.planttext.com/api/plantuml/png/T99DJeH048NtdA8pArtC1MPX9fenBap6YD5rsHHCXwQRL3Kan7Wo5nx9ArZqmC3yiI4yNdtr-i7Vp--Q0r1eAfje2yngKzNMTuZgAr5ocMobqa365V7HGOL70dax2T_907c1JbxO1-z2VqSQQ1giRYm470mtjr7E30lWipdL2tH8udx5sbDWKGyRtao56YYx77Fd6-8FJoMARbo8OWlMP4BhH-UeUt1bsd70Qe050iSvqcFZCXwYE1zCtcs8F1tbUDz3ZNSfKclqsDkuxAbFCZ3q3dMvRP4ir7D6f3xxeZZqP7qHnRthlCtbSlfEAxMeoMjaHbvSzDvDROavno11M4awkEQVLI8JOn-i62oGkRvdVX8Pb6EmmjZP8ZblwZJPs9dC23MkMQFB-d_p7m00__y30000)

### Mô tả
Sơ đồ này cho thấy mối quan hệ giữa các lớp phân tích và các phần tử thiết kế trong hệ thống `Payroll System`.  

### Thành phần chính
1. **Employee**: Lưu trữ thông tin cơ bản của nhân viên như tên, mã số và vai trò.  
2. **PayrollController**: Quản lý các quy trình liên quan đến bảng lương như tính toán, phân phối, và tạo báo cáo.  
3. **Timecard**: Ghi nhận giờ làm việc của nhân viên.  
4. **BankSystem**: Thực hiện chuyển khoản tiền lương và thông báo lỗi nếu xảy ra.  
5. **ValidationService**: Xác thực dữ liệu như giờ làm việc hoặc bảng lương để đảm bảo tính chính xác.  


---
## **5. Design-Element-to-Owning-Package Map**

![](https://www.planttext.com/api/plantuml/png/T951Zi8m34NtEOMLFHUO1KACPZ7IB910xAtK2b7J1Daf225EncAEn1Me1wPKAjt-_-p_dToklmifoALjejcZgz4Js4reg2RQX-HXzH0jd0s0YoW2QZlaQYHyvbGunqZSMrkCeS8ISbeJ7u8ZSp6le1MUb7yNyhJUhEmSjoDNzy8NS-QVx7q73RSlCTNmdGfv_cimNA_U-YI56XqPXS5iDk_FWW-mhP3O2Uw_a7AU4dLfq_2WhF8nUu4WqavFlAhgG7ZUGmB7K7RMZ5vurFtm83HXGQdIhxu3003__mC0)

### Mô tả
Bản đồ này liên kết các phần tử thiết kế trong hệ thống với các gói (packages) mà chúng thuộc về.  

### Thành phần chính
- **Package Timekeeping**: Chứa các phần tử liên quan đến quản lý thời gian làm việc, như `Timecard`, `TimecardController`.  
- **Package Payroll**: Chứa các thành phần xử lý bảng lương, bao gồm `PayrollController`, `Paycheck`.  
- **Package Bank**: Chứa các lớp liên quan đến ngân hàng như `BankSystem`.  


---
## **6. Architectural Layers and Their Dependencies**

![](https://www.planttext.com/api/plantuml/png/V5DBJiCm4Dtx52FlUm4M2Dg2X5IaY5Rif-wqDVMdZ9rA4U9aB3WILy1EIfis2Qj8dlVyFfxyV7tVXOWSIsl47jKEDmIoO0ha8aRj7Som8fRm8G2KjtllqWJap6-qU_HivUNvGbjIoAkUqHJ3TkdJJ8fFSHORbq4x2W7obMf0hi2AlJ4JxsB-9aI_x23W5OrUrO7cn0UjwDB452F2lLArZru7VmfNzpxOlV4LaUpuLLjIksiqi-UKSvFzjVMVNAGD_rVu6DrkNeL8rxKMh1EPymsyHjLnmlwDL7n6buHiEifHbnYQ0axF2AFHBNHQXXkGyt9fTGIJaP0gH2dQZrmJk_Mtc34D8GcpfY35QGk65L_elQGG8PJM8bTIY2xiIAvBpfm94qQ2W0ORdNxAkSLCMZ2wi4wZCwqdIJjW7GiFr8IwRAFnD5HtPXR4GQTW3KzqTh8ZTKIqwcjjq721QGwATTGA3L1c9EOTkLN-oty1003__mC0)

### Mô tả
Sơ đồ này phân lớp kiến trúc hệ thống và các phụ thuộc giữa các tầng.  

### Các tầng kiến trúc
1. **Presentation Layer**: Giao diện người dùng để nhân viên và quản trị viên tương tác.  
2. **Business Logic Layer**: Xử lý các quy trình nghiệp vụ chính như tính lương, xác thực, và ghi nhận giờ làm việc.  
3. **Data Access Layer**: Truy cập và thao tác dữ liệu từ cơ sở dữ liệu hoặc hệ thống bên ngoài như `BankSystem`.  

### Mối quan hệ
- **Presentation Layer** phụ thuộc vào **Business Logic Layer** để thực hiện các yêu cầu.  
- **Business Logic Layer** phụ thuộc vào **Data Access Layer** để lưu trữ hoặc truy xuất dữ liệu.  


---
## **7. Packages and Their Dependencies**

![](https://www.planttext.com/api/plantuml/png/V9FFJeD04CRlVOe9zxw01zDOQzB4DYOOx-Coq1NO9SFOf34-cGSVoLTm1zj2mUq9ydtxss_-mC_Nzw8LP7clgrc3fiI287d20_kgWlJG2jK9VCm0ZAyRxyZ9sLvw9_eaJYQ-sP4fH_AAsVEZBme5FcTztBEjgIHgh2jYaNh486VHpDE1aVo2bSrGh7SfyTuQkanUEw62Ep-MV8UkF5gZBja6clKApb5l7jd-ZOniq8MaEaZtAFYAxQY2hHURMtErX5MDjZhNVs6bctJOs6GpC9_VmdHuS0F90udPWGGFmeGmYS2dPIgoP48XQ8vI6sFwcIcrTbQiSiBesfmuoer7gdId0LFZMGBuJoz_P6JQUaMA--iz3hvCFH_UW5IA5ZhSI9T0BWCtM6MKx1SMunP1qx_n5m00__y30000)

### Mô tả
Sơ đồ này trình bày các gói chức năng trong hệ thống và cách chúng phụ thuộc lẫn nhau.

### Thành phần chính
- **Timekeeping Package**: Bao gồm các lớp liên quan đến chấm công như `Timecard`, `TimecardController`.  
- **Payroll Package**: Chứa các lớp xử lý bảng lương như `PayrollController`, `Paycheck`.  
- **Bank Package**: Bao gồm `BankSystem` để thực hiện giao dịch tiền lương.  
- **Print Package**: Quản lý các chức năng in ấn như `PrintService`, `Printer Interface`.  

### Mối quan hệ
- **Timekeeping Package** cung cấp dữ liệu cho **Payroll Package**.  
- **Payroll Package** sử dụng **Bank Package** để xử lý giao dịch lương.  
- **Payroll Package** cũng sử dụng **Print Package** để tạo và in báo cáo.  

---
