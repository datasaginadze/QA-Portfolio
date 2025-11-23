TEST SCENARIOS
---
Project: E-commerce - NDA Safe
========================================

VS-TS-1 - User Registration (Valid Flow)
Purpose: Confirm that a new customer can successfully create an account.
Preconditions: User is logged out.
Flow:
  1. User enters valid data (email, password, name).
  2. Submits the form.
Expected:
  • Account is created.
  • User becomes logged in automatically.

---

VS-TS-2 - User Registration (Invalid Email / Boundary)
Purpose: Validate email format and boundary limits.
Boundary Input Examples:
  • "a@a.c"
  • Very long email (e.g., 64+ characters before @)
Expected:
  • System rejects invalid email formats.
  • Appropriate validation error is shown.

---

VS-TS-3 - Login with Valid Credentials
Purpose: Verify successful authentication.
Expected:
  • User is redirected to the homepage.
  • User session starts correctly.

---

VS-TS-4 - Login with Invalid Credentials (Password Boundary)
Boundary Examples:
  • 1-character password
  • Overly long password (255–256 characters)
Expected:
  • System shows “Incorrect email or password.”
  • Repeated failures trigger security/brute-force protection.

---

VS-TS-5 - Product Filtering by Category
Purpose: Validate category browsing and filtering features.
Flow:
  1. User selects a category.
  2. Applies filters: price, size, brand.
Expected:
  • Correct filtered product list.
  • Pagination works reliably.

---

VS-TS-6 - Product Details Page Rendering
Purpose: Confirm product page elements load correctly.
Expected:
  • Image gallery works.
  • Product title, price, and variations display correctly.
  • “Add to Cart” button is functional.

---

VS-TS-7 - Add to Cart with Quantity (Boundary)
Boundary Inputs:
  • 0
  • 1
  • AvailableStock + 1
Expected:
  • 0 → rejected with validation.
  • 1 → added successfully.
  • Above stock → stock error message.

---

VS-TS-8 - Checkout Flow (Valid)
Purpose: Validate the complete purchase flow.
Steps:
  1. User adds item to cart.
  2. Enters delivery info.
  3. Selects payment method.
  4. Confirms order.
Expected:
  • Order is created.
  • Unique Order ID is generated.
  • Confirmation email is triggered.

---

VS-TS-9 - Checkout Validation (Invalid / Missing Fields)
Purpose: Ensure checkout form validation works.
Examples:
  • Missing name, phone, or address.
Expected:
  • Order is not submitted.
  • Clear validation messages appear.

---

VS-TS-10 - Viewing Order History
Purpose: Verify the order history functionality.
Expected:
  • Orders appear with correct status.
  • Pagination works.
  • “View Details” opens order info.

---

VS-TS-11 - Product Search (Boundary Inputs)
Boundary Inputs:
  • Empty search (“”)
  • 1-character input
  • 100-character keyword
Expected:
  • Empty → suggestions or an error message.
  • Long input → handled without performance or UI issues.

---

VS-TS-12 - Applying a Promo Code
Purpose: Verify discount code behavior.
Expected:
  • Valid → discount applied.
  • Expired → error message.
  • Usage limit exceeded → error shown.

---

VS-TS-13 - Payment Failure Simulation
Purpose: Confirm system behavior when payment fails.
Expected:
  • Payment gateway returns failure.
  • No order is created.
  • User sees clear error screen.

---

VS-TS-14 - Mobile / Desktop Responsive Behavior
Purpose: Validate multi-device consistency.
Expected:
  • Breakpoints work correctly.
  • No overlapping or broken UI elements.

---

VS-TS-15 - Wishlist Add/Remove
Purpose: Confirm wishlist feature functions correctly.
Expected:
  • Add → item appears in wishlist.
  • Remove → item disappears immediately.
