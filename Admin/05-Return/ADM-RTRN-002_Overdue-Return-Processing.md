# ADM-RTRN-002 — Overdue Return Processing (Fines and Redirects)

**Test Case ID:** ADM-RTRN-002  
**Module:** Admin  
**Page:** Return (`/Admin/Return` redirecting to `/Admin/FineManagement/UserFinesDetails`)  
**Summary:** Verify that processing a return for an overdue book successfully records the return, automatically generates the correct fine, and redirects the administrator to the user's fine details page to resolve the fines.  
**Priority:** Critical  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as an Administrator.
- At least one overdue loan exists in the system (the due date has passed).
- The Return page is accessible from the admin sidebar.

---

## Test Steps

### Scenario 1: Process Overdue Return (With Automatic Fine Redirection)

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Navigate to the Return page. | Verify that the page loads and displays active loans. |
| 2 | Locate an active overdue loan (visually marked as overdue). | Verify the loan details and confirm it is overdue. |
| 3 | Click the "Mark Returned" action for the overdue loan. | Verify that the return is processed successfully, a toast appears saying `"Book returned. Redirecting to resolve fines..."`, and the browser automatically redirects to the **User Fines Details** page (`/Admin/FineManagement/UserFinesDetails?email=...`) of the borrower. |
| 4 | On the redirected User Fines Details page, inspect the fines table. | Verify that a new fine record exists representing this overdue return, showing the correct amount calculated based on the overdue duration. |

---

## Postconditions

- The overdue book's copy status updates to Available.
- The returned loan record is updated with the current timestamp in ReturnDate.
- A new Fine record is generated in the database with status "Unpaid" linked to this borrowing record.
