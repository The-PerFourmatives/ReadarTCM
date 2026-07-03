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

### Scenario 1: ADM-APPR-001 — Approvals Search and Pagination

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Navigate to the Approvals page. | Verify that the page loads and displays a list of pending approval requests. |
| 2 | Observe the approval request list columns. | Verify that each entry shows relevant information (e.g., User Name, Book Title, Request Date, Status). |
| 3 | Search or filter the approvals list (if controls are present). | Verify that the list filters correctly based on the search or filter input. |
| 4 | Observe pagination controls (if there are more than 10 requests). | Verify that pagination functions and navigating to page 2 displays the next set of requests. |

---

### Scenario 2: ADM-APPR-001 — Process Loan Requests (Approve/Deny)

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Locate a pending approval request. | Verify that the "Approve" and "Deny" actions are visible. |
| 2 | Click the "Approve" action for a pending request. | Verify that a confirmation prompt or action is triggered, and the request status changes to Approved. |
| 3 | Verify the approved request. | Verify that the approved request is no longer listed under "Pending" and moves to an Approved or Active state. |
| 4 | Click the "Deny" action for another pending request. | Verify that the request status changes to Denied. |
| 5 | Verify the denial on the user side. | Verify that the user's reservation status reflects the admin's approval or denial decision, and they receive a corresponding notification. |

---

## Postconditions

- The approved loan is created and the book copy count is updated accordingly.
- The rejected request is closed with the appropriate status.
- The user is notified of the decision.