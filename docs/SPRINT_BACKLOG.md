# SPRINT BACKLOG

## ECommerce Platform - Sprint 1

**Project Name:** ECommerce Platform v3.0
**Sprint Number:** 1
**Sprint Duration:** January 27, 2026 - January 31, 2026 (5 working days)
**Document Version:** 1.0

---

# SPRINT OVERVIEW

## Team Information

| Member ID | Name | Role | Daily Hours | Weekly Hours |
|-----------|------|------|-------------|--------------|
| TM-01 | Michael Chen | Lead Developer | 9 | 45 |
| TM-02 | Emily Rodriguez | Frontend Developer | 9 | 45 |
| TM-03 | David Kim | Backend Developer | 9 | 45 |
| TM-04 | Jessica Williams | QA Engineer | 9 | 45 |
| TM-05 | Robert Taylor | DevOps/Backend Developer | 9 | 45 |
| TM-06 | Amanda Foster | Frontend Developer | 9 | 45 |
| TM-07 | Christopher Lee | Full Stack Developer | 9 | 45 |
| TM-08 | Sarah Thompson | Full Stack Developer | 9 | 45 |

## Sprint Capacity

| Metric | Value |
|--------|-------|
| Team Size | 8 members |
| Hours per Day | 9 hours/person |
| Sprint Duration | 5 days |
| **Total Sprint Capacity** | **360 hours** |
| Buffer (10%) | 36 hours |
| **Available Capacity** | **324 hours** |

---

# SPRINT BACKLOG TABLE

## Summary

| User Story ID | Description | Dev Hours | Test Hours | Review Hours | Total Hours |
|---------------|-------------|-----------|------------|--------------|-------------|
| US-001 | User Registration | 18 | 9 | 6 | 33 |
| US-002 | User Login | 12 | 8 | 5 | 25 |
| US-003 | Browse Product Catalog | 28 | 12 | 8 | 48 |
| US-004 | Product Search | 20 | 10 | 6 | 36 |
| US-005 | Add to Cart | 18 | 9 | 6 | 33 |
| US-006 | View Cart | 14 | 8 | 5 | 27 |
| US-007 | Apply Coupon | 12 | 7 | 4 | 23 |
| US-008 | Checkout - Address Selection | 16 | 8 | 5 | 29 |
| US-009 | Checkout - Payment | 20 | 10 | 6 | 36 |
| US-010 | Order Confirmation | 10 | 6 | 4 | 20 |
| **TOTAL** | | **168** | **87** | **55** | **310** |

---

# DETAILED SPRINT BACKLOG

## US-001: User Registration

| Task | Assigned To | Total Hours | Mon | Tue | Wed | Thu | Fri |
|------|-------------|-------------|-----|-----|-----|-----|-----|
| **Development** | Michael Chen (TM-01) | 18 | 9 | 9 | - | - | - |
| **Testing** | Jessica Williams (TM-04) | 9 | - | - | 5 | 4 | - |
| **Code Review** | David Kim (TM-03) | 6 | - | - | 3 | 3 | - |
| **Total** | | **33** | **9** | **9** | **8** | **7** | **0** |

### Task Breakdown - Development (18 hours)
| Sub-task | Hours | Day |
|----------|-------|-----|
| Backend: Create User entity and DTO | 3 | Mon |
| Backend: Implement UserRepository | 2 | Mon |
| Backend: Create AuthService registration logic | 4 | Mon |
| Backend: Create AuthController endpoint | 2 | Tue |
| Frontend: Create RegisterComponent | 4 | Tue |
| Frontend: Form validation and error handling | 3 | Tue |

### Task Breakdown - Testing (9 hours)
| Sub-task | Hours | Day |
|----------|-------|-----|
| Unit tests for registration service | 3 | Wed |
| Integration tests for registration endpoint | 3 | Wed |
| Frontend component testing | 2 | Thu |
| End-to-end registration flow testing | 1 | Thu |

---

## US-002: User Login

