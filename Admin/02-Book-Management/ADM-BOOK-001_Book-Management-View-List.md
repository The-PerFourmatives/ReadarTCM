# ADM-BOOK-001 — Book Management — View Book List

**Test Case ID:** ADM-BOOK-001  
**Module:** Admin  
**Page:** Book Management — Index (`/Admin/BookManagement`)  
**Summary:** Verify that the admin can view, search, and filter the complete list of books in the system.  
**Priority:** High  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as an Administrator.
- At least one book record exists in the system.
- The Book Management page is accessible from the admin sidebar.

---

## Test Steps

### Scenario 1: ADM-BOOK-001 — Book Management — View Book List

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Navigate to the Book Management page. | Verify that the page loads and displays a list/table of all books in the system. |
| 2 | Observe the book list table columns. | Verify that relevant columns are present (e.g., Title, Author, Genre, Copies Available, Status). |
| 3 | Use the search bar to search for an existing book by title. | Verify that the list filters to show only books matching the search query. |
| 4 | Use the search bar to search for a book that does not exist. | Verify that the list shows an empty state message (e.g., "No books found"). |
| 5 | Apply a filter (e.g., by category, date, or availability) if filter controls are present. | Verify that the book list updates to only show books matching the applied filter. |
| 6 | Click the "New Entry" button. | Verify that the Create Book modal opens on the screen. |
| 7 | Click the "Edit Entry" action on an existing book. | Verify that the Edit Book modal opens on the screen, pre-filled with the book's details. |
| 8 | Observe pagination controls if there are many books. | Verify that pagination works correctly and navigates between pages of book records. |

---

## Postconditions

- The book list page remains in a functional state.
- Search and filter inputs are reset-able.
- No data is modified during this test.