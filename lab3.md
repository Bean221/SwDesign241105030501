# Lab3 Subsystem context diagrams
## Phần 1 Subsystem context diagrams
---
### Hệ Thống con BankSystem
![BankSystem](https://www.planttext.com/api/plantuml/png/h9B1JiCm38RlUGehfqsY4xjEKJN1QJSahboyr8EeRL8bBg9YUp8EF1AlGD9g9OKhESIE_tosO-NhutCV63ttRID4Xxh6Pm9vXxP-709JA-5T01ZBv4-e2Gu_qgYaLL7dWk4LFk2WNqZNi8EhUvDObw0OJEPWJywtoCRPTUGl8cwwmH0WownKw8zXyZllteQo_EzgCwqKMJOSIomwoKWHiHdohcdkdULaoKTQJuUvGzzRwAPxgtL2_q95KIu6kGDvkzbidsnbF6c-FZ70s660LuDIv80w5qKshuMMacUZ6JDBCKUI_FjzOa-sIZ_W6m00__y30000)
- **Ngữ cảnh**:  
  Hệ thống **BankSystem** được tích hợp để hỗ trợ các tác vụ tài chính, đặc biệt là xử lý các giao dịch thanh toán lương và xác minh tài khoản. **PayrollController** (bộ điều khiển xử lý lương) là lớp điều khiển chính tương tác với `IBankSystem` để thực hiện các giao dịch trực tiếp. Khi nhận được yêu cầu từ **PayrollController**, **BankSystem** sẽ thực hiện việc nạp tiền từ phiếu lương vào tài khoản ngân hàng của người nhận.

- **Mối quan hệ**:
  - **PayrollController** gọi phương thức `deposit` trên `IBankSystem` để thực hiện giao dịch nạp tiền.
  - **IBankSystem** là interface giúp chuẩn hóa các thao tác tài chính và kết nối lớp điều khiển với hệ thống con.
  - **Paycheck** và **BankInformation** là các thực thể liên quan chứa thông tin về phiếu lương và tài khoản ngân hàng.
 
- **Kết quả**:  
  Nhờ có **BankSystem**, các yêu cầu về thanh toán lương được thực hiện chính xác và đảm bảo an toàn cho các giao dịch tài chính.
  
---

### Hệ Thống Con PrintService
![PrintService](https://www.planttext.com/api/plantuml/png/h56zJiGm3Dxp55QcEucUO3r5rKcmi25OMK8mLKIR5CSvSGAUZ857uXLmMbfTZvKCbktFt-UVV7z-xH9RujorIlNMFTi6GT-G3to7jFSEDRmf08cHdgn3k3u61woylYIleiiT1bxPoOCjJEuPvEH3Cx2H1FZrrgBmeSIurgO42tLZKdv8XyJOIOVuUgZh_-yuCuqHwrcQBAT1Kb8-9cwnZyINCJ35jXLLOzmOpACr690iurYwMXVo7rfLrIUNt88-tsmkxWFXIyR4QTnG5e2zjrejgyrxLIrkTO8N_QEJ3D9QpPa2Jxkf7OR7yly_0000__y30000)
- **Ngữ cảnh**:  
  Hệ thống **PrintService** được sử dụng để xử lý các yêu cầu in tài liệu và báo cáo. Khi **ReportController** (bộ điều khiển báo cáo) muốn in một tài liệu, nó sẽ gửi yêu cầu đến `IPrintService`. Hệ thống này sẽ đảm bảo rằng tài liệu được gửi đến đúng máy in và thực hiện in chính xác theo yêu cầu.

- **Mối quan hệ**:
  - **ReportController** gọi phương thức `printDocument` trên `IPrintService` để in tài liệu.
  - **IPrintService** là interface giúp chuẩn hóa quy trình in ấn và làm trung gian giữa lớp điều khiển và hệ thống in.
  - **Document** và **Printer** là các thực thể liên quan, đại diện cho tài liệu cần in và máy in sẽ sử dụng.

- **Kết quả**:  
  **PrintService** giúp giảm thiểu các lỗi trong quá trình in và đảm bảo rằng báo cáo được in chính xác, đúng thời gian và trên đúng máy in.

---
### Hệ Thống con ProjectMângementDatabase

![ProjectManagementDatabase](https://www.planttext.com/api/plantuml/png/l591Ri8m4Bpx5IkVG6eGlQ8eGcelFI3n02wBsIAtYOsy3WArVLaFVLA_qBK9e8ecn_fWUJqpk-D9lZ-_vXmnnBQfbTgXUSKjWLu6_q8cBj19sP2BZnXnZKmQtXI0TP72Cng2frvc9gQ5nX1pnqle2Bi2Pj2Txg1bwxOFtZcfh7S2dHjTByVIyKF9PcfaXlxHPSdjceySgO5Ty8TZLVsR7HakLcoKcHVeLgj4-4icK0o-hYb80tCgBgwR_CIEEHedyQsiAAgXpp43FPrCxbVk501nIYORtWW5zXQr6f2NxqNHd_YGClcw9fnDwBFz3FwHZfgJswHVyWS00F__0m00)
- **Ngữ cảnh**:  
  Hệ thống **ProjectManagementDatabase** quản lý thông tin dự án và cho phép truy cập vào dữ liệu dự án. Khi **ProjectController** (bộ điều khiển dự án) muốn xem hoặc cập nhật thông tin dự án, nó sẽ truy cập dữ liệu qua `IProjectManagementDatabase`. Hệ thống này đóng vai trò lưu trữ thông tin về tiến độ và trạng thái dự án, hỗ trợ quản lý dự án hiệu quả.

- **Mối quan hệ**:
  - **ProjectController** gọi phương thức `accessProjectData` trên `IProjectManagementDatabase` để truy cập dữ liệu dự án.
  - **IProjectManagementDatabase** là interface giúp chuẩn hóa các thao tác truy xuất dữ liệu dự án và là trung gian giữa lớp điều khiển và cơ sở dữ liệu.
  - **Project** và **DatabaseConnection** là các thực thể liên quan, đại diện cho dự án và kết nối cơ sở dữ liệu được sử dụng để truy cập thông tin.

- **Kết quả**:  
  **ProjectManagementDatabase** giúp đảm bảo rằng dữ liệu dự án được lưu trữ và truy cập một cách nhất quán và bảo mật, hỗ trợ quản lý dự án hiệu quả hơn.

---
# Mô tả Hệ Thống Con và Interface

## 1. BankSystem

- **Mô tả hệ thống con**:  
  Hệ thống **BankSystem** chịu trách nhiệm quản lý các giao dịch tài chính như thanh toán và nạp tiền vào tài khoản. Hệ thống này chủ yếu hỗ trợ xử lý phiếu lương và xác minh tài khoản. Đây là một phần quan trọng để đảm bảo các khoản thanh toán đến đúng tài khoản ngân hàng của người nhận.

- **Interface của hệ thống con (`IBankSystem`)**:  
  Interface `IBankSystem` cung cấp phương thức `deposit(aPaycheck : Paycheck, intoBank : BankInformation)` để thực hiện việc nạp tiền vào tài khoản ngân hàng. Phương thức này nhận hai tham số:
  - `aPaycheck`: Đối tượng đại diện cho phiếu lương cần được nạp vào tài khoản.
  - `intoBank`: Đối tượng chứa thông tin tài khoản ngân hàng mà tiền sẽ được chuyển vào.
  
  Interface này đảm bảo rằng các thao tác liên quan đến giao dịch tài chính đều được thực hiện qua một cổng giao tiếp duy nhất, giúp quản lý và bảo mật các giao dịch một cách dễ dàng.

---

## 2. PrintService

- **Mô tả hệ thống con**:  
  Hệ thống **PrintService** chịu trách nhiệm quản lý việc in ấn, bao gồm in các tài liệu và tạo báo cáo. Hệ thống này thường được sử dụng bởi các bộ phận khác để in báo cáo hoặc tài liệu cần thiết cho các quy trình nghiệp vụ. **PrintService** đảm bảo rằng các tài liệu được in đúng cách và trên đúng thiết bị in.

- **Interface của hệ thống con (`IPrintService`)**:  
  Interface `IPrintService` cung cấp phương thức `printDocument(aDocument : Document, usingPrinter : Printer)` để thực hiện in tài liệu. Phương thức này nhận hai tham số:
  - `aDocument`: Đối tượng đại diện cho tài liệu cần in.
  - `usingPrinter`: Đối tượng chứa thông tin về máy in sẽ được sử dụng để in tài liệu.
  
  Interface này đóng vai trò là cổng giao tiếp cho các yêu cầu in ấn, đảm bảo các tài liệu được xử lý và gửi đến máy in một cách thống nhất, tránh xung đột và giảm thiểu lỗi in ấn.

---

## 3. ProjectManagementDatabase

- **Mô tả hệ thống con**:  
  Hệ thống **ProjectManagementDatabase** chịu trách nhiệm lưu trữ và quản lý dữ liệu liên quan đến các dự án, bao gồm thông tin về tiến độ, tài nguyên, và trạng thái của các dự án. Hệ thống này giúp các quản lý dự án và thành viên trong nhóm có thể truy cập và cập nhật dữ liệu dự án một cách dễ dàng và chính xác.

- **Interface của hệ thống con (`IProjectManagementDatabase`)**:  
  Interface `IProjectManagementDatabase` cung cấp phương thức `accessProjectData(aProject : Project, usingConnection : DatabaseConnection)` để truy cập dữ liệu dự án. Phương thức này nhận hai tham số:
  - `aProject`: Đối tượng đại diện cho dự án cần truy cập dữ liệu.
  - `usingConnection`: Đối tượng đại diện cho kết nối cơ sở dữ liệu dùng để truy cập thông tin.
  
  Interface này giúp chuẩn hóa việc truy cập dữ liệu dự án, cung cấp một cổng giao tiếp thống nhất để đảm bảo dữ liệu được truy xuất và cập nhật một cách nhất quán và an toàn.

---
## Phần 2 Analysis class to design element map
---
### Ánh xạ lớp phân tích đến phần tử thiết kế
---

| Analysis Class               | Design Element               |
|------------------------------|------------------------------|
| PayrollController             | PayrollController            |
| BankSystem                    | BankSystem                   |
| IBankSystem                   | IBankSystem                  |
| Paycheck                      | Paycheck                     |
| BankInformation               | BankInformation              |
| PrintService                  | PrintService                 |
| IPrintService                 | IPrintService                |
| Document                      | Document                     |
| Printer                       | Printer                      |
| ProjectManagementDatabase     | ProjectManagementDatabase    |
| IProjectManagementDatabase    | IProjectManagementDatabase   |
| Project                       | Project                      |
| DatabaseConnection            | DatabaseConnection           |

---
## Phần 3 Design element to owning package map
---
### Ánh xạ phần tử thiết kế vào các gói

| Design Element               | "Owning" Package                           |
|------------------------------|--------------------------------------------|
| PayrollController            | Applications::Payroll                     |
| BankSystem                   | BusinessServices::FinancialTransactions   |
| IBankSystem                  | Interfaces::FinancialServices             |
| Paycheck                     | BusinessServices::PayrollArtifacts        |
| BankInformation              | DataEntities::Bank                        |
| PrintService                 | Infrastructure::Printing                  |
| IPrintService                | Interfaces::PrintingServices              |
| Document                     | DataEntities::Documents                   |
| Printer                      | Hardware::Printers                        |
| ProjectManagementDatabase    | Infrastructure::DatabaseManagement        |
| IProjectManagementDatabase   | Interfaces::ProjectDataServices           |
| Project                      | DataEntities::Projects                    |
| DatabaseConnection           | Infrastructure::DatabaseConnections       |

---

## Phần 4 Architectural layers and their dependencies
--- Mô Tả các Layers trong hệ thống 
![Layers](https://www.planttext.com/api/plantuml/png/Z5CxKW914Ctd52q96X2esGOMe1G9MWXuW7Pebv5bTcjcbf9IOWCJSoD38m-mWO5SX1Du1MS6rE5ZQMVxfllrUwzwFugtgZQeJ3vAs4wVheGaw3IEUxMpPgi1F46j6Il3x75UFCW1o7WmUq7WxyyS4foGOXdo8SO4fPRxXFq8QbcM28v6f18yM89R1hOy6zHH3hiJRMYqX7rXRWOaZPkZ2qrgT-_dBLCf9wrx2gL6xdYNhzE0jgs4D5rIOy4f9CuStY5E8ZCXQKoIb5tMeInLvfjmojOT7KHGpxNDnIvffR7Wsqm5sjeBjQaALOmn4NsxRTD3wB2Dav4DOOkxXShcGlCgDLUqRiCNtJZaJtk74PoWGQXnxXrkUhE6hecRKvHspEbp_PUeLsBcgPIsAHIWo2X1OtBj8Qvn1VEYod2UeuJ1lBY7MCoBrwyRcnTF6GjEfbAvEzgUTWIv9irMxi1thsUtRDnAuWT-Dnm1-fZi-3hh_oTPbMJV_M-V0000__y30000)

# Biểu đồ mô tả các layers trong hệ thống

Hệ thống bao gồm ba package chính:

## 1. Application Layer
- **BankSystem**: Chứa các chức năng quản lý giao dịch ngân hàng.
  - Các phương thức chính: `authenticateUser()`, `processTransaction()`.
- **PrintService**: Cung cấp dịch vụ in ấn biên nhận và báo cáo.
  - Các phương thức chính: `printReceipt()`, `generateReport()`.

## 2. Business Logic Layer
- **TransactionProcessor**: Xử lý các giao dịch, bao gồm xác thực và xử lý thanh toán.
  - Các phương thức chính: `validateTransaction()`, `processPayment()`.
- **ReportGenerator**: Tạo và xuất báo cáo.
  - Các phương thức chính: `createReport()`, `exportReport()`.

## 3. Data Access Layer
- **ProjectManagementDatabase**: Quản lý truy cập dữ liệu cho hệ thống, bao gồm kết nối, truy xuất và lưu trữ dữ liệu.
  - Các phương thức chính: `connect()`, `retrieveData()`, `saveData()`.

## Mối quan hệ giữa các lớp
- **BankSystem** sử dụng **TransactionProcessor** để xử lý các giao dịch ngân hàng.
- **PrintService** sử dụng **ReportGenerator** để in báo cáo.
- **TransactionProcessor** và **ReportGenerator** truy xuất và lưu trữ dữ liệu từ **ProjectManagementDatabase**.

