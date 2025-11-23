### VS-BR-001 - Search field accepts 0-length input
**Module:** Search  
**Severity:** Medium  
**Environment:** STAGE  
**Precondition:** User is on Catalog page  

**Steps to Reproduce:**  
1. Click on search bar  
2. Leave input empty  
3. Press ENTER  

**Expected Result:**  
System should request at least 1 non-whitespace character.

**Actual Result:**  
Empty query is sent to backend. Page reloads with no feedback.

**Risk:** Search endpoint unnecessarily loads DB, no validation.

------------------------------------
### VS-BR-002 - Search field accepts 256+ characters (should be max 100)
**Module:** Search  
**Severity:** High  

**Steps:**  
1. Enter 260 characters in search box  
2. Press Enter  

**Expected:**  
Input length limit (100 chars).  

**Actual:**  
System sends long query to backend → search hangs for ~4 sec.

------------------------------------
### VS-BR-003 - Quantity field accepts negative values
**Module:** Cart  
**Severity:** Critical  

**Steps:**  
1. Open Cart  
2. Type “-5” into quantity input  
3. Update  

**Expected:**  
Min boundary = 1  

**Actual:**  
Value “-5” is accepted; subtotal becomes negative.

------------------------------------
### VS-BR-004 - Quantity field accepts 99999+ units
**Module:** Cart  
**Severity:** High  

**Steps:**  
1. Enter “99999” quantity  
2. Update  

**Expected:**  
Max boundary should be ≤ 100 units.

**Actual:**  
System accepts, subtotal overflows to scientific notation.

------------------------------------
### VS-BR-005 - Postal code accepts letters and emojis
**Module:** Checkout  
**Severity:** Medium  

**Steps:**  
1. On Checkout, enter postal code “AB12D”  
2. Save  

**Expected:**  
Postal code should accept digits only, min 4 max 6.

**Actual:**  
System accepts mixed characters.

**Boundary Inputs:**  
- "123" (too short → should fail)  
- "12345" (valid)  
- "ABC12" (invalid)  
- "11D1" (invalid)  

------------------------------------
### VS-BR-006 - Promo Code field accepts unlimited characters
**Module:** Checkout → Promo Code  
**Severity:** Low  

**Steps:**  
1. Type 200 characters in promo field  
2. Apply  

**Expected:**  
Length ≤ 20  

**Actual:**  
Field accepts >500 characters; backend trims silently.

------------------------------------
### VS-BR-007 - Email field allows missing “@”
**Module:** Registration  
**Severity:** High  

**Steps:**  
1. Enter email “testexample.com”  
2. Sign Up  

**Expected:**  
Validation error.

**Actual:**  
Form proceeds to next step.

**Bad Inputs:**  
- "example.com"  
- "test@"  
- "@mail.com"  
- "test"  

------------------------------------
### VS-BR-008 - Password field accepts only spaces
**Module:** Registration → Password  
**Severity:** High  

**Steps:**  
1. Enter "        " (8 spaces)  
2. Submit  

**Expected:**  
Whitespace-only strings rejected.

**Actual:**  
System validates based on length only.

------------------------------------
### VS-BR-009 - Product page: Add to Cart works without selecting variant
**Module:** PDP (Product Details Page)  
**Severity:** Critical  

**Steps:**  
1. Open variable-type product  
2. Without choosing size/color, click Add to Cart  

**Expected:**  
System requires variant.

**Actual:**  
System adds default variant silently (variantID=0).

------------------------------------
### VS-BR-010 - Payment form accepts expired card dates
**Module:** Payment Gateway (Sandbox)  
**Severity:** High  

**Steps:**  
1. Use card with MM/YY = 01/21  
2. Submit  

**Expected:**  
Expiration date < current date → reject.

**Actual:**  
Payment gateway accepts.

------------------------------------
