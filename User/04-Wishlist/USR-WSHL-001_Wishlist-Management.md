# USR-WSHL-001 — Wishlist Management

**Test Case ID:** USR-WSHL-001  
**Module:** User — Wishlist  
**Page:** Wishlist page (`/Wishlist`)  
**Summary:** Verify that a user can add books to their wishlist from the catalog, view and manage their wishlist items, filter/sort them, reserve available items, and clear the wishlist.  
**Priority:** High  
**Status:** ✅ Pass

---

## Preconditions

- The tester is logged in as a regular User.
- There are books in the catalog (some available, some completely on loan).
- The Wishlist page is accessible from the user navigation.

---

## Test Steps

### Scenario 1: Adding to Wishlist

| # | Step | Expected Behavior |
|---|------|-------------------|
| A1 | Navigate to a book details page and click the "Add to Wishlist" icon button. | Verify that a success message is returned (e.g., "Book added to wishlist successfully.") and the button label changes to indicate it is wishlisted. |
| A2 | Click "Add to Wishlist" icon button again on the same book if possible. | Verify that the wishlist is removed and the button label reverts back to the previous state. |

---

### Scenario 2: Viewing and Sorting Wishlist

| # | Step | Expected Behavior |
|---|------|-------------------|
| B1 | Navigate to the Wishlist page. | Verify that the page loads and displays all the books added by the user. |
| B2 | Observe metadata for each book. | Verify that each book card completely mirrors the cards in the catalog page. |
| B3 | Change the sort filter to "Oldest First". | Verify that the items are sorted by the date they were added to the wishlist in ascending order. |
| B4 | Change the sort filter to "Latest First" (default). | Verify that the items are sorted by date added descending. |
| B5 | Filter the list by "Available" status. | Verify that only wishlisted books that have at least one copy with status "Available" are shown. |
| B6 | Filter the list by "Unavailable" status. | Verify that only wishlisted books with no available copies are shown. |

---

### Scenario 3: Removing from Wishlist

| # | Step | Expected Behavior |
|---|------|-------------------|
| C1 | On a book card in the Wishlist page, click the "Remove" icon button. | Verify that the book is removed from the wishlist, the page updates, and a success message is displayed. |
| C2 | Click the "Remove All" button at the top of the page. | Verify that a confirmation modal/prompt appears and upon confirming, all books are removed, showing an empty state. |

---

### Scenario 4: Reserving from Wishlist

| # | Step | Expected Behavior |
|---|------|-------------------|
| D1 | On an available book in the Wishlist page, click the "Reserve" button. | Verify that a reservation request is successfully submitted (creating a pending reservation) and the button state updates, respecting the unified limit check (combined loans + reservations cannot exceed 3). |
| D2 | Click the "Reserve All" button (if available). | Verify that the system attempts to reserve all books in the wishlist that are currently "Available", up to the remaining capacity of the user's active quota (Active Loans + Active Reservations <= 3), and returns a summary message (e.g., "Successfully reserved X book(s)."). |

---

## Postconditions

- User's wishlist updates are saved in the database.
- Reservation requests made from the wishlist are sent to the approvals queue.
- Clearing the wishlist successfully deletes all records for the user.
