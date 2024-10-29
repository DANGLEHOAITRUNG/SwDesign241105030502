#Lab 1
 __Câu 1: Phân Tích Kiến Trúc__
 
   __a. Đề xuất kiến trúc__
    
         Kiến trúc đề xuất cho hệ thống Payroll System là kiến trúc phân lớp (Layered Architecture). Đây là kiến trúc phù hợp cho các hệ thống có tính chất phức tạp và yêu cầu bảo trì 
         cao, giúp tách biệt các thành phần chức năng để dễ dàng quản lý, nâng cấp và mở rộng.

   __b. Giải thích lý do lựa chọn và ý nghĩa từng thành phần trong kiến trúc__
   
      - Kiến trúc phân lớp giúp chia hệ thống Payroll System thành các lớp chức năng riêng biệt, mỗi lớp có nhiệm vụ cụ thể và không phụ thuộc trực tiếp vào các lớp khác. Điều này giúp 
        hệ thống:
        + Tính bảo trì: Tách biệt các lớp giúp dễ dàng thay đổi hoặc nâng cấp một phần của hệ thống mà không ảnh hưởng đến các phần còn lại.
        + Tính mở rộng: Cho phép thêm hoặc thay đổi các lớp hoặc chức năng mới mà không ảnh hưởng đến hệ thống hiện tại.
        + Tính linh hoạt: Cho phép triển khai các lớp riêng biệt trên các máy chủ hoặc môi trường khác nhau, phù hợp với nhu cầu và tài nguyên của hệ thống.
      - Các lớp chính trong kiến trúc:
          - Presentation Layer (Lớp Giao diện):
            + Chức năng: Đây là lớp giao diện người dùng (UI), nơi người dùng tương tác trực tiếp với hệ thống.
            + Ý nghĩa: Cung cấp các chức năng như đăng nhập, lựa chọn phương thức thanh toán và quản lý thông tin timecard. Lớp này đảm bảo giao diện thân thiện và tối ưu cho người dùng.
          - Application Layer (Lớp Ứng dụng):
            + Chức năng: Là lớp trung gian kết nối giữa giao diện người dùng và các logic nghiệp vụ của hệ thống.
            + Ý nghĩa: Đảm nhận các xử lý logic chính của hệ thống, nhận yêu cầu từ lớp giao diện, gửi chúng tới lớp nghiệp vụ và trả về kết quả. Lớp ứng dụng giúp giảm tải cho lớp 
              nghiệp vụ, giúp các thao tác từ giao diện diễn ra mượt mà và hiệu quả.
          - Business Layer (Lớp Nghiệp vụ):
            + Chức năng: Chứa các logic nghiệp vụ như tính toán lương, quản lý timecard và xử lý thông tin thanh toán.
            + Ý nghĩa: Đây là thành phần trọng yếu của hệ thống, nơi thực hiện các tính toán phức tạp và các quy trình nghiệp vụ chính, đảm bảo rằng hệ thống hoạt động chính xác theo các 
              quy tắc của payroll.
          - Data Access Layer (Lớp Truy cập Dữ liệu):
            + Chức năng: Thực hiện các thao tác liên quan đến cơ sở dữ liệu như truy vấn, thêm, sửa, xóa dữ liệu.
            + Ý nghĩa: Đảm bảo việc truy cập dữ liệu được thực hiện một cách an toàn và hiệu quả. Lớp này là nơi duy nhất giao tiếp với cơ sở dữ liệu, giúp hệ thống bảo mật và tối ưu hóa 
              tốc độ truy xuất dữ liệu.
                
  __c. Biểu đồ package mô tả kiến trúc__
  
   ![Diagram](https://planttext.com/api/plantuml/png/Z9HBJiCm48RtEONL5Inw0HQeHI21H2L4om46PzfQE4xgHzK8iMRD6H12GaBiMw4koaLo0gw0xJxZjAMpc8Nz-v_FCqv-9zE6qY2rINWKPK0Ve8UaTWEvJ3adxLnfJ6haCI8sV5fh92eK6ZHB1Rc67ELIvu9oK8hSAPHNGgFi0iMDNHyyxJ5nT5nULCYHQbi_iTujrFqq3YK920lGOGbIa9kxJz4ybpcRMSOPtOkv8McZ7B8gQoPJYaejk6vnO53fxM0NISRJ70y7F3EA2Mk-YsunZ9Ptbo4P1KuD1urju23paAaF8kQuuAwWk0YgBR5tb8Cutd8n7oQBBSR1rpu73QH9wVytTyfxK9MXA1Ykkkqq8L0NDUrt90W5rCtsaYcTLbla5lTXkrn-oFNwwROtSq9glMBooKW--p245kDtGtvUYl5KrBp9bYFEAPYlTHbP5y9dt_uJeRPbNh3N91nRrKKl57EReEW6nwhRra9BavEHASPlciJ5v8jmLaoUJPaeBBt3Qs1jNeK7MgFOHz504Rk_pny0003__mC0)
      
 __Câu 2: Cơ Chế Phân Tích__
 
      - Đề xuất các cơ chế cần giải quyết trong bài toán Payroll System
         + Cơ chế 1: Xác thực và Phân quyền
            Lý do: Đảm bảo rằng chỉ người dùng có thẩm quyền mới có thể truy cập vào các chức năng nhạy cảm của hệ thống, chẳng hạn như quản lý thông tin lương của nhân viên hoặc duyệt 
            các yêu cầu thanh toán.
            Kết quả mong đợi: Hệ thống có thể ngăn chặn các truy cập trái phép và đảm bảo chỉ người dùng hợp lệ (nhân viên có quyền, quản lý payroll) mới có thể thực hiện các tác vụ cụ 
            thể.
         + Cơ chế 2: Lưu trữ và Truy xuất Dữ liệu
            Lý do: Dữ liệu lương và timecard của nhân viên cần được lưu trữ và truy xuất nhanh chóng, chính xác trong quá trình tính toán và xử lý payroll. Việc quản lý dữ liệu một cách 
          hiệu quả giúp hệ thống xử lý thông tin nhanh chóng và duy trì tính toàn vẹn của dữ liệu.
            Kết quả mong đợi: Hệ thống có cơ chế lưu trữ, truy xuất và cập nhật thông tin lương, timecard và các chi tiết giao dịch hiệu quả, hạn chế tối đa xung đột dữ liệu và đảm bảo 
          hiệu năng.
         + Cơ chế 3: Tính toán và Xử lý Lương
            Lý do: Quy trình tính toán lương phức tạp, có thể yêu cầu nhiều phương thức thanh toán khác nhau (chuyển khoản ngân hàng, phiếu lương qua bưu điện, nhận trực tiếp) và dựa 
          trên lịch sử timecard của từng nhân viên. Việc đảm bảo tính toán chính xác giúp tránh các sai sót về tiền lương và tăng tính chính xác trong hệ thống payroll.
            Kết quả mong đợi: Hệ thống có thể tính toán lương dựa trên các phương thức và lịch sử làm việc của nhân viên, đồng thời có thể linh hoạt khi thay đổi thông tin hoặc phương 
          thức tính toán nếu cần.
         + Cơ chế 4: Ghi nhận Lịch sử Giao dịch
            Lý do: Các giao dịch lương cần được ghi lại để dễ dàng kiểm tra, đối chiếu trong trường hợp có vấn đề hoặc yêu cầu kiểm toán. Lịch sử giao dịch minh bạch là cần thiết để bảo 
          vệ cả hệ thống và quyền lợi của nhân viên.
            Kết quả mong đợi: Hệ thống sẽ lưu lại đầy đủ các giao dịch thanh toán, bao gồm thông tin như ngày thực hiện, phương thức thanh toán và số tiền. Điều này giúp truy xuất và 
          kiểm tra thông tin một cách thuận tiện khi cần.
         + Cơ chế 5: Xử lý Lỗi và Bảo trì
            Lý do: Một hệ thống payroll ổn định cần có khả năng xử lý lỗi kịp thời để đảm bảo không ảnh hưởng đến hoạt động tính lương. Ngoài ra, khả năng bảo trì, nâng cấp định kỳ cũng 
          cần thiết để hệ thống hoạt động mượt mà và cập nhật các chức năng mới.
            Kết quả mong đợi: Hệ thống có khả năng phát hiện và thông báo lỗi kịp thời, cung cấp các báo cáo lỗi chi tiết để đội ngũ bảo trì khắc phục nhanh chóng. Đồng thời, hỗ trợ các 
          tính năng bảo trì định kỳ để cập nhật và duy trì hiệu năng.
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
 __Câu 4: Phân Tích Ca Sử Dụng Maintain Timecard__
 
   __a. Xác định các lớp phân tích__
        
            - TimecardManager: 
               + Lớp này chịu trách nhiệm quản lý và duy trì thông tin về timecard.
               + Nó cho phép các thao tác như thêm mới, cập nhật, và xóa timecard của nhân viên.
               + TimecardManager đóng vai trò như một lớp trung gian giữa người dùng và cơ sở dữ liệu, thực hiện logic nghiệp vụ liên quan đến timecard.
            - Employee: 
               + Đại diện cho nhân viên trong hệ thống.
               + Lớp này lưu trữ các thông tin cá nhân của nhân viên, bao gồm cả thông tin về timecard.
               + Đây là đối tượng được cập nhật khi có sự thay đổi trong timecard.
            - PayrollDatabase:
               + Lớp này thực hiện việc lưu trữ và truy xuất tất cả các dữ liệu liên quan đến payroll, bao gồm cả thông tin về timecard của nhân viên.
               + PayrollDatabase là nơi TimecardManager sẽ thực hiện các thao tác cập nhật hoặc truy xuất dữ liệu liên quan đến timecard của từng nhân viên.
               
   __b. Mô tả hành vi thông qua biểu đồ tuần tự__
          ![Diagram](https://planttext.com/api/plantuml/png/R94nIWD168NxFSLZAoroWHGIujgvOB4Uu7SoP0TsPvVPsU2MOc5bOM5bOn0H5K5G47QA51kynty2h-0a99AenV0pmtllUp_pvMQ3ofAnTPu596nXS5n94vJ-IGbLahO84vLBGMOKawQnD26eGX9lQuweCKMMHMJfX2gvr4J3RSr1NcP58sKO10i8Udi-fe_zbDsbXl3ZKK3Fp_KOOKnAMt-mXeT14YySqR2FnDGDJcjkxorishrxW_NITJuiksVyQXH4G_HMnCHmUuS9kxDDkrsHa2fs5_xExLHXHtCxgo6wjzsjradQFUN8sTqef0Mt7mA2svSIElN3_Xiis3tGJysDXGu_NsjaIvxefiARgS7yYjsrmgIxBVuiCv1wjFYoRm000F__0m00)
          
   __c. Nhiệm vụ của từng lớp phân tích__

            - TimecardManager: 
               + Đảm nhận việc quản lý timecard và thực hiện cập nhật các thông tin liên quan đến timecard của nhân viên.
               + Chịu trách nhiệm tương tác với PayrollDatabase để đảm bảo dữ liệu timecard luôn chính xác và đồng bộ.
            - Employee:
               + Là lớp đại diện cho từng nhân viên trong hệ thống, và là đối tượng chứa thông tin timecard sẽ được cập nhật.
               + Nhân viên có thuộc tính employeeID và timecardDetails để lưu các thông tin cá nhân và chi tiết timecard.
            - PayrollDatabase:
               + Thực hiện nhiệm vụ lưu trữ và quản lý dữ liệu liên quan đến timecard của nhân viên.
               + Cung cấp các thao tác như truy xuất, thêm mới, cập nhật thông tin timecard để hỗ trợ TimecardManager. 
               
   __d. Xác dịnh một số thuộc tính và quan hệ giữa các lớp phân tích__     
        ![Diagram](https://planttext.com/api/plantuml/png/V96zIWGn58NxFCLbId4Gss5PjXWBmGLHmVfk9km4CvCbkK47iR3oEImiB4HjPmextoDFu2juLsTcOVr9aS0vdE_c91_TsymJEWgL4K8Qz1uEgfMnZL9mBO1N2geN3lCCJidfUjaRf2ibqHMv8jJ6Pt2aFKtEUdKgRWRa8CsnngLoJ1wjOsoSDIP7mWNwpT21VQAaTGMpvxYQV4_VXNz6Z81BwowOgZ9OxxrOsk3yEJkgODs6XL5_bsJs-1PfElrnrGpC-qi0Sh5x1ehjlHRRHN-FKHcxLmcbZjrTpVdGm5M8xGFjWOpjqmhgaWyIsybaF_aY9Zl9fcy6ad6Fo27ctGOXPgekrl_v2G00__y30000)
        
        - Employee:
            + Thuộc tính:
               employeeID: Mã định danh duy nhất của nhân viên.
               timecardDetails: Chi tiết của các timecard liên quan đến nhân viên.
            + Quan hệ: Employee có quan hệ với PayrollDatabase, nơi lưu trữ thông tin timecard của từng nhân viên.
          - TimecardManager:
            + Quan hệ: TimecardManager liên kết với PayrollDatabase để thực hiện các thao tác truy xuất, thêm mới, và cập nhật timecard.
          - PayrollDatabase:
            + Thuộc tính:
              timecardRecords: Lưu trữ chi tiết tất cả các timecard, trong đó mỗi record chứa thông tin về thời gian làm việc, mã nhân viên, và ngày làm việc.
            + Quan hệ: PayrollDatabase chứa thông tin liên quan đến Employee và cho phép TimecardManager thực hiện các thao tác dữ liệu liên quan đến timecard.
 __Câu 5: Hợp Nhát Kết Quả Phân Tích__
 
   __a. Giới thiệu__
    
          Hệ thống Payroll System quản lý thông tin payroll của nhân viên, bao gồm các chức năng chính là Select Payment Method (chọn phương thức thanh toán) và Maintain Timecard (quản lý bảng chấm công). Hai chức năng này giúp nhân viên quản lý thông tin về phương thức nhận lương và thời gian làm việc, đảm bảo hệ thống có thể dễ dàng truy xuất, cập nhật thông tin thanh toán và bảng chấm công chính xác cho từng nhân viên.
   __b. Phân tích yêu cầu__
    
      Ca sử dụng 1: Select Payment Method
         Mô tả: Cho phép nhân viên chọn phương thức thanh toán lương như nhận trực tiếp, qua bưu điện, hoặc chuyển khoản ngân hàng.
         Yêu cầu chức năng:
         Nhân viên chọn phương thức thanh toán mong muốn.
         Hệ thống thu thập thông tin bổ sung (địa chỉ hoặc tài khoản ngân hàng) theo phương thức thanh toán.
         Thông tin được lưu lại trong hồ sơ payroll của nhân viên.
      Ca sử dụng 2: Maintain Timecard
         Mô tả: Cho phép nhân viên nhập và quản lý bảng chấm công, ghi lại số giờ làm việc của họ theo từng dự án và ngày làm việc.
         Yêu cầu chức năng:
         Nhân viên tạo hoặc truy xuất bảng chấm công cho kỳ lương hiện tại.
         Nhân viên nhập số giờ làm việc theo từng dự án và ngày làm việc cụ thể.
         Hệ thống xác thực thông tin, lưu lại bảng chấm công và cập nhật chi tiết thời gian làm việc của nhân viên.
         
   __c. Phân tích lớp__
   
       Các lớp phân tích chính:
          Employee (Nhân viên): Lớp trung tâm, chứa thông tin về nhân viên, gồm employeeID, thông tin thanh toán (paymentMethod) và chi tiết bảng chấm công (timecardDetails). Lớp này 
      giúp quản lý hồ sơ nhân viên một cách toàn diện.
          PayrollDatabase: Chứa tất cả thông tin payroll của nhân viên, bao gồm lịch sử thanh toán, thông tin về lương, và chi tiết bảng chấm công. Lớp này hỗ trợ việc truy xuất và cập 
       nhật dữ liệu payroll cho hai chức năng Select Payment và Maintain Timecard.
          TransactionHistory: Quản lý lịch sử các giao dịch thanh toán, lưu lại các chi tiết như ngày giao dịch, số tiền thanh toán và phương thức thanh toán.
          TimecardManager: Quản lý thông tin về bảng chấm công, cho phép nhân viên và hệ thống cập nhật chi tiết thời gian làm việc theo từng ngày và dự án cụ thể.
   Biểu đồ lớp tổng hợp:
     ![Diagram](https://planttext.com/api/plantuml/png/b5HBJiCm4Dtt55bI2IwG1IfG95WK8L69zIGUYga_aJr12eYJiU18N06diPsuiH1a4SNpUvbvR_pz-RMo18PQAHQr06kBQza8tI4MxukYVz2VRzTbyK26gzrWRw2Jg6Y3zAnPMTnFZqC4SOar6BP60YviMMozOV6ny619La2KXzEsQp15XBhMhQ9OxXBK_cAm-G3635hdkHW-Hfn9Q43nrUvQMQ59WIeNVGToX8zrVE5Gmv91f3IvvjIbbZVUN6cMgHRc4SezwzROHstsw0RAGrUDqIzOEvJxuMColS4GqdtWZAZ1d6_84M2q46iWgC16qdT8GGUtwacVp4MmBADIXfIsOK2O49f9E_rLDyk87aQJHuv2cY3_ad4QfJYcBYSq650MQk9QtN1BsdHX33Hwt8JS-Fgtbu_irLCMJBULm3-in8pr3IZOeObwPEpVBHmINq7mP02PoBAej1O8QhvwwLyuiTHEuDwPctvV8TuHPsVdHsqchiXJkkUzQxgySszOuBWX1o2l_sFDzhwenPnpJd0-BFpjCKFPLgQ-UVqLAjRVgJy0003__mC0)
     
   __d. Biểu đồ tuần tự hợp nhất__
   
   Biểu đồ tuần tự cho quy trình chọn phương thức thanh toán (Select Payment Method):
 ![Diagram](https://planttext.com/api/plantuml/png/R57DIWCn4BxdAOQUz23Uzo15wr5OB3x0c4nf8Cd4pAJGP_FGH-ehc2Mxe6jluSltoro_BrjHB5fZC6YL2xp67FXCP7A3lVKPay9cn7EazdWZFRA3FGMowZbj00N6ZlvJ50u1TgZuYKATkNisPac0XwT5Ei3BaLa8yfmJk-FyFJ4NrG3lz5L95D0vFtN003uT6EuQK4Za4QtbsamSAVeWzxSJny8dxsXjypkprHtW8plKTRD61JSlCutsTmkdWoyHQbTAjRRLkZrcuQxikzIPBIKttUO7003__mC0)
 
   Biểu đồ tuần tự cho quy trình duy trì bảng chấm công (Maintain Timecard):
  ![Diagram](https://planttext.com/api/plantuml/png/V95BRW8n38RtEON5dWkmG9J74WbLbBt9k2Lg7YF70N4s5Xo9A-0PIc4qj5ld_tv_IIwdyoGBifJW3Lf938jG-tGaChMEdNKrHe71sWMoo1KiCU8N1Oeo0ComdkdmDkCkiS8Z9-zXZe9RpDJ6L_EfCVSDC1nt-16yMKivW_miCy-dJLhn4RoJiACzWItCwl68wt6_K-E5OoyCbNhzexA8eZjtgN26G-9lwjjqWGrwfvrqOrwhVzHjujV1nLQZUPxNyhCKFns71r7QXbxx_Hv_4fMPKAoQNxu2003__mC0)
  
   __e. Mối quan hệ giữa các lớp__
    
       Employee: Tương tác với cả hai chức năng Select Payment Method và Maintain Timecard, giúp quản lý thông tin thanh toán và bảng chấm công của nhân viên.
       PayrollDatabase: Kết nối với các lớp TransactionHistory và TimecardManager để lưu trữ và quản lý các dữ liệu payroll của nhân viên.
       TransactionHistory: Lưu lịch sử giao dịch thanh toán, bao gồm ngày giao dịch, số tiền và phương thức thanh toán.
       TimecardManager: Quản lý thông tin về bảng chấm công, ghi lại chi tiết số giờ làm việc của nhân viên cho từng dự án và ngày làm việc.
        
