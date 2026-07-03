# ADM-TC-001 — Admin Dashboard Overview

**Test Case ID:** ADM-TC-001  
**Module:** Admin  
**Page:** Admin Dashboard (`/Admin/Dashboard`)  
**Summary:** Verify that the Admin Dashboard loads correctly and displays accurate system-wide statistics and recent activity.  
**Priority:** High  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as an Administrator.
- The system has existing data (users, books, loans, reservations, fines).
- The Admin Dashboard is accessible from the admin navigation sidebar.

---

## Test Steps

### Scenario 1: ADM-TC-001 — Admin Dashboard Overview

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Log in as an Admin and navigate to the Dashboard page. | Verify that the Admin Dashboard loads without errors and the page title is correct. |
| 2 | Observe the summary/statistic cards on the dashboard. | Verify that the cards display key metrics (e.g., total books, active loans, pending approvals, total users) with correct counts. |
| 3 | Observe any recent activity or log sections. | Verify that recent transactions, loans, or system events are listed with accurate information. |
| 4 | Observe the admin sidebar navigation. | Verify that all admin navigation items are present (Dashboard, Book Management, Approvals, Pickup, Return, Fine Management). |
| 5 | Click each sidebar navigation item. | Verify that each link navigates to the correct admin page without errors. |
| 6 | Observe the header on the admin layout. | Verify that the admin user's profile info (name/avatar), notification icon, and logout option are visible. |
| 7 | Click the notification icon. | Verify that the notification dropdown opens and shows the current notifications or an empty state message. |

---

## Postconditions

- The dashboard remains accessible.
- All statistics displayed accurately reflect the current system state.
- No console errors are present.