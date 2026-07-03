# USR-CTLG-001 — Book Catalog and Search

**Test Case ID:** USR-CTLG-001  
**Module:** User — Catalog  
**Page:** Catalog Home Page (`/Home/Index`) and Search Results Page (`/Home/Results`)  
**Summary:** Verify that users can browse the complete book catalog, search for books by title, author, category, or ISBN, apply multiple filters (availability, publication date, category), and sort results.  
**Priority:** High  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as a regular User.
- There are multiple books loaded in the system with different categories, publication dates, and copy availabilities.
- The Home/Catalog page is accessible directly via `/` or `/Home/Index`.

---

## Test Steps

### Scenario 1: General Catalog Page Loading

| # | Step | Expected Behavior |
|---|------|-------------------|
| A1 | Navigate to the Catalog page (`/Home/Index`). | Verify that the page loads correctly and displays a paginated list of books (up to 30 books per page). |
| A2 | Observe the book cards. | Verify that each card displays: Book cover image, Title, Author name(s), Category tags, Average Rating/Review Count, and status button (e.g., Reserve, Add to Wishlist). |
| A3 | Observe the side/top filter panel. | Verify that the filter options (Availability status, Category dropdown, Date filter, and Sort By options) are loaded correctly. |

---

### Scenario 2: Book Search

| # | Step | Expected Behavior |
|---|------|-------------------|
| B1 | Type an existing book title in the search box and click search. | Verify that the page redirects to `/Home/Results?query=...` displaying books matching the title. |
| B2 | Search for an existing author's name. | Verify that books written by that author are returned in the results. |
| B3 | Search for a specific category or ISBN. | Verify that the correct book(s) associated with that category or ISBN are displayed. |
| B4 | Search for a random string that doesn't match any record. | Verify that the system displays a clear message (e.g., "No results found"). |

---

### Scenario 3: Filtering the Catalog

| # | Step | Expected Behavior |
|---|------|-------------------|
| C1 | Select the "Available" status filter. | Verify that only books with at least one available copy are shown in the catalog. |
| C2 | Select the "Unavailable" status filter. | Verify that only books with all copies currently on loan are shown (often displaying an earliest due date hint). |
| C3 | Select a specific category from the category filter dropdown. | Verify that the catalog updates to display only books belonging to the selected category. |
| C4 | Select a date filter (e.g., "This Year", "2 Years Ago", "5 Years Ago"). | Verify that books are filtered based on their publication year accordingly. |

---

### Scenario 4: Sorting Results

| # | Step | Expected Behavior |
|---|------|-------------------|
| D1 | Select "Sort by Title". | Verify that books are reordered alphabetically by Title (A-Z). |
| D2 | Select "Sort by Author". | Verify that books are ordered alphabetically by Author's name. |
| D3 | Select "Sort by Oldest". | Verify that books are ordered by publication year ascending. |
| D4 | Select "Sort by Newest" (default). | Verify that books are ordered by publication year descending. |


---

## Postconditions

- Searching and filtering options can be combined without throwing SQL or runtime errors.
- The catalog state accurately reflects the current status and records in the database.