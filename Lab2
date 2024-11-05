#Lab2
1. Phân tích ca sử dụng Create Adminnistrative Report
  a. Xác định các lớp phân tích cho ca sử dụng Create Adminnistrative Report
     - Các lớp phân tích chính cho ca sử dụng này bao gồm:
       + Payroll Administrator: Đại diện cho người quản lý hệ thống Payroll. Đây là người có quyền truy cập vào các chức năng báo cáo và các tính năng hành chính.
       + Report Generator: Lớp chịu trách nhiệm tổng hợp và xây dựng báo cáo dựa trên các yêu cầu từ Payroll Administrator.
       + Employee Data: Lớp đại diện cho dữ liệu của nhân viên (chứa thông tin cá nhân, giờ làm việc, doanh số bán hàng, phương thức thanh toán, v.v.), phục vụ cho quá trình tạo báo cáo.
       + Project Management Database Interface: Lớp trung gian cho phép hệ thống Payroll truy cập dữ liệu liên quan đến các dự án từ Project Management Database mà không thay đổi dữ liệu này.
       + Report: Lớp đại diện cho đối tượng báo cáo được tạo ra, bao gồm dữ liệu cần thiết để Payroll Administrator xem xét.
  b. Mô tả được hành vi thông qua biểu đồ sequence
     ![Diagram](https://planttext.com/api/plantuml/png/X5F1Qjj04BthAmQV4aX-m8U0KnbXIa2uCVIwMK-aBT9AMOrCVCofXvvywAcKEeHIQ0av5hI779GVsI_eBsHNacChDUIoX-6zDs_cpVxJZoGeGVY0LoLAZk0B5YcMmcMcOF1E8IE4qJmLKXIa68a5mXJpJD70ynWdYmhPKcL9iWEoHLP0EF9ofaXmaJD9C9WLg60Y2TKbupXmaDca3scL8K29ZKm3cWPzq3ZDaso9rYeZrY36VXyHgkmJSeApA2NmJryr3S_yqtrjssQU5uxW-CHQ6yBxsEWV0iXKjnaiwzybS5FzAj_QospY1AR140AZxyKkivMwgEt3xUDDWmtqOttBuMbbz1SPmzpe1qY4qPzReWIAXQaU2Gx8wAyoWiBe5KGMyHsIUfqUGLVdiVMhJ7Lt1FECMQa6Q1jAYEkrZ0wxbcD_2EUgNC9rQQgV1FjbOL6l_rDsXJ_GIy4R-t3S3NBUO1P6t_J6U2NwejRvSQ7q7UsITqPfchy4p2IBC4KRehDnmGhSXkqvpRTixLtI9XRBwkVb-Dz4J-1fLTkDn3RQs5JtUKFjpgTDVqjkeKwnEH4tzMYu-JxG_p_Nc4AScUelTumxuRQYLpQ6xUqy0m00__y30000)
  c. xác định được nhiệm vụ của từng lớp phân tích
       + Payroll Administrator: Khởi tạo yêu cầu báo cáo, xem báo cáo.
       + Report Generator: Xử lý yêu cầu tạo báo cáo từ Payroll Administrator, truy xuất dữ liệu từ các nguồn liên quan và tổng hợp dữ liệu để xây dựng báo cáo.
       + Employee Data: Cung cấp thông tin liên quan đến nhân viên, bao gồm giờ làm, thông tin chi trả, và các dữ liệu cá nhân khác.
       + Project Management Database Interface: Cung cấp thông tin về các dự án và số giờ làm theo từng mã chi phí từ Project Management Database.
       + Report: Chứa dữ liệu báo cáo hoàn chỉnh và được trả về cho Payroll Administrator.
  d. xác định một số thuộc tính và quan hệ giữa các lớp phân tích
       + Payroll Administrator
          - Thuộc tính: ID, Name, Role
          - Quan hệ: Tương tác với lớp Report Generator để yêu cầu tạo báo cáo.
       + Report Generator
          - Thuộc tính: Report Type, Date Range
          - Quan hệ: Truy cập lớp Employee Data và Project Management Database Interface để thu thập dữ liệu cần thiết cho báo cáo.
       + Employee Data
          - Thuộc tính: EmployeeID, HoursWorked, Salary
          - Quan hệ: Cung cấp dữ liệu giờ làm và chi trả cho Report Generator.
       + Project Management Database Interface
          - Thuộc tính: ProjectID, Charge Code
          - Quan hệ: Cung cấp dữ liệu về dự án và mã chi phí cho Report Generator.
       + Report
          - Thuộc tính: ReportID, Data, DateGenerated
          - Quan hệ: Được tạo từ Report Generator và trả về để Payroll Administrator có thể xem hoặc tải xuống.
       + Mối quan hệ chính giữa các lớp:
          - Payroll Administrator có quyền yêu cầu tạo báo cáo thông qua Report Generator.
          - Report Generator phụ thuộc vào dữ liệu từ Employee Data và Project Management Database Interface để hoàn tất việc tạo báo cáo.
          - Report là kết quả chứa thông tin tổng hợp, được trả lại cho Payroll Administrator.
    e. Biểu đồ mô tả lớp phân tích
        ![Diagram](https://planttext.com/api/plantuml/png/Z5D1JiCm4Bpd5LPF894FH5LLH05L0bGL9CvBigG1nuxMRgi8yJ8EF8alODSsn6w4o2NnxCxkU7RpzV4vLnf8RrkUPIK7fTWAUfASdrTj8ngb2RGazfOn-omN1RlNr8ZQdU-WnHXPIvuW9I5eN6CdIP_GuVNGTpz9PwooOH2rWHRXyxHWZf6z1rtkV8q28qd75Hq-LjL5QbSYI1ffTTbsNFQ8XWYX3teijM0ZjwGU9RrYLR0hBa4xN047wYEeHZsiR3lV68UdGt3sgs95yWLBVGi2QcnHQ1j_0eLBeP6UeSIWhNEPgRHo0rJZXQmIQumENpkICS1cgUsnssaZupKSk-z7PNsn4_21HdKSUjjq9vlAWt8lZ4tL3sgwZwvXdi-Ezg1W4xTYogkRP6cAfKKpDHn28nTtXXKcUxZ6EFaVeuXA-e7yKT7RQbXX7TLa_CxJF1zaxnhSAsRWu9cXPNCKbVs3lm400F__0m00)
2. Phân tích ca sử dụng Create Employ Report
  a. Xác định các lớp phân tích cho ca sử dụng Create Employ Report
       + Employee: Là người dùng hệ thống yêu cầu tạo báo cáo của chính họ.
       + Employee Report Generator: Lớp chịu trách nhiệm thu thập và tổng hợp dữ liệu cần thiết để tạo báo cáo cho nhân viên.
       + Employee Data: Lưu trữ thông tin liên quan đến nhân viên như ID, giờ làm việc, lương, thông tin doanh số, v.v.
       + Project Management Database Interface: Cung cấp thông tin dự án và mã chi phí để phục vụ việc phân tích chi phí theo giờ làm việc của nhân viên.
       + Employee Report: Báo cáo cuối cùng chứa dữ liệu giờ làm, tổng chi trả, và các thông tin liên quan, được trả về cho nhân viên.
  b. Mô tả được hành vi thông qua biểu đồ sequence
    ![Diagram](https://planttext.com/api/plantuml/png/Z951ReD034NtdCBBLaela4KtJLLrKIdA3Lpc0zE2XnfJnDcww95wXGA1Y4WaPEUPRp__B__z_EvPpSU-P35wBieyj42qz7b06THU852se8izEpO-4_OQFX3R6mkdA23MTxnpXLSnQCBnjLrHDBtfuV6IZoqTy5MZCdfIiE7KHoFamjnLv0wTky8BI0U9h2r1B8vSvv-K9SKju3vjRz3KunkKXLehQe9-mcseufortGpOhaOrmAFvx4fkgrK8KzwpwGLJwxUOMIsFpOEvE6DDGN5m82z9q8BD1w4xdv003ku-MeVVacNQkXRbNDhIA9xErNZBklgOnItXvfJkthugSswfexlGI1xOKJeotGYD_W400F__0m00)
  c. xác định được nhiệm vụ của từng lớp phân tích

  d. xác định một số thuộc tính và quan hệ giữa các lớp phân tích
  e. Biểu đồ mô tả lớp phân tích.
3. Phân tích ca sử dụng Login
 a. Xác định các lớp phân tích cho ca sử dụng Login
  b. Mô tả được hành vi thông qua biểu đồ sequence
  c. xác định được nhiệm vụ của từng lớp phân tích
  d. xác định một số thuộc tính và quan hệ giữa các lớp phân tích
  e. Kết quả mong đợi là các biểu đồ lớp mô tả lớp phân tích và giải thích.
4. Phân tích ca sử dụng Maintain Employee Information
5. Phân tích ca sử dụng Maintain Purchase Order
6. Phân tích ca sử dụng Run Payroll
7. Viết code Java mô phỏng ca sử dụng Maintain Timecard.

