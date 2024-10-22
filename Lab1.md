#Lab 1
 Câu 1: Phân Tích Kiến Trúc
     Đè xuất kiến trúc là 
 Câu 2: Cơ Chế Phân Tích
 Câu 3: Phân Tích Ca Sử Dụng Select Payment
 a. Xác định các lớp phân tích
        - Các lớp phân tích
           + Employee : Lớp đại diện cho nhân viên,lưu trữ các thông tin cá nhân và các phương thức thanh toán
           + PaymentMethoad: Lớp trừu tượng,đại diện cho phương thức thanh toán(mail, direct deposit, pick-up)
              - DirectDepositpayment: Thanh toán bằng cách chuyển tiền trực tiếp vào tài khoản ngân hàng của nhân viên.
              - MailPayment: Thanh tonas bằng cách gửi tiến qua bưu điện tới địa chỉ đươc chỉ định.
              - PickUpPayment: Thanh toán bằng cách nhận trực tiếp tại văn phòng công ty.
           + PayrollAdministrator: Lớp này quản lý các hành động như thêm, sửa, xóa nhân viên và cập nhật thông tin nhân viên
           + PayrollProcessor: Xử lý tính toán và gửi các khoản thanh toán vào mối thứ Sáu hoặc cuối tháng.
 b. Mô tả hành vi thông qua biểu đồ tuần tự
 ![Diagram](https://planttext.com/api/plantuml/png/Z9513e8m44NtSufUW0kmC13YqeH8F42bepIs7UmK3MTpuP6yWZQ461j2NC__x_-PUJsU1GVfms0D05-q4vuO0RQsDpGYYYpRY5gEdemfbTLES_0oaC_57gy3SeXJYow87OQEbAWwwSu8IvuP5kMJEXTDHtTHtgGsycWmWV4_FHeqsAOrLlFZeFRK8dC477ebGneDgMwfV4NkfBrTFy4lOLxeQvxY0Q10fpv_U0C00F__0m00)
 c. Xác định nhiệm vụ của từng lớp phân tích
 d. Xác dịnh một số thuộc tính và quan hệ giữa các lớp phân tích
 Câu 4: Phân Tích Ca Sử Dụng Maintain Timecard
        - Các lớp phân tích
 Câu 5: Hợp Nhát Kết Quả Phân Tích