| Task | Assigned To | Total Hours | Mon | Tue | Wed | Thu | Fri |
|------|-------------|-------------|-----|-----|-----|-----|-----|
| **Development** | Emily Rodriguez (TM-02) | 12 | 6 | 6 | - | - | - |
| **Testing** | Jessica Williams (TM-04) | 8 | - | - | 4 | 4 | - |
| **Code Review** | Michael Chen (TM-01) | 5 | - | - | - | 2 | 3 |
| **Total** | | **25** | **6** | **6** | **4** | **6** | **3** |

### Task Breakdown - Development (12 hours)
| Sub-task | Hours | Day |
|----------|-------|-----|
| Backend: Implement login service logic | 3 | Mon |
| Backend: Create login endpoint | 2 | Mon |
| Backend: Session management implementation | 1 | Mon |
| Frontend: Create LoginComponent | 3 | Tue |
| Frontend: Auth interceptor for headers | 2 | Tue |
| Frontend: Auth guard implementation | 1 | Tue |

### Task Breakdown - Testing (8 hours)
| Sub-task | Hours | Day |
|----------|-------|-----|
| Unit tests for login service | 2 | Wed |
| Integration tests for login endpoint | 2 | Wed |
| Session timeout testing | 2 | Thu |
| Invalid credentials testing | 2 | Thu |

---

## US-003: Browse Product Catalog

| Task | Assigned To | Total Hours | Mon | Tue | Wed | Thu | Fri |
|------|-------------|-------------|-----|-----|-----|-----|-----|
| **Development** | David Kim (TM-03) | 28 | 9 | 9 | 7 | 3 | - |
| **Testing** | Robert Taylor (TM-05) | 12 | - | - | - | 6 | 6 |
| **Code Review** | Christopher Lee (TM-07) | 8 | - | - | - | 3 | 5 |
| **Total** | | **48** | **9** | **9** | **7** | **12** | **11** |

### Task Breakdown - Development (28 hours)
| Sub-task | Hours | Day |
|----------|-------|-----|
| Backend: Product entity and repository | 3 | Mon |
| Backend: ProductService with pagination | 4 | Mon |
| Backend: Filtering by category, price, rating | 2 | Mon |
| Backend: Sorting implementation | 2 | Tue |
| Backend: ProductController endpoints | 2 | Tue |
| Frontend: ProductListComponent | 5 | Tue |
| Frontend: Filter sidebar component | 4 | Wed |
| Frontend: Sorting dropdown | 2 | Wed |
| Frontend: Pagination component | 3 | Wed |
| Backend: Category service and endpoints | 1 | Thu |

### Task Breakdown - Testing (12 hours)
| Sub-task | Hours | Day |
|----------|-------|-----|
| Unit tests for product service | 3 | Thu |
| Pagination testing | 2 | Thu |
| Filter combination testing | 3 | Fri |
| Sorting verification | 2 | Fri |
| Performance testing for large datasets | 2 | Fri |

---

## US-004: Product Search

| Task | Assigned To | Total Hours | Mon | Tue | Wed | Thu | Fri |
|------|-------------|-------------|-----|-----|-----|-----|-----|
| **Development** | Amanda Foster (TM-06) | 20 | 9 | 9 | 2 | - | - |
| **Testing** | Jessica Williams (TM-04) | 10 | - | - | - | 5 | 5 |
| **Code Review** | Emily Rodriguez (TM-02) | 6 | - | - | - | 3 | 3 |
| **Total** | | **36** | **9** | **9** | **2** | **8** | **8** |

### Task Breakdown - Development (20 hours)
| Sub-task | Hours | Day |
|----------|-------|-----|
| Backend: Search service with keyword matching | 5 | Mon |
| Backend: Search across name and description | 2 | Mon |
| Backend: Handle special characters | 2 | Mon |
| Backend: Search controller endpoint | 2 | Tue |
| Frontend: Search bar component | 4 | Tue |
| Frontend: Search results page | 3 | Tue |
| Frontend: No results handling | 2 | Wed |

### Task Breakdown - Testing (10 hours)
| Sub-task | Hours | Day |
|----------|-------|-----|
| Search with various keywords | 3 | Thu |
| Empty/no results testing | 2 | Thu |
| Special character handling | 2 | Fri |
| Search performance testing | 2 | Fri |
| Cross-browser testing | 1 | Fri |

