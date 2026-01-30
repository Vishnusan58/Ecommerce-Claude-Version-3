# DEFECT LOG

## ECommerce Platform - Defect Tracking Log

**Project:** ECommerce Platform v3.0
**Document Version:** 1.0
**Last Updated:** January 30, 2026
**Prepared By:** QA Team

---

## Defect Summary

| Severity | Count |
|----------|-------|
| Critical | 1 |
| High | 3 |
| Medium | 4 |
| Low | 2 |
| **Total** | **10** |

---

## Defect Log Table

| Defect ID | Description | Steps to Reproduce | Actual Result | Expected Result | Severity | Priority | Raised By | Date | Assigned To | Root Cause | Fix | Status |
|-----------|-------------|-------------------|---------------|-----------------|----------|----------|-----------|------|-------------|------------|-----|--------|
| DEF-001 | Cart total not updating after coupon application | 1. Login as customer 2. Add products to cart 3. Apply valid coupon code "SAVE20" 4. Observe cart total | Cart total remains unchanged after coupon is applied successfully | Cart total should decrease by the coupon discount amount (20%) | High | P1 | Jessica Williams | 2026-01-15 | Michael Chen | Frontend state not refreshing after API call success; missing subscription to coupon service observable | Updated CartComponent to subscribe to coupon application response and refresh total calculation | Closed |
| DEF-002 | Payment fails silently without error message | 1. Login and add items to cart 2. Proceed to checkout 3. Enter invalid card number "1234-5678-9999-0000" 4. Click "Pay Now" | Page reloads without any feedback, order not placed | System should display clear error message indicating payment failure with reason | Critical | P1 | Emily Rodriguez | 2026-01-16 | David Kim | Exception not caught in PaymentService; frontend not handling error response | Added try-catch block in PaymentService with proper error DTO; updated frontend to display error messages from API | Closed |
| DEF-003 | Seller dashboard shows incorrect revenue calculation | 1. Login as verified seller 2. Navigate to Seller Dashboard 3. View "Total Revenue" metric 4. Compare with actual order totals | Revenue shows $5,420.00 but actual order sum is $4,890.00 | Revenue calculation should match sum of completed orders minus refunds and returns | High | P2 | Robert Taylor | 2026-01-17 | David Kim | Revenue query including cancelled and refunded orders; commission not properly deducted | Modified AdminAnalyticsService query to filter by OrderStatus.DELIVERED only; added commission deduction logic | Closed |
| DEF-004 | Product images not loading on Safari browser | 1. Open Safari browser (v14+) 2. Navigate to product listing page 3. Observe product images | Images show broken image icon on Safari; work fine on Chrome/Firefox | All product images should load correctly across all supported browsers | Medium | P2 | Amanda Foster | 2026-01-18 | Emily Rodriguez | Safari requires explicit CORS headers for image requests; webp format not fully supported | Added CORS configuration for image endpoints; added fallback to JPEG format for unsupported browsers | Closed |
| DEF-005 | Wishlist API returns empty array for premium users | 1. Login as premium customer 2. Add products to wishlist 3. Navigate to wishlist page 4. Observe empty list | Wishlist page shows "No items in wishlist" despite products being added | Wishlist should display all products added by the user | High | P1 | Jessica Williams | 2026-01-19 | David Kim | WishlistRepository query filtering by premiumStatus incorrectly; method findByUserAndActiveTrue missing | Added findByUserAndActiveTrue method to WishlistRepository; fixed query to include premium users | Closed |
| DEF-006 | Order status history not recording all transitions | 1. Login as admin 2. Navigate to order management 3. Update order from "PLACED" to "CONFIRMED" to "SHIPPED" 4. View order history | History shows only "PLACED" and "SHIPPED" missing "CONFIRMED" | All status transitions should be recorded in order history | Medium | P3 | Christopher Lee | 2026-01-20 | Michael Chen | OrderStatusHistoryService not called for intermediate status updates; only initial and final states logged | Added OrderStatusHistory creation in AdminOrderService for every status change; added event listener pattern | In Progress |
| DEF-007 | Search results pagination returns duplicate products | 1. Search for "wireless" 2. Navigate to page 2 3. Navigate to page 3 4. Observe product listings | Same 3 products appear on both page 2 and page 3 | Each page should show unique products without duplicates | Medium | P2 | Jessica Williams | 2026-01-21 | Emily Rodriguez | ProductRepository pageable query missing ORDER BY clause; default ordering causing inconsistent results | Added explicit ORDER BY createdAt DESC in product search query; verified unique results across pages | Closed |
| DEF-008 | Admin cannot delete category with existing products | 1. Login as admin 2. Navigate to Category Management 3. Try to delete "Electronics" category 4. Observe result | Application throws 500 Internal Server Error | System should display warning that category has products and prevent deletion with clear message | Medium | P3 | Robert Taylor | 2026-01-22 | David Kim | Foreign key constraint violation not handled gracefully; CategoryService missing pre-deletion validation | Added product count check before deletion; return appropriate error message if category has associated products | Open |
| DEF-009 | Mobile view: Checkout button overlaps price on small screens | 1. Open application on mobile device (width < 375px) 2. Add items to cart 3. View cart page 4. Observe checkout section | "Proceed to Checkout" button overlays on top of price summary text | Button should be properly positioned below the price summary on small screens | Low | P4 | Amanda Foster | 2026-01-23 | Emily Rodriguez | CSS media query breakpoint not covering extra-small devices; flexbox layout not wrapping properly | Added additional breakpoint for xs devices (max-width: 374px); changed flex-direction to column | Closed |
| DEF-010 | Recently viewed products showing deleted products | 1. Login as customer 2. View several products 3. Admin deletes one of those products 4. View Recently Viewed section | Deleted product still appears in recently viewed list with broken link | Deleted products should be automatically removed from recently viewed lists | Low | P4 | Jessica Williams | 2026-01-25 | Michael Chen | RecentlyViewed records not cascade deleted when product is removed; orphan records remain in database | Added CASCADE delete on Product-RecentlyViewed relationship; added cleanup job for orphan records | Open |

