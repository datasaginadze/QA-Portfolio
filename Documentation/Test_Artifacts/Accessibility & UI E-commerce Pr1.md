# Accessibility & UI Review - E-commerce Platform
---

## VS-A11Y-1 - Color Contrast Audit (WCAG 2.1 AA)
**Area:** Product Page – Price Text  
**Issue:** Price (#8E8E8E) over white background fails WCAG contrast ratio.  
**Expected:** Minimum 4.5:1 for normal text.  
**Impact:** Users with low vision may not distinguish regular vs discounted price.  
**Recommendation:** Darken text color to #4A4A4A or use bold-weight variant.  

---

## VS-A11Y-2 - Missing Alt Text on Product Thumbnails
**Area:** Product Listing Grid  
**Issue:** `<img>` elements missing `alt` attributes.  
**Expected:** Informative alt text describing product.  
**Impact:** Screen readers cannot identify items.  
**Recommendation:** Auto-generate alt text from product title.  

---

## VS-A11Y-3 - Button Focus Not Visible
**Area:** Add to Cart Buttons  
**Issue:** Keyboard focus outline removed via CSS (`outline: none`).  
**Expected:** Clear 3:1 contrast around focused element.  
**Impact:** Keyboard-only users can’t track movement.  
**Recommendation:** Restore default outline or apply custom high-contrast style.  

---

## VS-A11Y-4 - Low Tap Target Size on Mobile
**Area:** Header Icons (Cart, Profile, Wishlist)  
**Issue:** Tap targets < 44x44 px (Apple HIG & WCAG Guidance).  
**Impact:** Users on small screens may tap the wrong icon.  
**Recommendation:** Increase padding + extend hitbox.  

---

## VS-A11Y-5 - Form Labels Missing Association
**Area:** Checkout → Shipping Information  
**Issue:** Labels not connected to inputs via `for=""` and `id=""`.  
**Impact:** Screen reader users skip required fields without context.  
**Recommendation:** Add programmatic label-binding.  

---

## VS-A11Y-6 - Insufficient Error Message Description
**Area:** Login Form  
**Issue:** Only a red border indicates an error; no textual explanation.  
**Expected:** Error must be described by helper text + announced by screen readers.  
**Recommendation:** Add ARIA roles (`aria-live="assertive"`).  

---

## VS-A11Y-7 - Carousel Not Keyboard Accessible
**Area:** Home Page Banner Slider  
**Issue:** Arrow controls cannot be reached via Tab.  
**Expected:** Full keyboard operability per WCAG 2.1.  
**Recommendation:** Make arrows focusable + add keyboard event handlers.  

---

## VS-A11Y-8 - Dynamic Content Not Announced
**Area:** Cart Popup ("Item Added")  
**Issue:** The Modal appears visually but is not announced for screen readers.  
**Expected:** ARIA live regions or modal dialog roles.  
**Recommendation:** Wrap popup inside a `role="dialog"` with focus trap.  

---

## VS-A11Y-9 - Headings Hierarchy Not Logical
**Area:** Category Page  
**Issue:** H4 used above H2; visual hierarchy doesn’t match semantic hierarchy.  
**Impact:** Screen reader users receive content in the wrong order.  
**Recommendation:** Refactor to follow descending order (H1 → H2 → H3…).  

---

## VS-A11Y-10 - Link Text Not Descriptive
**Area:** Footer  
**Issue:** Many links use “Learn more”, “See more”, “Click here”.  
**Expected:** Link text must explain the destination.  
**Recommendation:** Rename to descriptive variants (“Shipping Policy”, “Privacy Overview”).  

---

![NDA Warning](https://img.shields.io/badge/NDA-Restricted-red?style=for-the-badge")

Due to NDA restrictions, screenshots and visual materials from the E-commerce platform cannot be shared.
