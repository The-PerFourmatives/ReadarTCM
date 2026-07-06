# USR-LOAN-002 — Loans — Renew a Book

**Test Case ID:** USR-LOAN-002  
**Module:** User — Loans  
**Page:** Loans (`/User/Loans`)  
**Summary:** Verify that a user can successfully renew an active loan to extend its due date, and that ineligible loans (overdue, already returned) cannot be renewed.  
**Priority:** High  
**Status:** ✅ Pass
---

## Preconditions

- The tester is logged in as a User with at least one **active, non-overdue** loan.
- The user also has an overdue loan (to test renewal restriction).
- The Loans page is accessible.

---

## Test Steps

### Scenario 1: USR-LOAN-002 — Loans — Renew a Book

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Navigate to the Loans page and locate an active, non-overdue loan. | Verify that a "Renew" button or action is visible for the active loan. |
| 2 | Click the "Renew" button for the active loan. | Verify that a success response is returned and the due date is extended accordingly. |
| 3 | Observe the loan's due date after renewal. | Verify that the due date has been extended by the allowed renewal period (confirm the expected number of days from business rules). |
| 4 | Locate an **overdue** loan on the Loans page. | Verify that the "Renew" button state is changed to a disabled state with "Late" label. |
| 5 | Attempt to renew a loan that has already been returned. | Verify that the renewal action is disabled state. |
| 6 | Attempt to renew the same loan thrice in a row (renewals are limited to 2 times). | Verify that the system returns an appropriate error message if the maximum renewal limit has been reached. |

---

## Postconditions

- The renewed loan's due date is updated in the database.
- The loan list reflects the new due date immediately after renewal.
- Overdue loans remain ineligible for renewal.
