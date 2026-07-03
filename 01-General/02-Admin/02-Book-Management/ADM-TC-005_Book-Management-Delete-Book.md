# ADM-TC-005 — Book Management — Delete Book (Modal)

**Test Case ID:** ADM-TC-005  
**Module:** Admin  
**Page:** Book Management Index (`/Admin/BookManagement` via Delete Confirmation Modal)  
**Summary:** Verify that an admin can successfully delete a book from the catalog using the delete confirmation modal if it has no active loans or reservations (even if it has historical loan records), and that the system blocks deletion if any copies are currently borrowed or reserved.  
**Priority:** High  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as an Administrator.
- The Book Management Index page is loaded.
- **Scenario 1:** At least one book exists that has **historical (returned/completed) loan records** in the database, but currently has **no active loans** (none borrowed) and **no active reservations** (none reserved).
- **Scenario 2:** At least one book exists that has **active loans** (status: `Borrowed`) or **active reservations** (status: `Reserved`) on any of its copies.

---

## Test Steps

### Scenario 1: Delete Book with Historical Loans Only (No active loans/holds)

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Locate the target book in the table (which has historical loan history but all current copies are `Available`). | Verify that the book is listed and all copies are available. |
| 2 | Click its "Delete" (trash icon or button) action. | Verify that a Delete Confirmation modal pops up asking "Are you sure you want to delete this book?". |
| 3 | Click "Cancel" on the confirmation modal. | Verify that the modal closes and the book remains in the list (not deleted). |
| 4 | Click the "Delete" action again, and click "Confirm" on the confirmation modal. | Verify that the modal closes, the page refreshes, and the book is successfully removed from the catalog. |
| 5 | Search for the deleted book in the search bar. | Verify that the book no longer appears in the list, confirming that historical records do not block catalog deletion. |

---

### Scenario 2: Attempt to Delete Book with Active Loans or Reservations

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Locate a book that has at least one copy in `Borrowed` or `Reserved` status. | Verify that the book is listed and has active copies. |
| 2 | Click its "Delete" action. | Verify that the Delete Confirmation modal pops up. |
| 3 | Click "Confirm" on the confirmation modal. | Verify that the page refreshes, an error message is displayed: `A book cannot be deleted when it is still borrowed or reserved.`, and the book is not deleted. |
| 4 | Inspect the book table. | Verify that the book is still listed in the catalog. |

---

## Postconditions

- Eligible books (no active checkouts/holds) are permanently removed from the catalog database.
- Ineligible books (with active checkouts/holds) remain unaltered in the catalog.
- The total book catalog count decrements by one for each successful deletion.
