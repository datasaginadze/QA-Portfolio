## SMOKE

### VS-CL-001 - Smoke Checklist

| # | Check Item | Status |
|---|------------|--------|
| 1 | Homepage loads without errors | ☐ |
| 2 | User can open Login page | ☐ |
| 3 | User can Login with valid credentials | ☐ |
| 4 | Search bar is visible and functional | ☐ |
| 5 | Product page opens successfully | ☐ |
| 6 | Add to Cart button works | ☐ |
| 7 | Cart page opens | ☐ |
| 8 | Checkout opens | ☐ |
| 9 | Order placement (COD) works | ☐ |
|10 | Logout works | ☐ |

## SANITY

### VS-CL-002 - Sanity Checklist (Post-fix)

| # | Check Item | Status |
|---|------------|--------|
| 1 | Fixed module loads without errors | ☐ |
| 2 | Main function affected by fix works | ☐ |
| 3 | Related UI elements display correctly | ☐ |
| 4 | No duplicate items appear | ☐ |
| 5 | Cart calculations remain correct | ☐ |
| 6 | Checkout still processes orders | ☐ |
| 7 | Login/Session unaffected | ☐ |


##FUNCTIONAL

### VS-CL-003 - Functional Checklist  
**Modules covered:** Auth, Search, Product, Cart, Checkout, Orders

| # | Functional Area | Check Item | Status |
|---|----------------|------------|--------|
| 1 | Login | Valid credentials allow login | ☐ |
| 2 | Login | Invalid credentials show error | ☐ |
| 3 | Registration | Email validation works | ☐ |
| 4 | Search | Search by keyword works | ☐ |
| 5 | Search | No-result case handled correctly | ☐ |
| 6 | PDP | Product images visible | ☐ |
| 7 | PDP | Variant selection required | ☐ |
| 8 | Cart | Add/remove/update quantity works | ☐ |
| 9 | Cart | Price × quantity = correct total | ☐ |
|10 | Checkout | Address validation works | ☐ |
|11 | Checkout | Promo code validation | ☐ |
|12 | Checkout | Payment method selection | ☐ |
|13 | Order | Order creation successful | ☐ |
|14 | Order History | User sees list of past orders | ☐ |
|15 | Profile | User can update account info | ☐ |

## REGRESSION

### VS-CL-004 - Regression Checklist  
**Covers all critical flows**

| # | Module | Check Item | Status |
|---|--------|------------|--------|
| 1 | Auth | Login/Logout cycle | ☐ |
| 2 | Auth | Registration | ☐ |
| 3 | Search | Search with filters | ☐ |
| 4 | Search | Sorting (Price Low→High) | ☐ |
| 5 | PDP | Variant selection and Add to Cart | ☐ |
| 6 | PDP | Gallery images zoom/slider | ☐ |
| 7 | Cart | Quantity change with limit checks | ☐ |
| 8 | Cart | Removing product | ☐ |
| 9 | Checkout | Shipping form validation | ☐ |
|10 | Checkout | Promo code logic | ☐ |
|11 | Payment | Card validation + expiration check | ☐ |
|12 | Orders | Order confirmation email sent | ☐ |
|13 | Orders | Cancel order (if available) | ☐ |
|14 | Profile | Change password | ☐ |
|15 | Profile | Update address | ☐ |
|16 | UI | Header/Footer responsive | ☐ |
|17 | UI | Category navigation | ☐ |
|18 | System | 404 page loads | ☐ |

## UI / UX

### VS-CL-005 - UI/UX Checklist

| # | Area | Check Item | Status |
|---|------|------------|--------|
| 1 | Layout | All pages aligned consistently | ☐ |
| 2 | Colors | Brand colors match design | ☐ |
| 3 | Fonts | Font size + spacing consistent | ☐ |
| 4 | Buttons | Clear label + correct state (hover/active/disabled) | ☐ |
| 5 | Inputs | Error messages readable and placed correctly | ☐ |
| 6 | Images | Product images not stretched | ☐ |
| 7 | Mobile | Navigation works on mobile | ☐ |
| 8 | Responsiveness | Breakpoints work (320, 375, 768, 1024) | ☐ |
| 9 | Navigation | Breadcrumbs work | ☐ |
|10 | Checkout UX | Required fields visually clear | ☐ |
|11 | PDP UX | Variant buttons clear and clickable | ☐ |
|12 | Cart UX | Totals visible and always updated | ☐ |
|13 | Search UX | Suggestions appear quickly | ☐ |
|14 | Accessibility | Links have proper focus states | ☐ |

## ACCESSIBILITY

### VS-CL-006 - Accessibility Checklist  
( WCAG AA standards )

| # | Standard | Check Item | Status |
|---|----------|------------|--------|
| 1 | ALT text | Product images have ALT attributes | ☐ |
| 2 | Keyboard | Full navigation works with TAB | ☐ |
| 3 | Screen Reader | Buttons have aria-label | ☐ |
| 4 | Color Contrast | Text contrast ≥ 4.5:1 | ☐ |
| 5 | Forms | Required fields marked for screen reader | ☐ |
| 6 | Focus | Clear visible focus states | ☐ |
| 7 | Errors | Validation messages read by screen reader | ☐ |
| 8 | Headings | H1-H2-H3 order logical | ☐ |
| 9 | Links | Descriptive link labels | ☐ |
|10 | Live Regions | Toast messages announced via aria-live | ☐ |
|11 | Images | Decorative images marked role="presentation" | ☐ |
|12 | Mobile | WCAG touch target size ≥ 44px | ☐ |
|13 | Checkout | Labels correctly linked with inputs | ☐ |
|14 | Popup | Modal can close via ESC | ☐ |
|15 | Icons | Icons have accessible names | ☐ |
