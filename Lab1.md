#Lab 1
 __Câu 1: Phân Tích Kiến Trúc__
 
     Đè xuất kiến trúc là 
 __Câu 2: Cơ Chế Phân Tích__
 
 __Câu 3: Phân Tích Ca Sử Dụng Select Payment__
 __a. Xác định các lớp phân tích__
 
        - Các lớp phân tích
           + PaymentProcessor:Chịu trách nhiệm xử lý các phương thức thanh toán, bao gồm xác minh phương thức thanh toán của nhân viên và thực hiện các thao tác 
           thanh toán.
              - PaymentMethoad: Lớp trừu tượng,đại diện cho phương thức thanh toán(mail, direct deposit, pick-up)
              - DirectDepositpayment: Thanh toán bằng cách chuyển tiền trực tiếp vào tài khoản ngân hàng của nhân viên.
              - MailPayment: Thanh tonas bằng cách gửi tiến qua bưu điện tới địa chỉ đươc chỉ định.
              - PickUpPayment: Thanh toán bằng cách nhận trực tiếp tại văn phòng công ty.
           + Employee:Đại diện cho thông tin nhân viên bao gồm thông tin cá nhân và phương thức thanh toán đã chọn.
           + PayrollDatabase:Lưu trữ và quản lý dữ liệu nhân viên, thông tin payroll (bảng lương), bao gồm các phương thức thanh toán, lương hàng tháng, và chi 
            tiết payroll của từng nhân viên.
           + TransactionHistory:Chứa thông tin về lịch sử các giao dịch thanh toán của nhân viên, bao gồm ngày giao dịch, số tiền, và phương thức thanh toán.
 __b. Mô tả hành vi thông qua biểu đồ tuần tự__
 
 ![Diagram](https://planttext.com/api/plantuml/png/Z9513e8m44NtSufUW0kmC13YqeH8F42bepIs7UmK3MTpuP6yWZQ461j2NC__x_-PUJsU1GVfms0D05-q4vuO0RQsDpGYYYpRY5gEdemfbTLES_0oaC_57gy3SeXJYow87OQEbAWwwSu8IvuP5kMJEXTDHtTHtgGsycWmWV4_FHeqsAOrLlFZeFRK8dC477ebGneDgMwfV4NkfBrTFy4lOLxeQvxY0Q10fpv_U0C00F__0m00)
 __c. Xác định nhiệm vụ của từng lớp phân tích__
 
         - Employee:
           + Xem và chọn phương thức thanh toán phù hợp từ các tùy chọn, gồm DirectDepositPayment, MailPayment, và PickUpPayment.
           + Xác nhận phương thức thanh toán đã chọn để thực hiện giao dịch.
         - PaymentProcessor:
           + Đảm nhận việc truy xuất và xử lý phương thức thanh toán của nhân viên.
           + Tương tác với PayrollDatabase để lấy thông tin thanh toán của Employee.
           + Dựa trên phương thức thanh toán đã chọn, PaymentProcessor sẽ gọi lớp tương ứng (ví dụ: DirectDepositPayment, MailPayment, PickUpPayment) để thực hiện 
             thanh toán.
           + Ghi lại các giao dịch thành công vào TransactionHistory.
                - DirectDepositPayment:
                   + Thực hiện việc chuyển khoản lương trực tiếp vào tài khoản ngân hàng của Employee.
                   + Tương tác với TransactionHistory để ghi nhận giao dịch.
                - MailPayment:
                   + Xử lý thanh toán qua đường bưu điện, đảm bảo gửi phiếu lương tới địa chỉ đã đăng ký của Employee.
                   + Tương tác với TransactionHistory để ghi nhận giao dịch.
                - PickUpPayment:
                   + Xử lý việc cho phép Employee đến nhận trực tiếp tại văn phòng.
                   + Tương tác với TransactionHistory để ghi nhận giao dịch khi Employee nhận tiền lương.
         - PayrollDatabase:
           + Cung cấp thông tin về bảng lương, phương thức thanh toán đã đăng ký của Employee.
           + Lưu trữ các dữ liệu cần thiết cho các yêu cầu truy xuất từ PaymentProcessor.
         - TransactionHistory:
           + Ghi lại chi tiết giao dịch bao gồm ngày, phương thức thanh toán, số tiền và các chi tiết liên quan khác để phục vụ cho báo cáo và đối chiếu trong 
             tương lai.
 __d. Xác dịnh một số thuộc tính và quan hệ giữa các lớp phân tích__
       ![Diagram](https://planttext.com/api/plantuml/png/Z5HBJiCm4Dtd5BE4HIuGLLKh1Gca5bLy3k0uLcFXs94zgOY04t0A5brMi62LBhf0uXuv0LV09Q5DY2kQHHHdPjvdPkIlzMPaa6ZCK-5HGOo1ipGJgc0C7ZpuULZpuo8Cu1erb_Cca94YPHAd31CL1p1h7viKGmJHHG2XoYF1l2Ul8MboPrfHPepIEpBKH1f2aIlPuoEfoYKwmRGI8YH88cBwmgyOLJes0KoumS6ll-4Uu6PFUcvJb2vSUYm-i-JsVRp_Fv8FDjHA8P6nP1IXqw4QRISdgnlM14zE0rWe7k-TX5mpYY7BbE7OP06xHoRZGv0HaNTZIckTdNvhbQCzNUPfn7HRQiqr9LmSHv7QJ5iwZcDjnVUHPfpUtMR7OMKsDyycYfBjJDfOkyNr_M5l9m8Gds-v7MUrVWLCFjxb7AmvhxU8xcBKUG6BgbpAVuiTonJ0FE4WawfSIPXpeY2kriyqESZUyXs0gTQhRS7Iskp61e--xnovAwyrBbUuCmFFOS8bRMjBLEKB1sg_a5Vb1Zi6lP4TvVPk-GO00F__0m00)
       
       - Employee:
            + Thuộc tính:
             employeeID: Mã định danh của nhân viên.
             paymentMethod: Phương thức thanh toán đã đăng ký của nhân viên, có thể là DirectDepositPayment, MailPayment, hoặc PickUpPayment.
             salary: Mức lương của nhân viên.
            + Quan hệ:
             Employee có quan hệ với PayrollDatabase để lưu trữ thông tin cá nhân và bảng lương.
       - PaymentProcessor:
            + Thuộc tính:
             transactionID: Mã định danh cho mỗi giao dịch thanh toán.
             amount: Số tiền cần thanh toán.
            + Quan hệ:
             PaymentProcessor có quan hệ với PayrollDatabase để lấy thông tin về nhân viên và phương thức thanh toán.
             PaymentProcessor có quan hệ với TransactionHistory để ghi lại các giao dịch đã hoàn tất.
             PaymentProcessor sử dụng các lớp DirectDepositPayment, MailPayment, và PickUpPayment để thực hiện các phương thức thanh toán tương ứng.
        - PayrollDatabase:
            + Thuộc tính:
             employeeRecords: Danh sách thông tin nhân viên bao gồm các thông tin như employeeID, paymentMethod, salary.
            + Quan hệ:
             PayrollDatabase chứa dữ liệu của Employee và được truy vấn bởi PaymentProcessor.
        - TransactionHistory:
            + Thuộc tính:
             transactionDate: Ngày thực hiện giao dịch.
             paymentMethod: Phương thức thanh toán sử dụng.
             amount: Số tiền giao dịch.
             employeeID: Mã nhân viên thực hiện giao dịch.
            + Quan hệ:
             TransactionHistory có quan hệ với PaymentProcessor để ghi nhận lịch sử các giao dịch thanh toán.
             Các lớp DirectDepositPayment, MailPayment, và PickUpPayment tương tác với TransactionHistory để ghi lại chi tiết giao dịch.
         - DirectDepositPayment:
            + Thuộc tính:
             bankAccount: Số tài khoản ngân hàng nhận tiền.
             routingNumber: Mã ngân hàng để chuyển khoản.
            + Quan hệ:
             DirectDepositPayment có quan hệ với TransactionHistory để ghi lại chi tiết giao dịch chuyển khoản.
         - MailPayment:
             + Thuộc tính:
              mailingAddress: Địa chỉ bưu điện để gửi phiếu lương.
             + Quan hệ:
              MailPayment có quan hệ với TransactionHistory để ghi lại chi tiết giao dịch khi gửi phiếu lương qua bưu điện.
         - PickUpPayment:
            + Thuộc tính:
              pickupLocation: Địa điểm mà nhân viên sẽ đến nhận tiền.
            + Quan hệ:
              PickUpPayment có quan hệ với TransactionHistory để ghi lại giao dịch khi Employee nhận lương tại địa điểm đăng ký.
 Câu 4: Phân Tích Ca Sử Dụng Maintain Timecard
        - Các lớp phân tích
 Câu 5: Hợp Nhát Kết Quả Phân Tích
