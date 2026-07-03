# ADM-FINE-001 — Fine Management — View and Manage User Fines

**Test Case ID:** ADM-FINE-001  
**Module:** Admin — Fine Management  
**Page:** Fine Management Index (`/Admin/FineManagement/Index`) and User Fines Details (`/Admin/FineManagement/UserFinesDetails`)  
**Summary:** Verify that an admin can view the list of users with outstanding fines, check their fine audits/details, and perform fine-clearing actions (mark as paid, waive, reject waive request) individually or in bulk.  
**Priority:** High  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as an Administrator.
- A test user has at least one unpaid fine with status "Unpaid".
- A test user has a fine with status "WaiveRequested" (User requested a waive).
- The Fine Management page is accessible from the admin sidebar.

---

## Test Steps

### Scenario 1: View Users with Fines & Search/Filter

| # | Step | Expected Behavior |
|---|------|-------------------|
| A1 | Navigate to the Fine Management page. | Verify that the page loads and displays a list of all users who currently have incurred fines. |
| A2 | Click on a user's name or the "View Details" action. | Verify that the page redirects to the User Fines Details page (`/Admin/FineManagement/UserFinesDetails?email=user@example.com`) showing all fines for that user. |
| A3 | Observe the user details header. | Verify that the user's name, email, and profile photo (if any) are correctly displayed at the top. |
| A4 | Observe the list of user fines. | Verify that the table displays: Book Detail, Item Due Date, Fine Amount, Status, and action buttons. |

---

### Scenario 2: Fine Audit Log

| # | Step | Expected Behavior |
|---|------|-------------------|
| B1 | On a specific fine row, click the book cover or book title action in the "Details" column. | Verify that the system fetches the fine history details from the API and displays it in a modal. |
| B2 | Observe the audit logs. | Verify that the audit trail shows the history of the fine (e.g., Date, Description, Amount). |

---

### Scenario 3: Verify Weekend Skipping in Fine Audit Log

| # | Step | Expected Behavior |
|---|------|-------------------|
| C1 | Locate a user fine where the period between the item's due date and the return date (or current date if unreturned) spans over a weekend (Saturday and Sunday). | Verify the dates of the fine record. |
| C2 | Click the book cover or book title action in the "Details" column to open the modal. | Verify that the history modal opens. |
| C3 | Inspect the dates of the daily log entries in the audit trail. | Verify that **Saturdays and Sundays are skipped** (do not appear as daily log entries) and no fine amount accrued for those weekend days, confirming that weekends do not count towards overdue fine accrual. |
---

## Postconditions

- The audit logs accurately reflect dates, descriptions, and accrued fine calculations.
- Saturdays and Sundays are excluded from all displayed daily audit entries.