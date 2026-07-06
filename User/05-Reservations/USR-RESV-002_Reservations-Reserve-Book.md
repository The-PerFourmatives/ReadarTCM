# USR-RESV-002 — Reservations — Reserve a Book

**Test Case ID:** USR-RESV-002  
**Module:** User — Reservations  
**Page:** Book Details (`/Books/Details/{id}`) → triggers `POST /Reservation/Reserve`  
**Summary:** Verify that a user can successfully place a reservation request for an available book, and that the system correctly prevents duplicate or invalid reservation requests.  
**Priority:** Critical  
**Status:** ✅ Pass

---

## Preconditions

- The tester is logged in as a User.
- At least one book with available copies exists in the catalog.
- At least one book that the user has **already reserved** exists (to test duplicate prevention).
- The Book Details page is accessible from the catalog/home page.

---

## Test Steps

### Scenario 1: USR-RESV-002 — Reservations — Reserve a Book

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Navigate to the Details page of a book with available copies. | Verify that a "Reserve" or "Request" button is visible and enabled. |
| 2 | Click the Reserve button. | Verify that a success response is returned and the button state updates. |
| 3 | Navigate to the Reservations page. | Verify that the new reservation appears in the list with a "Pending" status. |
| 4 | Attempt to reserve the same book again. | Verify that the button state in that specified book details page is "Cancel Reservation". |
| 5 | Navigate to the Details page of a book that has **no available copies** (all on loan). | Verify that the Reserve button shows "Reserve Book" state. |
| 6 | Attemt to reserve a book with no copies available | Verify that a success message is shown including the date of the copy due back. |
| 7 | Attempt to reserve a book when the user already has the maximum number of active reservations (shared max with the loans). | Verify that an appropriate error message is shown and the new reservation is not created. |

---

## Postconditions

- A new reservation record is created in the database with Pending status.
- The admin receives an in-app notification about the new reservation request (see GEN-NOTIF-002 Scenario A).
- No duplicate reservations exist for the same user and book.
