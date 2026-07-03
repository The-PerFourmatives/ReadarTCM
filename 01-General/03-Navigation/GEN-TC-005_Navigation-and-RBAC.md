# GEN-TC-005 — Navigation & Role-Based Access Control

**Test Case ID:** GEN-TC-005  
**Module:** General  
**Page:** All Pages  
**Summary:** Verify that unauthenticated users and users with incorrect roles cannot access protected routes.  
**Priority:** Critical  
**Status:** ⬜ Not Run

---

## Preconditions

- The user is not logged in (unauthenticated).
- A regular User account is logged in (non-admin).
- An Admin account is logged in.

---

## Test Steps

### Scenario 1: GEN-TC-005 — Navigation & Role-Based Access Control

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | While unauthenticated, navigate directly to a protected user route (e.g., `/Loans`). | Verify that the user is redirected to the Login page and not shown the protected content. |
| 2 | While unauthenticated, navigate directly to a protected admin route (e.g., `/Dashboard`). | Verify that the user is redirected to the Login page and not shown the admin content. |
| 3 | Log in as a regular User and navigate to an admin-only route (e.g., `/Dashboard`). | Verify that access is denied (e.g., 403 Forbidden page or redirect to user dashboard). |
| 4 | Log in as an Admin and navigate to a user-only route (e.g., `/Loans`). | Verify that access is appropriately handled per the system's role rules. |
| 5 | After logging out, attempt to navigate back using the browser's Back button to a previously viewed protected page. | Verify that the user is not shown the cached protected page content and is redirected to the Login page. |

---

## Postconditions

- Role-based access control is enforced on all protected routes.
- No protected data is exposed to unauthorized users.
- Session invalidation on logout is properly enforced.