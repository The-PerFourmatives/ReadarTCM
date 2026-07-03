# ADM-BOOK-002 — Book Management — Create Book (Modal)

**Test Case ID:** ADM-BOOK-002  
**Module:** Admin  
**Page:** Book Management Index (`/Admin/BookManagement` via Create Modal)  
**Summary:** Verify that an admin can successfully add a new book to the library catalog using the Create Book modal, and that validation prevents invalid submissions.  
**Priority:** High  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as an Administrator.
- The Book Management Index page is loaded.
- All required fields are known (Title, Author, ISBN, Genre, Copies, etc.).

---

## Test Steps

### Scenario 1: ADM-BOOK-002 — Book Management — Create Book

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | On the Book Management page, click the "New Entry" button. | Verify that the Create Book modal pops up, displaying all input fields (Title, Author, ISBN, Genre, Copies, Cover Image) and an "Add to Catalog" and "Cancel" button. |
| 2 | Submit the form without filling in any fields. | Verify that the browser blocks submission, displays a validation error on the first invalid field, and the book is not created. |
| 3 | Enter data only in some required fields and click Submit. | Verify that the browser blocks submission and displays a validation error on the next sequential empty required field. |
| 4 | Enter an ISBN that already exists in the system (e.g., `9781250266101`) along with other valid data, and click Submit. | Verify that a duplicate ISBN error message is shown and the book is not created. |
| 5 | Enter a negative number (e.g., `-1`) for the number of copies. | Verify that the browser blocks submission or a validation error is shown indicating that the number of copies must be between 0 and 1000. |
| 6 | Fill in all fields with valid, unique data and click "Add to Catalog". | Verify that the modal closes, the page refreshes, a success alert ("Book added to catalog successfully.") is displayed, and the new book is listed in the catalog. |
| 7 | On the Book Management list, search for the newly created book. | Verify that the new book appears in the list with the correct details. |

---

## Postconditions

- The new book is persisted in the database.
- The book is visible in the Book Management list.
- The book catalog count is incremented by one.