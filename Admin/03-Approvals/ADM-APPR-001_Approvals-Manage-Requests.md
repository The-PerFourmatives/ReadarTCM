# ADM-APPR-001 — Approvals — View and Manage Loan Requests

**Test Case ID:** ADM-APPR-001  
**Module:** Admin  
**Page:** Approvals (`/Admin/Approvals`)  
**Summary:** Verify that an admin can view pending loan/reservation approval requests and approve or reject them.  
**Priority:** Critical  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as an Administrator.
- At least one pending approval request exists (submitted by a user).
- The Approvals page is accessible from the admin sidebar.

---

## Test Steps

### Scenario 1: ADM-APPR-001 — Approvals — View and Manage Loan Requests

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Navigate to the Approvals page. | Verify that the page loads and displays a list of pending approval requests. |
| 2 | Observe the approval request list columns. | Verify that each entry shows relevant information (e.g., User Name, Book Title, Request Date, Status). |
| 3 | Search or filter the approvals list (if controls are present). | Verify that the list filters correctly based on the search or filter input. |
| 4 | Click the "Approve" action for a pending request. | Verify that a confirmation prompt or immediate action is triggered, and upon confirmation, the request status changes to Approved. |
| 5 | Verify the approved request. | Verify that the approved request is no longer listed under "Pending" and moves to an Approved or Active state. |
| 6 | Click the "Deny" action for a pending request. | Verify that the request status changes to Denied. |
| 7 | On the same page from step 6, observe the denial request. | Verify that the user's reservation status reflects the admin's approval or denial decision. |
| 8 | Check that the user received a notification regarding the approval/rejection. | Verify that a notification appears in the user's notification list. |

---

## Postconditions

- The approved loan is created and the book copy count is updated accordingly.
- The rejected request is closed with the appropriate status.
- The user is notified of the decision.