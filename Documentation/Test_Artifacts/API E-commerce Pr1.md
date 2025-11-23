# API Testing Artifacts - E-commerce Platform
All endpoints and payloads are fictional and anonymized for NDA protection.  
Base URL is masked intentionally.

---

## VS-API-1 - Get Product List
**Method:** GET  
**Endpoint:** `/api/v1/products?limit=20&page=1`

**Purpose:** Fetch paginated product catalog.

**Validations:**
- Response code = 200  
- `data` → array  
- Each item contains: id, title, price, image, in_stock  

**Expected Response Example:**
{
  "success": true,
  "data": [
    { "id": 101, "title": "Running Shoes", "price": 129.90, "in_stock": true }
  ]
}

---

## VS-API-2 - Get Product Details (Boundary Test)
**Method:** GET  
**Endpoint:** `/api/v1/products/{product_id}`

**Boundary IDs Tested:**
- Minimum existing ID → 1  
- Maximum existing ID → 9999  
- Out-of-range ID → 10000 (should return 404)

**Expected Failure Response (404):**
{
  "success": false,
  "error": "Product not found"
}

---

## VS-API-3 - Search Products
**Method:** GET  
**Endpoint:** `/api/v1/products/search?q=iphone`

**Checks:**
- 200 OK  
- Only relevant items returned  
- SQL Injection prevention test:  
  Query: `q=iphone' OR '1'='1` → Expected 400  

**Expected Response (Injection Safe):**
{
  "success": false,
  "error": "Invalid search query"
}

---

## VS-API-4 - User Registration
**Method:** POST  
**Endpoint:** `/api/v1/auth/register`

**Payload:**
{
  "email": "test@example.com",
  "password": "Test12345!",
  "full_name": "John Doe"
}

**Validations:**
- 201 Created  
- Token returned  
- Email uniqueness check (duplicate returns 409)

**Expected Conflict Error:**
{
  "success": false,
  "error": "Email already exists"
}

---

## VS-API-5 - Login
**Method:** POST  
**Endpoint:** `/api/v1/auth/login`

**Payload Variants Tested:**
- Valid credentials → 200  
- Wrong password → 401  
- Account not verified → 403  
- Missing fields → 400  

**Expected Success:**
{
  "token": "JWT_TOKEN_EXAMPLE"
}

---

## VS-API-6 - Add Item to Cart
**Method:** POST  
**Endpoint:** `/api/v1/cart/add`

**Payload:**
{
  "product_id": 2001,
  "quantity": 2
}

**Validations:**
- Requires authentication  
- Stock check  
- Max limit test: quantity > 20 → return 400  

**Expected Failure Example:**
{
  "success": false,
  "error": "Quantity exceeds allowed limit"
}

---

## VS-API-7 - View Cart
**Method:** GET  
**Endpoint:** `/api/v1/cart`

**Checks:**
- 200 OK  
- Correct subtotal  
- Currency formatting  
- Empty cart edge case  

**Expected Empty Example:**
{
  "items": [],
  "subtotal": 0.00
}

---

## VS-API-8 - Apply Promo Code
**Method:** POST  
**Endpoint:** `/api/v1/cart/promo/apply`

**Payload:**
{
  "code": "WELCOME10"
}

**Checks:**
- Invalid code → 404  
- Expired code → 410  
- Already used → 409  

**Expected Success:**
{
  "promo": "WELCOME10",
  "discount": 10
}

---

## VS-API-9 - Create Order
**Method:** POST  
**Endpoint:** `/api/v1/orders`

**Payload:**
{
  "address_id": 501,
  "payment_method": "card"
}

**Checks:**
- Returns unique order_id  
- Stock re-validation  
- Payment validation  
- DB value matches UI summary  

**Expected Response:**
{
  "order_id": "EC-012345",
  "status": "processing"
}

---

## VS-API-10 - Get Order History
**Method:** GET  
**Endpoint:** `/api/v1/orders/history`

**Validations:**
- 200 OK  
- Sorted by date DESC  
- Pagination supported  
- Required fields: id, total, items_count, status, created_at  

**Expected Example:**
{
  "orders": [
    { "id": "EC-111", "total": 209.90, "items_count": 3 }
  ]
}