---

## US-005: Add to Cart

| Task | Assigned To | Total Hours | Mon | Tue | Wed | Thu | Fri |
|------|-------------|-------------|-----|-----|-----|-----|-----|
| **Development** | Christopher Lee (TM-07) | 18 | 9 | 9 | - | - | - |
| **Testing** | Robert Taylor (TM-05) | 9 | - | - | 5 | 4 | - |
| **Code Review** | David Kim (TM-03) | 6 | - | - | 3 | 3 | - |
| **Total** | | **33** | **9** | **9** | **8** | **7** | **0** |

### Task Breakdown - Development (18 hours)
| Sub-task | Hours | Day |
|----------|-------|-----|
| Backend: Cart and CartItem entities | 3 | Mon |
| Backend: CartRepository implementation | 2 | Mon |
| Backend: CartService add/remove logic | 4 | Mon |
| Backend: CartController endpoints | 2 | Tue |
| Frontend: Add to Cart button component | 3 | Tue |
| Frontend: Cart notification/toast | 2 | Tue |
| Frontend: Cart icon with count badge | 2 | Tue |

### Task Breakdown - Testing (9 hours)
| Sub-task | Hours | Day |
|----------|-------|-----|
| Add single item to cart | 2 | Wed |
| Add with quantity testing | 2 | Wed |
| Duplicate item handling | 2 | Wed |
| Stock validation testing | 2 | Thu |
| Cart persistence testing | 1 | Thu |

---

## US-006: View Cart

| Task | Assigned To | Total Hours | Mon | Tue | Wed | Thu | Fri |
|------|-------------|-------------|-----|-----|-----|-----|-----|
| **Development** | Sarah Thompson (TM-08) | 14 | 7 | 7 | - | - | - |
| **Testing** | Jessica Williams (TM-04) | 8 | - | - | 4 | 4 | - |
| **Code Review** | Amanda Foster (TM-06) | 5 | - | - | 2 | 3 | - |
| **Total** | | **27** | **7** | **7** | **6** | **7** | **0** |

### Task Breakdown - Development (14 hours)
| Sub-task | Hours | Day |
|----------|-------|-----|
| Backend: Get cart endpoint | 2 | Mon |
| Backend: Update quantity endpoint | 2 | Mon |
| Backend: Remove item endpoint | 2 | Mon |
| Backend: Clear cart endpoint | 1 | Mon |
| Frontend: CartComponent UI | 4 | Tue |
| Frontend: Quantity update functionality | 2 | Tue |
| Frontend: Remove and clear actions | 1 | Tue |

### Task Breakdown - Testing (8 hours)
| Sub-task | Hours | Day |
|----------|-------|-----|
| View cart with items | 2 | Wed |
| Update quantity testing | 2 | Wed |
| Remove individual items | 2 | Thu |
| Clear entire cart | 1 | Thu |
| Empty cart display | 1 | Thu |

---

## US-007: Apply Coupon

| Task | Assigned To | Total Hours | Mon | Tue | Wed | Thu | Fri |
|------|-------------|-------------|-----|-----|-----|-----|-----|
| **Development** | Michael Chen (TM-01) | 12 | - | - | 6 | 6 | - |
| **Testing** | Robert Taylor (TM-05) | 7 | - | - | - | - | 7 |
| **Code Review** | Emily Rodriguez (TM-02) | 4 | - | - | - | - | 4 |
| **Total** | | **23** | **0** | **0** | **6** | **6** | **11** |

### Task Breakdown - Development (12 hours)
| Sub-task | Hours | Day |
|----------|-------|-----|
| Backend: Coupon entity and repository | 2 | Wed |
| Backend: CouponService validation logic | 4 | Wed |
| Backend: Apply coupon endpoint | 2 | Thu |
| Frontend: Coupon input in cart | 2 | Thu |
| Frontend: Discount display and error handling | 2 | Thu |

### Task Breakdown - Testing (7 hours)
| Sub-task | Hours | Day |
|----------|-------|-----|
| Valid coupon application | 2 | Fri |
| Invalid/expired coupon | 2 | Fri |
| Minimum order amount validation | 2 | Fri |
| Multiple coupon attempts | 1 | Fri |

