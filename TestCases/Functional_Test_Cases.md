# Functional Test Cases

This section contains anonymized examples of **functional test cases**, focused on validating core features and user workflows.
All examples are generalized to protect project confidentiality (NDA compliant).

---

### **Feature: User Authentication**

| ID      | Test Case Description                                      | Preconditions       | Test Steps                                                                          | Expected Result                                          | Status |
| ------- | ---------------------------------------------------------- | ------------------- | ----------------------------------------------------------------------------------- | -------------------------------------------------------- | ------ |
| TC-F001 | Verify user can log in with valid credentials              | User account exists | 1. Open login page<br>2. Enter valid email and password<br>3. Click “Login”         | User successfully logs in and is redirected to dashboard | Passed |
| TC-F002 | Verify error message for invalid password                  | User account exists | 1. Open login page<br>2. Enter valid email and invalid password<br>3. Click “Login” | “Invalid credentials” message displayed                  | Passed |
| TC-F003 | Verify login button remains disabled when fields are empty | None                | 1. Open login page<br>2. Leave all fields blank<br>3. Try to click “Login”          | Login button inactive or validation message shown        | Passed |

---

### **Feature: Registration Form**

| ID      | Test Case Description                                         | Preconditions                    | Test Steps                                                                                              | Expected Result                                              | Status |
| ------- | ------------------------------------------------------------- | -------------------------------- | ------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ | ------ |
| TC-F004 | Verify user can register with valid data                      | None                             | 1. Open registration page<br>2. Fill in all required fields with valid data<br>3. Click “Register”      | Account created successfully; confirmation message displayed | Passed |
| TC-F005 | Verify system prevents duplicate registration with same email | Existing account with same email | 1. Open registration page<br>2. Enter existing email<br>3. Fill in other details<br>4. Click “Register” | Error message displayed: “Email already exists”              | Passed |
| TC-F006 | Verify mandatory field validation                             | None                             | 1. Open registration page<br>2. Leave required fields blank<br>3. Click “Register”                      | Validation errors displayed for each mandatory field         | Passed |

---

### **Feature: Password Reset**

| ID      | Test Case Description                               | Preconditions       | Test Steps                                                                         | Expected Result                                  | Status |
| ------- | --------------------------------------------------- | ------------------- | ---------------------------------------------------------------------------------- | ------------------------------------------------ | ------ |
| TC-F007 | Verify password reset link sent to registered email | User account exists | 1. Open “Forgot Password” page<br>2. Enter registered email<br>3. Click “Submit”   | Confirmation message displayed; reset email sent | Passed |
| TC-F008 | Verify error for unregistered email                 | None                | 1. Open “Forgot Password” page<br>2. Enter unregistered email<br>3. Click “Submit” | Error message displayed: “Email not found”       | Passed |

---

🧩 *Note:*
All test data and project names are anonymized to comply with NDA policies. Each test case follows best practices: clear objectives, defined preconditions, structured steps, and verifiable expected results.
