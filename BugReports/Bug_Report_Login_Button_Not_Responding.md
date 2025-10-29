# 🐞 Bug Report: Login Button Not Responding

### Summary

The **Login** button on the web application does not respond when clicked.
The issue prevents users from accessing their accounts after entering valid credentials.

### Environment

* **Platform:** Web
* **Browser:** Google Chrome 129.0
* **OS:** Windows 11
* **Build Version:** v1.4.3 (Staging)

### Severity / Priority

* **Severity:** Major
* **Priority:** High

### Precondition

User is on the login page with a registered account.

### Steps to Reproduce

1. Navigate to the login page
2. Enter a valid email and password
3. Click the “Login” button

### Expected Result

User should be redirected to the dashboard after successful login.

### Actual Result

Nothing happens after clicking the “Login” button.
No error message is displayed.

### Screenshot

![Login Button Bug Screenshot](./Screenshots/LoginError.png)

### Additional Notes

The issue occurs consistently across Chrome and Edge. Works fine on mobile.
The potential cause may be related to the button event listener not triggering properly.
