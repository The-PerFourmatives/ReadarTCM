# ADM-BOOK-003 — Book Management — Edit Book (Modal)

**Test Case ID:** ADM-BOOK-003  
**Module:** Admin  
**Page:** Book Management Index (`/Admin/BookManagement` via Edit Modal)  
**Summary:** Verify that an admin can successfully update an existing book's information using the Edit Book modal, that validation is enforced, and that decreasing copies respects active loans/reservations while allowing historical cleanups.  
**Priority:** High  
**Status:** ✅ Pass

---

## Preconditions

- The tester is logged in as an Administrator.
- At least one book record exists in the system that can be edited.
- The Book Management Index page is loaded.

---

## Test Steps

### Scenario 1: Basic Information Updates and Required Fields Validation

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | On the Book Management page, click the "Edit" action for an existing book in the table. | Verify that the Edit Book modal opens and all input fields are pre-filled with the book's current data. |
| 2 | Clear a required field (e.g., Title) and attempt to save. | Verify that the browser blocks submission or a validation error is displayed for the cleared field and the book is not saved. |
| 3 | Modify the book title to a new valid value and click Save. | Verify that the changes are saved, the modal closes, the page refreshes, and a success message ("Book updated successfully.") is displayed. |
| 4 | On the Book Management list, locate the edited book. | Verify that the updated title (or other modified field) is reflected correctly in the list. |

---

### Scenario 2: Decrease Copy Count Below Active Loans and Reservations

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Select a book that has active loans (status: `Borrowed`) or active reservations (status: `Reserved`). Note the total count of active copies (e.g., 2 copies are borrowed/reserved). | Verify the current status of copies for the target book. |
| 2 | Click "Edit" for the book to open the Edit modal. | Verify the modal opens successfully. |
| 3 | Set the "Number of Copies" to a value **less** than the number of active copies (e.g. if 2 are borrowed, set copies to 1) and click Save. | Verify that the page refreshes and displays a validation error message: `Editing a book must not set the total copies of a book to be less than the number of active copies (X).` |
| 4 | Check the book list table. | Verify that the total number of copies is unchanged. |

---

### Scenario 3: Decrease Copy Count for Book with Historical Loans Only

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Select a book that has **historical (returned/completed) loan records** in the database, but currently has **no active loans** (none borrowed) and **no active reservations** (none reserved). Note the current copy count (e.g., 3 copies). | Verify that the copies' current statuses are all `Available`. |
| 2 | Click "Edit" for the book to open the Edit modal. | Verify the modal opens successfully. |
| 3 | Set the "Number of Copies" to a lower value (e.g., set copies to 1) and click Save. | Verify that the changes are saved successfully, the modal closes, and a success message is displayed. |
| 4 | Check the book list table. | Verify that the copy count has successfully updated to the new lower value (e.g., 1 copy), confirming that historical loan records do not block copy reduction. |

---

## Postconditions

- The book record is updated in the database with the new values.
- The Book Management list reflects the updated book data.
- Active loans and reservations are never disrupted by copy reduction.
