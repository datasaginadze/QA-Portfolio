## Test Artifacts

This section contains additional technical QA materials created during testing activities for an NDA-protected e-commerce platform.  
All examples are representative and anonymized. They reflect the testing approach, tooling proficiency, and documentation quality demonstrated during the project.

### API Testing
This folder includes:
• REST API request/response samples  
• Positive and negative test examples  
• Environment variables setup  
• Boundary testing for endpoints  
• Authentication and error-handling checks  

Each example is presented in Postman-style format, including:
– Endpoint under test  
– Method (GET/POST/PUT/DELETE)  
– Request body (if applicable)  
– Expected response  
– Actual response sample  
– Assertions and verification steps  

File examples:
• VS-API-1_GetProductDetails.md  
• VS-API-2_SearchProducts_InvalidQuery.md  
• VS-API-3_AddToCart_ValidRequest.md  
• VS-API-4_AddToCart_StockBoundary.md  
• VS-API-5_Checkout_CreateOrder.md  
• VS-API-6_Checkout_InvalidPayment.md  
• VS-API-7_GetOrderHistory_AuthRequired.md  
• VS-API-8_UpdateUserProfile.md  
• VS-API-9_ApplyPromoCode.md  
• VS-API-10_ValidateStockLevels.md  


### SQL Queries
This folder contains SQL queries used to validate data integrity, user flows, and backend consistency.  
All queries follow safe, anonymized structures.

Common uses:
• Checking user creation in the database  
• Validating order records after checkout  
• Verifying product stock levels  
• Filtering orders by status  
• Boundary testing with long/empty inputs  

File examples:
• VS-SQL-1_VerifyUserCreation.sql  
• VS-SQL-2_ValidateLoginEmailExists.sql  
• VS-SQL-3_GetProductsByCategory.sql  
• VS-SQL-4_CheckStockBeforeOrder.sql  
• VS-SQL-5_ConfirmOrderSaved.sql  
• VS-SQL-6_GetOrderDetailsByID.sql  
• VS-SQL-7_FilterOrdersByStatus.sql  
• VS-SQL-8_SearchProductKeywordBoundary.sql  
• VS-SQL-9_CheckPromoUsageLimit.sql  
• VS-SQL-10_ValidateUpdatedProfileData.sql  


### Accessibility & UI Review
This folder contains findings from UI, UX, and accessibility evaluations performed on the e-commerce platform.

Coverage:
• Color contrast and WCAG compliance  
• Tap-target sizing on mobile  
• Keyboard navigation support  
• ARIA labels and alternative text validation  
• Layout consistency across responsive breakpoints  
• Visual defects and UI mismatches (design vs. production)  

Each artifact contains:
– Observed issue  
– Expected behavior  
– Severity  
– Affected platform (Web / Mobile)  
– Screenshot (placeholder until added)  

File examples:
• VS-ACC-1_ColorContrast_Issue.md  
• VS-ACC-2_MissingAltText_ProductImage.md  
• VS-ACC-3_ButtonTapTarget_Mobile.md  
• VS-ACC-4_FocusIndicator_Missing.md  
• VS-ACC-5_HeadingHierarchy.md  
• VS-ACC-6_FormErrorAccessibility.md  
• VS-ACC-7_KeyboardNavigation_Issue.md  
• VS-ACC-8_ResponsiveLayout_Header.md  
• VS-ACC-9_ProductCard_AlignmentIssue.md  
• VS-ACC-10_CheckoutForm_Contrast.md  

---

These artifacts collectively demonstrate technical depth and real-world QA practice across API, database, accessibility, and UI/UX testing.

