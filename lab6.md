# Lab6 Thiết kế hệ thống payroll system
---
## Xác định các operations
---
### Timecard Management System Design
![](https://www.planttext.com/api/plantuml/png/h5JBRjim4BphAmYVvA89cgjFGPq4DT040HhqlY4t3Wi-378Ln2twPJtqa_eBfII-RCb13pLWM-3EScPdT_Ndr-zBJ-2eqwgHXj0z0KUskNVs6tAw1GDRr6Ze2WWUmIFxqR3XiqLQFuFRubsd7z5zbfvQxcIuGSAAVI4dpNQvOiUOc2sD90bAViTssVni6gx0U_OWDN9muiOwdOc4z3i5-nGB-F4SUxMVRETyWBS2zedrFNlkJrTiP4ruWGe9Hpqj7_xMLc3M6c4UNd32fI5u4xvLO29wRGqvgnIw0uywvuBIdFXatRNUARl7m9oUWay9y5_SxNO2A5Tn7NJjM-n_2yzmsFCwC1uuIMlc3A3uK19dAg_hVR04QkXAkqmTAD6ULM9fM9YgklX1L4I34FzGG7Lrz79prHDl31MTnovblTmENVLn74P4PUz7QnM2AOhcWJ7kKDiNF04ffXN3imvyHTuHvd7hZB1p8pRKdBFYbDye2wdnVTj7LrE5apbF2-Y_XlKJRLLbfajM5dtnu0xqyJsORHzDVxiV1mj-TZQpEytCEbN04-7JxwkSm1ON2sO3Tl7X_FpTucZc3XqEgCbcJH3rvcJ7QgcNQ4J_MlqB003__mC0)
### 1. **IProjectManagementDatabase (Interface)**
- **Chức năng**:
  - Kết nối với cơ sở dữ liệu quản lý dự án.
  - Lấy danh sách các mã công việc (charge numbers) dựa trên tiêu chí.
  - Khởi tạo cơ sở dữ liệu.

### 2. **TimecardForm (Lớp giao diện người dùng)**
- **Chức năng**:
  - Hiển thị thẻ chấm công.
  - Nhập giờ làm việc cho từng ngày.
  - Xóa mã công việc khỏi thẻ chấm công.
  - Lưu thông tin chấm công.
  - Duy trì (chỉnh sửa) thẻ chấm công.

### 3. **TimecardController (Lớp điều khiển)**
- **Chức năng**:
  - Lấy thẻ chấm công hiện tại của một nhân viên.
  - Lấy danh sách mã công việc từ cơ sở dữ liệu.
  - Cập nhật một mục (entry) chấm công.
  - Lưu thẻ chấm công.

### 4. **Timecard (Lớp chính cho thẻ chấm công)**
- **Chức năng**:
  - Tính tổng số giờ làm việc.
  - Lấy các mục chấm công của một ngày cụ thể.
  - Thêm một mục chấm công.
  - Lấy mã nhân viên.

### 5. **ChargeNumberList**
- **Chức năng**:
  - Quản lý danh sách các mã công việc được sử dụng trong thẻ chấm công.
  - Kiểm tra một mã công việc có trong danh sách hay không.
  - Thêm hoặc xóa mã công việc.

### 6. **Transaction**
- **Chức năng**:
  - Đại diện cho một giao dịch hoặc tác vụ có thể hoàn tác (undo).
  - Thực hiện một giao dịch.
  - Hoàn tác giao dịch.

### 7. **TimecardEntry**
- **Chức năng**:
  - Đại diện cho một mục (entry) chấm công trên thẻ, với giờ làm việc trong một ngày cụ thể và một mã công việc.
  - Kiểm tra tính hợp lệ của mục chấm công.

### 8. **Employee**
- **Chức năng**:
  - Đại diện cho thông tin nhân viên.
  - Truy xuất thông tin mã nhân viên.
## BankSystem 
![](https://www.planttext.com/api/plantuml/png/Z5HBJiCm4Dtd55PM2Mehs4QeAYMgg8GGKX5xrvbM5lvKzgHG8Kx6WYDn1UBKSJwbY2oSUEQDPzxCSxu_lsOMgS5IYeW9QYsPK_MoEbW4ITuZKZyxenbO-sIeifGXroh1zZiZ7KUQaRdM0gZoiNigU44HRXZJfSA47jyFfLo3oSWA3LVRawWje0_80IaNzcoSX_cukgmDc4Mf2fjiZ9RUtqIC2EeJ4vN7_K9eYccFJwX7WQbOhB1Q99pZCI9rC_CAb16tZWYeejsc3kXFY3uYtt5VJsZthqTxtveAgXZuMhrHloe7l2qjQWccxU7yY4xIFhw0DQyO35W_Qrvu03DG_8re1tIdHG76fGZv0xF64gWnRrZc0rwAIXYOc5PO3M6fDdhWQPDRb_UUMxpsXccRl3F5aByZsvCIUcmR_64tBAi8q_G6U0DMOjtaleWDxC7OdYCK5sJmhwbtohQURuVTT23IntnHJvmBS0ax5tey3lUbR-qglkzfzTh8DBwAdIE-d4mkubxa456zWYPcrKLmFvaV0000__y30000)
### Mô tả hệ thống giao dịch

- **Customer**: Đại diện khách hàng, liên kết với các tài khoản ngân hàng.
- **Transaction**: Giao dịch tài chính, hỗ trợ hành vi `reverse()` để hoàn giao dịch.
- **Statement**: Tạo báo cáo giao dịch và hỗ trợ xuất ra file PDF.
- Hệ thống đảm bảo tính chính xác khi liên kết khách hàng, quản lý giao dịch, và xuất báo cáo.

## PrintService
![](https://www.planttext.com/api/plantuml/png/T5FBJiCm4BpdAwoSKWGLN2E42kgb225G17VNMOgH7vMzhYY8B-F09_4BE0ydSLryidV7wvdPzU_tpy8YDUYao9YWrf87mnLMO7QS0VdCIBkiMqkERUfMhuitlIv9ECrASgEr0AfwCAEAWPY2LykILEW3cmIyWGPK8KLd4sYtwP5RmxNXo3yWgNeQalkIh1GcZmXkyLe8VyyMFdddZvU1trNsbKsb-z0WEtgaZzMQEGaAIxBiTp6_ZaBmhTLrKA4pi_Z7jpJkjZL5w2sAAthii-RrA25m6YG4keaEv2ZW8CQqmbPQ5AKENxKfoPC5CtQjSb9Iio_6DiK-FZfmC7NI9iRtvUlws4orkZg40QbtQTTZaATq3-_jnCt6GYEfXlr0n_b3ueYYyfWXbE5AlUYZJGns5zxcSI0Etez-rDdPn9viubH-aJV9_7m-Fyd7-yDC-jmmS4ENVR3joW9KtNpXFm000F__0m00)

### Mô tả hệ thống in tài liệu

- **User**: Đại diện cho người gửi tài liệu.
- **PrintJob**: Công việc in, được ưu tiên xử lý dựa trên thuộc tính `priority`.
- **PrintQueue**: Quản lý hàng đợi in, xử lý công việc theo thứ tự ưu tiên.
## ProjectManagementDatabase
![](https://www.planttext.com/api/plantuml/png/T5FBJiCm4BpdAwoSKWGLN2E42kgb225G17VNMOgH7vMzhYY8B-F09_4BE0ydSLryidV7wvdPzU_tpy8YDUYao9YWrf87mnLMO7QS0VdCIBkiMqkERUfMhuitlIv9ECrASgEr0AfwCAEAWPY2LykILEW3cmIyWGPK8KLd4sYtwP5RmxNXo3yWgNeQalkIh1GcZmXkyLe8VyyMFdddZvU1trNsbKsb-z0WEtgaZzMQEGaAIxBiTp6_ZaBmhTLrKA4pi_Z7jpJkjZL5w2sAAthii-RrA25m6YG4keaEv2ZW8CQqmbPQ5AKENxKfoPC5CtQjSb9Iio_6DiK-FZfmC7NI9iRtvUlws4orkZg40QbtQTTZaATq3-_jnCt6GYEfXlr0n_b3ueYYyfWXbE5AlUYZJGns5zxcSI0Etez-rDdPn9viubH-aJV9_7m-Fyd7-yDC-jmmS4ENVR3joW9KtNpXFm000F__0m00)
### Mô tả hệ thống quản lý dự án

- **Task**: Có thuộc tính `priority` và liên kết với **TeamMember** để chỉ định công việc.
- **ProjectReport**: Tự động tạo từ dữ liệu dự án và hỗ trợ xuất file PDF.
- **IProjectManagementDatabase**: Thêm chức năng `assignTeamMember()` để phân công thành viên.
- Hệ thống tối ưu quản lý nhiệm vụ, báo cáo và phân công nhóm hiệu quả.


---
## Xác định các trạng thái
### Quản lý Thẻ Chấm Công
![](https://www.planttext.com/api/plantuml/png/V9AzJWCn3CTtFuLdfBv01rHKs14C31L3cdDBq2KNEMaHpzQ1H-8LI9ph9ITTcUBOl_pzbT_BpoP4nV5aUzZTlUDgTO-Fh0uHG0vnl9xsriH87QunY8tHMDAAEwYnJ3vupyDPG5NCM-GBVP8kaYnc1M5IoU0p3vf2CEwOq2k3Vl920mYlJ1RrwXiF0rVL1UpDn8ydvaGL_YlTaR83vk5Iy9XJAhxQwPab5w56snhc4AgZCWvWQhsTGqws7MpcGfs9LAH7DoooqyRarTc4PkJIXX1vj-kiv7jA2Wlz5O9SruwX_e6jSfhwNXQcnRwrsVz8gC5vpd5Ki4cN_1V_0000__y30000)
### Mô tả các trạng thái thẻ chấm công

### 1. **Processing**
- **Mô tả**: Giai đoạn xử lý thẻ chấm công sau khi phê duyệt và trước khi thanh toán.
- **Chi tiết**: Trong giai đoạn này, thẻ chấm công sẽ được chuẩn bị để thanh toán. Tuy nhiên, có thể phát sinh lỗi trong quá trình thanh toán, dẫn đến việc chuyển sang trạng thái **PaidWithError**.

### 2. **PaidWithError**
- **Mô tả**: Trạng thái khi thẻ chấm công đã được thanh toán nhưng có lỗi xảy ra trong quá trình thanh toán.
- **Chi tiết**: Nếu có lỗi trong khi thực hiện thanh toán, thẻ chấm công sẽ chuyển sang trạng thái **PaidWithError**. Quá trình thanh toán cần được **Reprocess** lại để sửa lỗi và hoàn tất thanh toán.

### 3. **RejectedWithComments**
- **Mô tả**: Trạng thái khi thẻ chấm công bị từ chối và có lời giải thích đi kèm.
- **Chi tiết**: Nếu thẻ chấm công không hợp lệ hoặc có vấn đề, nó sẽ bị từ chối với lý do rõ ràng. Sau khi xem xét các lý do từ chối, thẻ có thể được **Revise** lại để sửa chữa và nộp lại.
### Quản lý Giao Dịch (Transaction)
![](https://www.planttext.com/api/plantuml/png/X94z3i8m38Ntd28pKY_G0LL2CAEkY26aBef8ayf949oDWIDn1UhqBoq3Koo_xptPpkVrBfmNw4EZsMbpvbcsvKSmbJ9NneOYDlSFaC53nNCEVSaz2kE4zCeQDian0Aq4vyYQfnHl9u4b35bsjcarzFcfmmL9M1tqsd4GIl_WTMmoDeZ4bU3nsM4OttJcNbajXv3ztQ-qMb-4l14-belWiKamNNKv9C8TqD6OyzOpsTry4LPq3VgTBm000F__0m00)
### Mô tả các trạng thái giao dịch

### 1. **Processing**
- **Mô tả**: Giai đoạn giao dịch đang được xử lý.
- **Chi tiết**: Trong trạng thái này, giao dịch đang được thực hiện và các thao tác liên quan đến nó đang diễn ra. Giao dịch có thể hoàn tất thành công hoặc gặp sự cố, dẫn đến các trạng thái khác.

### 2. **Retry**
- **Mô tả**: Giao dịch có thể bị thất bại và được thử lại.
- **Chi tiết**: Nếu giao dịch không thành công trong lần xử lý đầu tiên, hệ thống sẽ chuyển sang trạng thái **Retry** để thử lại giao dịch. Việc thử lại có thể xảy ra nhiều lần cho đến khi giao dịch thành công hoặc chuyển sang trạng thái khác.

### 3. **Rollback**
- **Mô tả**: Nếu giao dịch không thể hoàn tất, hệ thống sẽ thực hiện Rollback để đảo ngược giao dịch, phục hồi trạng thái ban đầu.
- **Chi tiết**: Khi giao dịch không thể hoàn thành (do lỗi hoặc thất bại liên tục), hệ thống sẽ quay lại trạng thái ban đầu và phục hồi các thay đổi đã thực hiện, đảm bảo tính toàn vẹn của dữ liệu.

### Quản lý Nhân Viên và Quy Trình Thay Đổi Trạng Thái
![](https://www.planttext.com/api/plantuml/png/b9L1JyCW5CVlV0hEnXtrqCHbYydYmSH4ZyO3TgyRiOK9T6QVpOCVoQyWjAnxG1tTgUtZzzYlVoZx_VvPQCEKQPkQl5wzqTbiJX-uWZKXtQKlo5RL1rhGRLVQTeze_8NLJ77xS2IqAs3YNZODrvfBWQWI5GDM6CLACt1CMzJNeDdLyW1WzNgfwFVBBHCRUsTaBy7Tr2Soya1qA8Cx1fk0Jdm6YI0nrEDZ2xY9Fb7FHADWyenLmcOoJVWBh7mfQuIuh0rY9sQA5_aHs1wUgkMx1b62RLBmsO8sj7O3OVmPDWacooFr34kYyI111QPLOWn1uVqFHQcT0uU5zX1ESjLziGMjkcib5RMpsbsmRaiJvdYMJ5BCq2Z38tdQUc9j2xR3W6guOCOj_ceuRjofLpY8oiflqmP49FiCna_BDa3dT_Js9dKSWr0qutCWyp6078k9QiaKW0hFmLRl-hSjg1xkNLXxBcjch6huMbCQqfDXKXF-U2Sqa1E45v5LTj5yarEuxZT0H2zBm_SmYlTRr7tyNr9za8LjSdzrVm000F__0m00)
### Mô tả các trạng thái nhân viên

### 1. **Suspended**
- **Mô tả**: Nhân viên bị đình chỉ công tác vì vi phạm nội quy hoặc lý do khác.
- **Chi tiết**: Trong trạng thái này, nhân viên tạm thời không làm việc do vi phạm quy định của công ty hoặc lý do khác. Thời gian đình chỉ có thể thay đổi tùy thuộc vào mức độ vi phạm.

### 2. **Fired**
- **Mô tả**: Nhân viên bị sa thải vì vi phạm hoặc lý do khác.
- **Chi tiết**: Nhân viên bị sa thải khi vi phạm nghiêm trọng các quy định công ty hoặc không hoàn thành công việc. Khi ở trạng thái này, nhân viên không còn làm việc tại công ty.

### 3. **Active**
- **Mô tả**: Nhân viên trở lại làm việc sau khi hết thời gian đình chỉ.
- **Chi tiết**: Nhân viên quay lại làm việc sau khi hoàn tất thời gian đình chỉ và các vấn đề đã được giải quyết. Trạng thái này chỉ ra rằng nhân viên hiện tại đang làm việc và có thể tiếp tục nhiệm vụ bình thường.


### Quy Trình Xử Lý Chấm Công với Các Tình Huống Ngoại Lệ
![](https://www.planttext.com/api/plantuml/png/X5B1JiCm3BtxAt96sW_iW8Oc3jpG42V48KlDQfGcaPCMzTiuy4dy0awQhcn5ulPilsSxp_d-_Dh5f3drdOMNcrUrsTog1qU9j0Mee2IV-cD7AM6ZjYeMh19rQ3GtiDGoyzaro0SS23-4s-T8SGdXTobJxq9WFvIUUeR7KVe7v86YvvNYWEzefYruXfSAE3VD_4TDcIiPWp6geCSENOAIplNyvgqolWiMfHV0UK1Hesl8dVQUMPBadN0TOXD5CQTWJRhsYx4wfj-IcF6lTg-TGMkBrXIyUBrov3uQRVKq22kkVglaLKkdLcRgFhMUAOsmyF--G5sojifBNYfM5rWBhXIJn_BI-Gomao3_k1y0003__mC0)
### Mô tả các trạng thái thẻ chấm công

### 1. **UnderReview**
- **Mô tả**: Thẻ chấm công đang được xem xét.
- **Chi tiết**: Trong trạng thái này, thẻ chấm công của nhân viên đang được kiểm tra và xem xét để đảm bảo tính chính xác. Việc phê duyệt hoặc từ chối sẽ được thực hiện sau khi hoàn tất việc kiểm tra.

### 2. **Escalated**
- **Mô tả**: Trường hợp thẻ chấm công cần được xem xét bởi cấp trên hoặc bộ phận cao hơn nếu có vấn đề phát sinh.
- **Chi tiết**: Khi có vấn đề nghiêm trọng hoặc không thể giải quyết ở cấp độ hiện tại, thẻ chấm công sẽ được đưa lên cấp trên hoặc bộ phận có thẩm quyền để tiếp tục xem xét và xử lý.

### 3. **PendingCorrection**
- **Mô tả**: Thẻ chấm công cần sửa chữa sau khi bị từ chối và sẽ được gửi lại để phê duyệt hoặc hủy.
- **Chi tiết**: Sau khi thẻ chấm công bị từ chối, nhân viên hoặc bộ phận liên quan cần sửa chữa và điều chỉnh lại thông tin. Thẻ sẽ được gửi lại để phê duyệt hoặc có thể bị hủy nếu không còn phù hợp.



---
## Xác định các thuộc tính
---
## Xác thực thuộc tính cho Timecard
![](https://www.planttext.com/api/plantuml/png/X9BFQW8n4CRl-nJ3dhGGiTTGYbGh2ZqKAlKSDiEQcir84eMbzCbww2Fr5PgiwzRT5SrX3ZFVDtz-vFVxP-Ayi7vVw2JJmZbOgG8pOILy9X0U0qzUw0NjhUCmroHydKVZhSAGV57EFvnipo5RFfuanKvJYRYSSLYQex4A048UfOFOfkJGyWzhaSM23dXRbwDVDLiEXkTx0Xo4LbBuQsquF15f5APZQJUzh5cJtIgJzrHVIGTeDQgXkka3pJR2vZWbYHpU0bkJruKuXiCin2jS6IYtHjoYaUrL6UmiVM3cUvthIvHxZxVqJmnOfyrEiNpchQeNUOVyw__0dasv1KLoPGTMy-_I-nI8CKZ7ez5TsiQNJC9vyQ_-0G00__y30000)
### Xác thực các mục nhập thẻ chấm công

### 1. **validateEntry()**
- **Chức năng**: Kiểm tra tính hợp lệ của mỗi mục nhập.
- **Chi tiết**: Phương thức này xác nhận số giờ làm việc của mỗi mục nhập có hợp lý không. Ví dụ: số giờ làm việc cho từng mục phải nằm trong một khoảng hợp lý, không vượt quá giới hạn (như 12 giờ trong một ngày).

### 2. **validateWorkingHours()**
- **Chức năng**: Kiểm tra xem tổng số giờ làm việc có vượt quá quy định không.
- **Chi tiết**: Phương thức này xác nhận tổng số giờ làm việc trong một khoảng thời gian (ví dụ: trong một tuần) có vượt quá quy định hay không, ví dụ như không vượt quá 40 giờ trong một tuần.

### 3. **isHoliday() trong TimecardEntry**
- **Chức năng**: Kiểm tra xem mục nhập có rơi vào ngày lễ không.
- **Chi tiết**: Phương thức này kiểm tra xem ngày mà mục nhập tương ứng có phải là ngày lễ hay không. Nếu là ngày lễ, số giờ làm việc có thể được tính theo một cách khác (ví dụ: trả lương gấp đôi).

### 4. **isWeekend() trong TimecardEntry**
- **Chức năng**: Kiểm tra xem mục nhập có vào cuối tuần không.
- **Chi tiết**: Phương thức này xác định xem mục nhập có rơi vào ngày cuối tuần (thứ Bảy hoặc Chủ Nhật). Nếu có, có thể áp dụng các quy tắc đặc biệt, như trả lương cao hơn hoặc giới hạn số giờ làm việc.

## Xác thực thuộc tính cho Employee, Transaction, ChargeNumberList
![](https://www.planttext.com/api/plantuml/png/T9BFJiCm3CRlVGgh9vYq2QuHGeDkI9FGBgkucyugaV879UuaX7Wo3ZmIhq3QLINDsXnoy6Vxyo_nx_VFsZCwRhJAAeNUmrQ_A_j119yPXBC4wWExZO2TOQh99SeUDGaui9EcxYMiASqEFjpuKLvt0KZ_WaeUjuFHrRM0HsiLeHcdFDGqgnsw_h7ybVLCfKFZiM9fpO35_x5BiaZS80UKzfxd2BpQDeO5F2cBFC5Mncwp2ENOTluPEhT9rE8DNKtxHh-IUvQU1zug4iBqhNPtHhYVo2ZEEF6hZ4T8VMPdBTAkoTZ3lkMtEIoMIyXlLgj5Flep0HfDM2cVnT6au89SW3GdgqwXR4tcsAxu7m000F__0m00)
### 1. **Employee**
- **employeeID**: Phải duy nhất và dương.
  - **Chi tiết**: Mã nhân viên phải là một giá trị duy nhất trong hệ thống và có giá trị dương.
  
- **employeeName**: Không trống, không có ký tự đặc biệt.
  - **Chi tiết**: Tên nhân viên không được để trống và không chứa các ký tự đặc biệt không hợp lệ.

- **age**: Phải từ 18 trở lên.
  - **Chi tiết**: Tuổi của nhân viên phải là một giá trị từ 18 tuổi trở lên.

- **status**: Phải là một trong các giá trị hợp lệ ("Hired", "Terminated", "On Leave", "Retired").
  - **Chi tiết**: Trạng thái của nhân viên phải thuộc một trong các giá trị sau: "Hired" (Đã tuyển dụng), "Terminated" (Đã thôi việc), "On Leave" (Đang nghỉ phép), "Retired" (Đã nghỉ hưu).

---

### 2. **Transaction**
- **transactionID**: Phải duy nhất và dương.
  - **Chi tiết**: Mã giao dịch phải là một giá trị duy nhất và có giá trị dương trong hệ thống.

- **transactionDate**: Ngày hợp lệ và không phải quá khứ.
  - **Chi tiết**: Ngày giao dịch phải là một ngày hợp lệ và không được là ngày trong quá khứ.

- **status**: Phải là một trong các giá trị hợp lệ ("Pending", "Completed", "Failed").
  - **Chi tiết**: Trạng thái của giao dịch phải là một trong các giá trị sau: "Pending" (Chờ xử lý), "Completed" (Hoàn thành), "Failed" (Thất bại).

- **amount**: Phải là số dương.
  - **Chi tiết**: Số tiền giao dịch phải là một giá trị dương.

---

### 3. **ChargeNumberList**
- **chargeNumbers**: Phải có mã chi phí hợp lệ và không trùng lặp.
  - **Chi tiết**: Mỗi mã chi phí trong danh sách phải hợp lệ và không được trùng lặp.

- **chargeNumberCount**: Phải khớp với số lượng phần tử trong danh sách chargeNumbers.
  - **Chi tiết**: Số lượng mã chi phí trong danh sách phải chính xác và khớp với giá trị `chargeNumberCount`.
---
## Xác định các phụ thuộc, quan hệ kết hợp
---
## Interface
![](https://www.planttext.com/api/plantuml/png/T56nRi8m4Dtz5QTC2L9GMJsXAeid1WhCr_WQ6HadifqYLF5b3Fsa_a9jav0s4XvET-_UlUUpVsxVQ-VH-lwacJAUx0VM148yqYy6wKZbEesNdSYB0QbRhQdsmdIzpmiEEqSs5KFVaf5aA_IOon0uRDwFWJ-Ezrr0QQ_ed7-6m67hhJ9DmQwCrHgTcmI7IvIWObKbiJjxq6h8HtBoAcOzvVQebOpuQzjgGZCv79GCem_vSof5nI7ktv3zXxzTEffftrUSIVzvl6oLmQ8i8NjPBXVPQCVXX0ORSi-e8Prsv-D3ExOETl6ZVW400F__0m00)
#### Mô tả IInterface

### 1. **IInterface**: Quản lý nhiều Widget
- **Chức năng**: IInterface chịu trách nhiệm quản lý các Widget, bao gồm các phần tử giao diện người dùng như nút bấm, ô nhập liệu, danh sách thả xuống, v.v.
  
### 2. **Tương tác với UserInput**
- **Chức năng**: IInterface tương tác với **UserInput** để thu thập dữ liệu người dùng. Các Widget sẽ nhận dữ liệu từ người dùng và chuyển tiếp cho IInterface để xử lý.

### 3. **Hiển thị và Cập nhật Giao Diện**
- **Chức năng**: IInterface có khả năng hiển thị các Widget và cập nhật giao diện khi có sự thay đổi, đảm bảo rằng các phần tử trên giao diện luôn phản ánh dữ liệu và trạng thái hiện tại.

## Security
![](https://www.planttext.com/api/plantuml/png/R93D2i8m3CVlVOgmqnnkwBMd8Lvs4uOF4BggXTfAcoegFfa77ybNS2iJLp27199VFlvvFr-r9tGKZfefGzBjK4XeMYc2KtI5EuDe6EWW3Ic19FFWfUEmxVsCmyfQBT5CEElKRGhD0GKfQpYqv9JPJveUZ0cDtaTkN5R2qDgil_YOFFNOnRekIGESKQkkFsepblDq-az9jioWACiOupQUYFB_q4LL5GaTfNbMIzCD7_i0003__mC0)
#### Mô tả ISecurity

### 1. **ISecurity**: Phụ thuộc vào User để thực hiện xác thực và ủy quyền
- **Chức năng**: ISecurity phụ thuộc vào đối tượng **User** để thực hiện các tác vụ xác thực và ủy quyền. Nó sử dụng thông tin người dùng để xác định quyền truy cập và tính hợp lệ của các thao tác yêu cầu bảo mật.

### 2. **Cung cấp các phương thức bảo mật**
- **Chức năng**: ISecurity cung cấp các phương thức bảo mật như:
  - **Xác thực người dùng**: Kiểm tra xem thông tin đăng nhập của người dùng có hợp lệ hay không.
  - **Kiểm tra quyền truy cập**: Đảm bảo rằng người dùng có quyền truy cập vào các tài nguyên hoặc chức năng nhất định trong hệ thống.

## Distribution 
![](https://www.planttext.com/api/plantuml/png/L50nRW913Ept5HOLHBc2zYgIqD3Gy0Apwn0hTzwJxOC2yJAAF2bVOEyu8kB2jgmPpOn_hpyhSrJlsoQmEEadHeBDcisLzxrp5ZW76Cj8qXeTvwcq6dO58OTNI6JEWWFqSLpKy9vpGoWJLIaI7sbaM-urqXFqleHB2B51CzYIdx9-JxeLSFUMafBP7_H-xx9w3PlY-a0w2HKlk6_OlZwo2CN1rFp9JT7udsssdC5BLOtpeLj3p6tR2qTqih0giOVtt0000F__0m00)
#### Mô tả IDistribution

### 1. **IDistribution**: Phụ thuộc vào Network để truyền và nhận dữ liệu giữa các hệ thống
- **Chức năng**: IDistribution phụ thuộc vào dịch vụ **Network** để thực hiện việc truyền và nhận dữ liệu giữa các hệ thống. Nó đảm bảo quá trình truyền thông tin được thực hiện đúng cách và hiệu quả.

### 2. **Phân phối dữ liệu và tương tác với dịch vụ mạng**
- **Chức năng**: IDistribution chịu trách nhiệm phân phối dữ liệu từ một hệ thống đến các hệ thống khác và đảm bảo tính toàn vẹn của dữ liệu trong quá trình giao tiếp. Nó tương tác với các dịch vụ mạng để duy trì kết nối và xử lý các yêu cầu phân phối dữ liệu.

## Persistency
![](https://www.planttext.com/api/plantuml/png/R90n3i8m34NtdCBgL90wi7QgW8K994xW9WQ2WeDY0qA8ap5m9Av0AQKI0W_syhw__H-tUoMAIG-xO3mhfHLQWjc2adXHOdk6Yu6s18yqHSNSDQs4URqbguCInZ46Gkwe4D6rb7V4wbUUKWbBJPxNWu_8N8sn0KNWHTOer9aKO2DpG_Z8Ryr7sssFU-99Z-G_xZP4eVz0u_drLZRAO5WKxUpFAA4D0QqAdBnkJ4NiNjay0G00__y30000)
#### Mô tả IPersistency

### 1. **IPersistency**: Phụ thuộc vào Database để lưu trữ và tải dữ liệu từ cơ sở dữ liệu
- **Chức năng**: IPersistency phụ thuộc vào **Database** để lưu trữ và tải dữ liệu từ hệ thống cơ sở dữ liệu. Nó sử dụng các phương thức của Database để thực hiện các thao tác đọc và ghi dữ liệu.

### 2. **Quản lý dữ liệu dài hạn và giao tiếp với hệ thống cơ sở dữ liệu**
- **Chức năng**: IPersistency chịu trách nhiệm quản lý dữ liệu dài hạn, bao gồm việc lưu trữ, truy xuất và cập nhật dữ liệu. Nó giao tiếp trực tiếp với hệ thống cơ sở dữ liệu để đảm bảo rằng dữ liệu được bảo mật, toàn vẹn và có thể truy xuất khi cần thiết.

## Everything 
![](https://www.planttext.com/api/plantuml/png/V91D2i8m48NtESNGbGfTkEsgY2ww4tA2c8usaAQIcHIAU38N7iahE2qYYjXiGjxxykRdSRkNn2PoQhsotX31hiSuSEF22IuAvEGW2hak5A0vYlvIQI36LhDX_780faGzsOjb0PkkysZ2s-pElzvLgO_2sJg3LPvFTrK5ndWq5g60H4X_GOqsHSU3S1WenHbqwqWQFYIMiGHlJAZz3BuV5o0j1pk6omII3V878aeCzlAg3HjLOgZ7JJu1003__mC0)
#### Mô tả Everything

### 1. **Everything**: Phụ thuộc vào tất cả các giao diện IInterface, ISecurity, IDistribution, và IPersistency
- **Chức năng**: **Everything** là lớp tổng hợp, phụ thuộc vào tất cả các giao diện sau:
  - **IInterface**: Để thực hiện các chức năng liên quan đến giao diện người dùng, như quản lý Widget, thu thập và hiển thị dữ liệu.
  - **ISecurity**: Để xử lý các tác vụ bảo mật, bao gồm xác thực người dùng và kiểm tra quyền truy cập.
  - **IDistribution**: Để phân phối dữ liệu và tương tác với các dịch vụ mạng, đảm bảo truyền và nhận dữ liệu giữa các hệ thống.
  - **IPersistency**: Để lưu trữ và tải dữ liệu từ cơ sở dữ liệu, quản lý dữ liệu dài hạn và giao tiếp với hệ thống cơ sở dữ liệu.

### 2. **Khởi động và dừng hệ thống, quản lý các thành phần hệ thống**
- **Chức năng**: **Everything** chịu trách nhiệm khởi động và dừng hệ thống, quản lý vòng đời của các thành phần hệ thống. Nó đảm bảo các giao diện và các thành phần của hệ thống hoạt động đồng bộ và hiệu quả.

