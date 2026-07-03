# USR-LOAN-001 — Loans — View Loan History

**Test Case ID:** USR-LOAN-001  
**Module:** User — Loans  
**Page:** Loans (`/User/Loans`)  
**Summary:** Verify that the user's Loans page correctly displays their full borrowing history with accurate summary counts, and that filtering, sorting, and pagination work as expected.  
**Priority:** High  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as a User who has at least one active loan and at least one returned loan in their history.
- The Loans page is accessible from the user navigation.

---

## Test Steps

### Scenario 1: USR-LOAN-001 — Loans — View Loan History

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Navigate to the Loans page. | Verify that the page loads and displays the user's borrowing history list. |
| 2 | Observe the summary statistics at the top of the page. | Verify that the summary cards correctly show: Total Books, Active Books, and Overdue Books counts based on the user's actual data. |
| 3 | Observe the loan list columns. | Verify that each row shows relevant information (e.g., Book Title, Borrow Date, Due Date, Return Date, Status). |
| 4 | Apply the "Active" filter. | Verify that only loans where the book has not been returned and is not overdue are displayed. |
| 5 | Apply the "Overdue" filter. | Verify that only loans where the due date has passed and the book has not been returned are displayed, with a visible overdue indicator. |
| 6 | Apply the "Returned" filter. | Verify that only loans where the book has been returned (Return Date is set) are displayed. |
| 7 | Clear the filter (select "All"). | Verify that all loans are displayed again regardless of status. |
| 8 | Change the sort order to "Oldest First". | Verify that loans are re-ordered so the oldest borrow date appears first. |
| 9 | Change the sort order to "Newest First" (default). | Verify that loans are ordered with the most recent borrow date appears first. |
| 10 | If the user has more than 10 loans, observe the pagination controls. | Verify that pagination is present and navigating to page 2 shows the next set of 10 loans. |
| 11 | Observe the page with a user who has no loans. | Verify that an appropriate empty state message is shown (e.g., "You have no borrowing history yet."). |

---

## Postconditions

- No loan data is modified during this test.
- All counts and statuses accurately reflect the current state of the user's loans in the database.