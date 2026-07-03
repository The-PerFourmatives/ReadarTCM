# USR-CTLG-002 — Catalog Card Navigation and Actions

**Test Case ID:** USR-CTLG-002  
**Module:** User — Catalog  
**Page:** Catalog Home Page (`/Home/Index`) and Search Results Page (`/Home/Results`)  
**Summary:** Verify that users can click book cards in the catalog list to view details, and initiate quick borrow or waitlist queue requests directly from the book cards.  
**Priority:** High  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as a regular User.
- There are multiple books loaded in the system with different copy availabilities.
- The Home/Catalog page is loaded.

---

## Test Steps

### Scenario 1: Navigation to Book Details

| # | Step | Expected Behavior |
|---|------|-------------------|
| A1 | Click on a book cover image or the book title of any card in the catalog. | Verify that the browser redirects to the **Book Details** page (`/Book/Details/{id}`) of the selected book. |

---

### Scenario 2: Request Borrow or Reserve (Waitlist Queue) from Catalog Card

| # | Step | Expected Behavior |
|---|------|-------------------|
| B1 | Locate a book card with available copies and click the "Reserve Book" button. | Verify that a borrow/reservation request is submitted, a success toast is shown ("Book reservation request placed successfully."), and the button status updates. |
| B2 | Locate a book card that has **no available copies** (all copies on loan) and click the "Reserve Book" button. | Verify that the system places the user in the waitlist queue (adds a pending reservation), showing a confirmation toast, and the status changes to indicate the hold is queued. |

---

## Postconditions

- Clicking book cards redirects to the details page without throwing errors.
- Quick action requests (borrow/waitlist) from the catalog cards create corresponding pending reservation records in the database.
