# Lab 6
__1. Authentication Subsystem__

    - Lớp thiết kế : LoginForm (Boundary)
        + Thuộc tính:
            username: String
            password: String
        + Phương thức:
            submitLogin(): void
          
     - Lớp thiết kế : AuthenticationSystem (Control)
        + Thuộc tính:
            activeSession: Session
        + Phương thức:
            validateCredentials(username: String, password: String): Boolean
            createSession(userID: String): Session
            endSession(sessionID: String): void
            
      - Lớp thiết kế : UserDatabase (Entity)
        + Thuộc tính:
            users: List<User>
        + Phương thức:
            getUser(username: String): User
            saveUser(user: User): void
            
__2. Maintain Timecard Subsystem__

    - Lớp thiết kế : TimecardController (Control)
        + Thuộc tính:
            timecards: List<Timecard>
        + Phương thức:
            createTimecard(employeeID: String, date: Date): Timecard
            updateTimecard(timecard: Timecard): void
            submitTimecard(timecardID: String): void
     - Lớp thiết kế : Timecard (Entity)
        + Thuộc tính:
            timecardID: String
            employeeID: String
            date: Date
            workHours: Map<ProjectID, Float>
            status: String (e.g., "draft", "submitted")
        + Phương thức:
            calculateTotalHours(): Float
            
    - Lớp thiết kế : ProjectManagementDatabase (Entity)
        + Thuộc tính:
            projects: List<Project>
        + Phương thức:
            getProjectCodes(): List<String>
            
3. Payroll Processing Subsystem
   
       - Lớp thiết kế : PayrollController (Control)
          + Thuộc tính:
              payrolls: List<Paycheck>
          + Phương thức:
              calculatePayroll(timecard: Timecard, employee: Employee): Paycheck
              processPayroll(employeeID: String): void
       - Lớp thiết kế : Paycheck (Entity)       
          + Thuộc tính:
              paycheckID: String
              employeeID: String
              amount: Float
              issueDate: Date
          + Phương thức:
              generatePayStub(): String
       - Lớp thiết kế : PayrollDatabase (Entity)
          + Thuộc tính:
              payrollRecords: List<Paycheck>
          + Phương thức:
              savePaycheck(paycheck: Paycheck): void
       - Lớp thiết kế : BankSystemProxy (Boundary)
          + Thuộc tính:
              bankDetails: BankInformation
          + Phương thức:
              transferSalary(paycheck: Paycheck): Boolean