---

## Defect Status Definitions

| Status | Definition |
|--------|------------|
| Open | Defect has been logged and is awaiting assignment or investigation |
| In Progress | Developer is actively working on the fix |
| Fixed | Code fix has been implemented and is ready for testing |
| Closed | Fix has been verified by QA and deployed to production |
| Reopened | Previously closed defect has recurred or fix was incomplete |
| Deferred | Defect will be addressed in a future release |
| Won't Fix | Defect will not be fixed (by design, low priority, or obsolete) |

---

## Severity Definitions

| Severity | Definition | Examples |
|----------|------------|----------|
| Critical | System is completely unusable; no workaround exists | Payment processing failure, data loss, security breach |
| High | Major feature is broken; limited or difficult workaround | Core shopping flow blocked, user cannot complete orders |
| Medium | Feature partially works; workaround is available | Minor calculation errors, UI inconsistencies |
| Low | Cosmetic issues or minor inconveniences | Typos, alignment issues, minor display bugs |

---

## Priority Definitions

| Priority | Definition | Response Time |
|----------|------------|---------------|
| P1 | Must be fixed immediately; blocking release | Within 24 hours |
| P2 | Should be fixed in current sprint | Within 1 week |
| P3 | Can be fixed in next sprint | Within 2 weeks |
| P4 | Nice to have; fix when time permits | No specific timeline |

---

## Defect Metrics

### By Status
- Open: 2
- In Progress: 1
- Closed: 7
- Total: 10

### By Severity
- Critical: 1 (10%)
- High: 3 (30%)
- Medium: 4 (40%)
- Low: 2 (20%)

### By Module
- Cart/Checkout: 2
- Product Catalog: 2
- User Features: 2
- Admin Features: 2
- Seller Features: 1
- UI/UX: 1

### Resolution Rate
- Resolved: 80%
- Pending: 20%

---

## Notes

1. All critical defects must be resolved before production release.
2. Defects should be verified in staging environment before marking as closed.
3. Regression testing required for all closed defects.
4. Weekly defect review meeting scheduled for Fridays at 10:00 AM.

---

**Document End**

*Last Updated: January 30, 2026*
