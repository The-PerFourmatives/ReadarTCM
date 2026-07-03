# USR-CTLG-003 — Book Details Page

**Test Case ID:** USR-CTLG-003  
**Module:** User — Catalog  
**Page:** Book Details (`/Book/Details/{id}`)  
**Summary:** Verify that the Book Details page displays accurate information (metadata, cover image, availability), allows users to submit borrow/waitlist requests, add/remove items from the wishlist, and displays ratings/reviews correctly.  
**Priority:** High  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as a regular User.
- The user has navigated to the details page of a book.
- **Scenario 1:** The book has at least one copy with status `Available`.
- **Scenario 2:** The book has `0` available copies (all copies are currently `Borrowed` or `Reserved`).

---

## Test Steps

### Scenario 1: Book Details with Available Copies

| # | Step | Expected Behavior |
|---|------|-------------------|
| A1 | Navigate to the details page of a book with available copies. | Verify that the page loads without errors and display correct metadata (Title, Authors, Categories, Publication Year, Description, etc.). |
| A2 | Observe the status and action buttons. | Verify that the page shows the number of available copies and a "Reserve Book" button is visible and active. |
| A3 | Observe the wishlist option. | Verify that the "Add to Wishlist" option is visible and active. |
| A4 | Click the "Reserve Book" button. | Verify that a success message is shown ("Book reservation request placed successfully.") and the button state updates. |

---

### Scenario 2: Book Details with No Available Copies (Waitlist Queue)

| # | Step | Expected Behavior |
|---|------|-------------------|
| B1 | Navigate to the details page of a book that has no copies available. | Verify that the page metadata loads correctly. |
| B2 | Observe the status and action buttons. | Verify that the page indicates that all copies are currently checked out/unavailable, and the "Reserve Book" button remains active to allow queueing. |
| B3 | Click the "Reserve Book" button. | Verify that a success message is shown indicating that you have joined the waitlist queue for this book, and a queued reservation is created. |

---

### Scenario 3: Verify Reviews

| # | Step | Expected Behavior |
|---|------|-------------------|
| C1 | Scroll down to the Reviews section on the details page. | Verify that the average rating star indicator and total review count are displayed. |
| C2 | Observe the list of reviews. | Verify that individual reviews are displayed with the reviewer's name, rating (stars), review comment/text, and date submitted. |

---

## Postconditions

- Reservation and wishlist actions performed on the details page are saved in the database.
- The catalog availability and status update accordingly.
