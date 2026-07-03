# ADM-RTRN-001 — Return Processing

**Test Case ID:** ADM-RTRN-001  
**Module:** Admin  
**Page:** Return (`/Admin/Return`)  
**Summary:** Verify that an admin can view all active loans, search and filter them, and successfully process a standard (non-overdue) book return.  
**Priority:** Critical  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as an Administrator.
- At least one active, non-overdue loan exists in the system.
- The Return page is accessible from the admin sidebar.

---

## Test Steps

### Scenario 1: View Active Loans List

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Navigate to the Return page. | Verify that the page loads and displays a list of all currently active loans. |
| 2 | Observe the summary statistics. | Verify that the page shows: Total Active Loans and Total Overdue Loans counts, accurately reflecting the current data. |
| 3 | Observe the loan list columns. | Verify that each row shows relevant information (e.g., Borrower Name, Borrower Email, Book Title, Borrow Date, Due Date, Status). |

---

### Scenario 2: Search Active Loans

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Enter a borrower's name in the search bar and submit. | Verify that the results are filtered to show only loans matching the borrower's name. |
| 2 | Enter a borrower's email in the search bar. | Verify that results are filtered by email. |
| 3 | Enter a book title in the search bar. | Verify that results are filtered by book title. |
| 4 | Search for a term that matches no records. | Verify that the results show an empty state or "No active loans for [book title]." message. |

---

### Scenario 3: Filter & Sort

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Filter the list by status/overdue indicator (if controls are present). | Verify that the table updates to show only the selected category of loans. |
| 2 | Sort the table by Due Date (ascending/descending) or Borrower Name. | Verify that the rows reorder correctly based on the chosen sort parameter. |

---

### Scenario 4: Process Standard Return (Non-Overdue)

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Locate an active, non-overdue loan. | Verify that a "Mark Returned" button or action is available for the loan. |
| 2 | Click the "Mark Returned" action (using the borrowing token). | Verify that a success toast is shown ("Book marked as returned successfully."). |
| 3 | Verify the loan is removed from the active list. | Verify that the returned book's loan no longer appears in the Return page list. |
| 4 | Check the user's Loans page (as the user). | Verify that the loan is now shown as "Returned" with the correct return date recorded. |

---

## Postconditions

- The returned book's copy status in the database updates to Available.
- The returned loan record is updated with the current timestamp in ReturnDate.
- No fines are generated or modified during standard returns.