---

## US-008: Checkout - Address Selection

| Task | Assigned To | Total Hours | Mon | Tue | Wed | Thu | Fri |
|------|-------------|-------------|-----|-----|-----|-----|-----|
| **Development** | Emily Rodriguez (TM-02) | 16 | - | - | 5 | 7 | 4 |
| **Testing** | Jessica Williams (TM-04) | 8 | - | - | - | - | 8 |
| **Code Review** | Christopher Lee (TM-07) | 5 | - | - | - | - | 5 |
| **Total** | | **29** | **0** | **0** | **5** | **7** | **17** |

### Task Breakdown - Development (16 hours)
| Sub-task | Hours | Day |
|----------|-------|-----|
| Backend: UserAddress entity and repository | 2 | Wed |
| Backend: AddressService CRUD | 3 | Wed |
| Backend: Address controller endpoints | 2 | Thu |
| Frontend: Address list component | 3 | Thu |
| Frontend: Add new address form | 3 | Thu |
| Frontend: Address selection in checkout | 3 | Fri |

### Task Breakdown - Testing (8 hours)
| Sub-task | Hours | Day |
|----------|-------|-----|
| Add new address | 2 | Fri |
| Edit existing address | 2 | Fri |
| Delete address | 1 | Fri |
| Select address at checkout | 2 | Fri |
| Address validation | 1 | Fri |

---

## US-009: Checkout - Payment

| Task | Assigned To | Total Hours | Mon | Tue | Wed | Thu | Fri |
|------|-------------|-------------|-----|-----|-----|-----|-----|
| **Development** | David Kim (TM-03) | 20 | - | - | - | 2 | 9 |
| **Development** | Robert Taylor (TM-05) | - | - | - | - | - | 9 |
| **Testing** | Amanda Foster (TM-06) | 10 | - | - | - | - | 6 |
| **Testing Continuation** | | - | Sprint 2: 4 hours | | | | |
| **Code Review** | Sarah Thompson (TM-08) | 6 | - | - | - | - | 6 |
| **Total** | | **36** | **0** | **0** | **0** | **2** | **30** |

### Task Breakdown - Development (20 hours)
| Sub-task | Hours | Day |
|----------|-------|-----|
| Backend: Payment entity and repository | 2 | Thu |
| Backend: PaymentService logic | 4 | Fri |
| Backend: Order creation on payment | 4 | Fri |
| Backend: Payment controller | 2 | Fri |
| Frontend: Payment method selection | 4 | Fri |
| Frontend: Payment form | 4 | Fri |

### Task Breakdown - Testing (10 hours)
| Sub-task | Hours | Day |
|----------|-------|-----|
| COD payment flow | 2 | Fri |
| Card payment validation | 2 | Fri |
| Payment error handling | 2 | Fri |
| Order creation verification | 2 | Sprint 2 |
| Payment status updates | 2 | Sprint 2 |

---

## US-010: Order Confirmation

| Task | Assigned To | Total Hours | Mon | Tue | Wed | Thu | Fri |
|------|-------------|-------------|-----|-----|-----|-----|-----|
| **Development** | Sarah Thompson (TM-08) | 10 | - | - | 5 | 5 | - |
| **Testing** | Robert Taylor (TM-05) | 6 | - | - | - | - | 6 |
| **Code Review** | Michael Chen (TM-01) | 4 | - | - | - | - | 4 |
| **Total** | | **20** | **0** | **0** | **5** | **5** | **10** |

### Task Breakdown - Development (10 hours)
| Sub-task | Hours | Day |
|----------|-------|-----|
| Backend: Order confirmation email service | 3 | Wed |
| Backend: Generate order ID | 1 | Wed |
| Backend: Order details endpoint | 1 | Wed |
| Frontend: Confirmation page component | 3 | Thu |
| Frontend: Order summary display | 2 | Thu |

### Task Breakdown - Testing (6 hours)
| Sub-task | Hours | Day |
|----------|-------|-----|
| Order ID generation | 1 | Fri |
| Confirmation page display | 2 | Fri |
| Order details accuracy | 2 | Fri |
| Email notification | 1 | Fri |

