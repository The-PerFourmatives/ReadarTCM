# ADM-TC-007 — Pickup — Process Book Pickup

**Test Case ID:** ADM-TC-007  
**Module:** Admin  
**Page:** Pickup (`/Admin/Pickup`)  
**Summary:** Verify that an admin can view approved loan requests ready for pickup and mark them as picked up.  
**Priority:** Critical  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as an Administrator.
- At least one approved loan request exists with a status of "Ready for Pickup" or equivalent.
- The Pickup page is accessible from the admin sidebar.

---

## Test Steps

### Scenario 1: ADM-TC-007 — Pickup — Process Book Pickup

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Navigate to the Pickup page. | Verify that the page loads and displays a list of reservations that are ready for pickup. |
| 2 | Observe the pickup list columns. | Verify that relevant columns are displayed (e.g., Requester's Name, Book Title, Requested Date, etc.). |
| 3 | Search for a specific user or book in the pickup list. | Verify that the list filters correctly to match the search input. |
| 4 | Click the "Picked Up" action for a record. | Verify that a confirmation prompt appears (if applicable), and upon confirmation, the record's status updates to "Picked Up" and "Active" (in user's loans page). |
| 5 | Verify the updated record. | Verify that the processed pickup no longer appears in the pending pickup list. |
| 6 | Navigate to the user's Loans page. | Verify that the loan is now listed as active with the correct start date and expected return date. |
| 7 | Check the book's available copy count. | Verify that the available copies for the picked-up book have decreased by one. |

---

## Postconditions

- The loan record is updated to Active/Borrowed status with the pickup date recorded.
- The book's available copy count is decremented.
- The user is notified that their book has been processed for pickup.