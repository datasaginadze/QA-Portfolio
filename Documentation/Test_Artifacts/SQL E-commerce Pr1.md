SQL Testing Artifacts - E-commerce Platform
---

VS-SQL-1: Verify total number of products in catalogue  

Purpose: ensure the products table is populated correctly  

SELECT COUNT(*)  
AS total_products  
FROM products;

-----------------------------------------------

VS-SQL-2: Fetch product details by product_id (Boundary Value Example)  

Boundary: users may enter product_id = 0, -1, 999999  

SELECT *  
FROM products  
WHERE product_id = 101;

-----------------------------------------------

VS-SQL-3: Validate product price range (detect incorrect pricing)  

SELECT product_id, name, price  
FROM products  
WHERE price <= 0 OR price > 10000;

-----------------------------------------------

VS-SQL-4: Verify users with unverified emails  

SELECT user_id, email, is_verified  
FROM users  
WHERE is_verified = FALSE;

-----------------------------------------------

VS-SQL-5: Get all orders for a specific user  

Boundary: user may enter user_id that does not exist  

SELECT order_id, user_id, order_status, total_amount  
FROM orders  
WHERE user_id = 15;

-----------------------------------------------

VS-SQL-6: Validate order totals by summing related order_items

       SELECT o.order_id, o.total_amount,
       SUM(oi.quantity * oi.unit_price) AS calculated_total  
       FROM orders o  
       JOIN order_items oi ON o.order_id = oi.order_id  
       GROUP BY o.order_id, o.total_amount  
       HAVING o.total_amount != SUM(oi.quantity * oi.unit_price);

-----------------------------------------------

VS-SQL-7: Verify inventory levels (detect negative stock)  

SELECT product_id, name, stock  
FROM products  
WHERE stock < 0;

-----------------------------------------------

VS-SQL-8: Check for duplicated emails in users table  

SELECT email, COUNT(*) AS cnt  
FROM users  
GROUP BY email  
HAVING COUNT(*) > 1;

-----------------------------------------------

VS-SQL-9: Fetch recent orders (last 7 days)  

SELECT order_id, user_id, created_at  
FROM orders  
WHERE created_at >= NOW() - INTERVAL '7 days';

-----------------------------------------------

-- VS-SQL-10: Verify expired discount code  
SELECT code, discount_value, expires_at  
FROM discount_codes  
WHERE expires_at < CURRENT_DATE;