---

# TEAM MEMBER WORKLOAD DISTRIBUTION

## Daily Hours by Team Member

| Team Member | Mon | Tue | Wed | Thu | Fri | Total |
|-------------|-----|-----|-----|-----|-----|-------|
| Michael Chen (TM-01) | 9 | 9 | 6 | 8 | 7 | 39 |
| Emily Rodriguez (TM-02) | 6 | 6 | 5 | 10 | 11 | 38 |
| David Kim (TM-03) | 9 | 9 | 10 | 8 | 9 | 45 |
| Jessica Williams (TM-04) | 0 | 0 | 9 | 17 | 13 | 39 |
| Robert Taylor (TM-05) | 0 | 0 | 5 | 10 | 28 | 43 |
| Amanda Foster (TM-06) | 9 | 9 | 4 | 6 | 12 | 40 |
| Christopher Lee (TM-07) | 9 | 9 | 3 | 12 | 10 | 43 |
| Sarah Thompson (TM-08) | 7 | 7 | 5 | 10 | 16 | 45 |
| **Daily Total** | **49** | **49** | **47** | **81** | **106** | **332** |

*Note: Some days show more than 9 hours per person due to task overlap flexibility. Actual allocation will be adjusted in daily standups.*

---

## Hours by Task Type

| Task Type | Hours | Percentage |
|-----------|-------|------------|
| Development | 168 | 54% |
| Testing | 87 | 28% |
| Code Review | 55 | 18% |
| **Total** | **310** | **100%** |

---

## Remaining Capacity

| Metric | Hours |
|--------|-------|
| Total Sprint Capacity | 360 |
| Allocated to User Stories | 310 |
| **Remaining Capacity** | **50** |

### Remaining Capacity Allocation
- Sprint ceremonies (planning, standup, review, retro): 24 hours (3 hours × 8 people)
- Buffer for blockers/issues: 16 hours
- Knowledge sharing/documentation: 10 hours

---

# SPRINT BURNDOWN CHART DATA

| Day | Ideal Remaining (hrs) | Planned Remaining (hrs) |
|-----|----------------------|------------------------|
| Start | 310 | 310 |
| Mon EOD | 248 | 261 (49 completed) |
| Tue EOD | 186 | 212 (49 completed) |
| Wed EOD | 124 | 165 (47 completed) |
| Thu EOD | 62 | 84 (81 completed) |
| Fri EOD | 0 | 0 (106 completed) |

---

# SPRINT GOALS

1. **Primary Goal:** Complete user authentication flow (registration and login)
2. **Secondary Goal:** Implement core shopping experience (browse, search, cart)
3. **Stretch Goal:** Begin checkout process (address selection, payment initiation)

---

# DEFINITION OF DONE

Each user story is considered done when:
- [ ] All development tasks completed
- [ ] Code reviewed and approved
- [ ] Unit tests written and passing (80%+ coverage)
- [ ] Integration tests passing
- [ ] No critical or high severity bugs
- [ ] Documentation updated
- [ ] Deployed to staging environment
- [ ] Product Owner acceptance

---

# RISKS AND DEPENDENCIES

| Risk | Impact | Mitigation |
|------|--------|------------|
| Payment integration complexity | High | Early spike, mock service as fallback |
| Database performance with filters | Medium | Query optimization, indexing |
| Frontend state management | Medium | Use established patterns, pair programming |

| Dependency | User Story | Status |
|------------|-----------|--------|
| US-001 (Registration) | US-002 (Login) | Internal |
| US-003 (Browse) | US-005 (Add to Cart) | Internal |
| US-005, US-006 (Cart) | US-007, US-008, US-009 (Checkout) | Internal |

---

# NOTES

1. Daily standup at 9:30 AM to address blockers
2. Code freeze for Sprint 1 on Friday 3:00 PM
3. Sprint review scheduled for Friday 4:00 PM
4. Remaining testing for US-009 to be completed in Sprint 2 first day

---

**Document End**

*Sprint Backlog - Sprint 1*
*ECommerce Platform v3.0*
*Version 1.0 - January 30, 2026*
