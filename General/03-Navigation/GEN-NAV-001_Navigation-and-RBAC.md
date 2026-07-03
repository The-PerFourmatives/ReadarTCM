# GEN-NAV-001 — Navigation & Role-Based Access Control

**Test Case ID:** GEN-NAV-001  
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

### Scenario 1: GEN-NAV-001 — Public and User Navigation Views

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Navigate to the landing page as an unauthenticated (public) user. | Verify that only public header navigation is visible (e.g. Home, Login, Register). |
| 2 | Log in as a regular User. | Verify that the header switches to user-specific views (e.g. Catalog, Reservations, Loans, Fines, Logout). |
| 3 | While unauthenticated, attempt to navigate directly to a protected user route (e.g., `/Loans`). | Verify that the user is redirected to the Login page and not shown protected content. |

---

### Scenario 2: GEN-NAV-001 — Admin Navigation Views

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Log in as an Administrator. | Verify that the admin header and admin sidebar/dashboard are visible and accessible. |
| 2 | While unauthenticated, attempt to navigate directly to a protected admin route (e.g., `/Admin/Dashboard`). | Verify that the user is redirected to the Login page and not shown the admin content. |

---

### Scenario 3: GEN-NAV-001 — Role-Based Access Control Restrictions

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Log in as a regular User and attempt to navigate directly to an admin-only route (e.g., `/Admin/Dashboard`). | Verify that access is denied (e.g., 403 Forbidden page or redirected back to the user dashboard with an authorization error). |
| 2 | Log in as an Admin and navigate to a user-only route (e.g., `/Loans`). | Verify that access is appropriately handled per the system's role rules. |
| 3 | After logging out, attempt to navigate back using the browser's Back button to a previously viewed protected page. | Verify that the user is not shown the cached protected page content and is redirected to the Login page. |

---

## Postconditions

- Role-based access control is enforced on all protected routes.
- No protected data is exposed to unauthorized users.
- Session invalidation on logout is properly enforced.