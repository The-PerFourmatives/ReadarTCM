# USR-FINE-002 — Fines — Request a Waive

**Test Case ID:** USR-FINE-002  
**Module:** User — Fines  
**Page:** Fines (`/Fines`)  
**Summary:** Verify that the user can request to waive an unpaid fine with a reason and the fine status updates to pending review (WaiveRequested).  
**Priority:** High  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as a regular User.
- The user has at least one fine with status "Unpaid".
- The Fines page is accessible from the user navigation.

---

## Test Steps

### Scenario 1: USR-FINE-002 — Fines — Requesting a Waive

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Locate an "Unpaid" fine in the list. | Verify that a "Request Waive" button or action is visible and enabled. |
| 2 | Click the "Request Waive" button. | Verify that a form or text area appears prompting the user to enter a reason for the waive. |
| 3 | Submit the waive request with an empty reason field (if mandatory). | Verify that validation prevents submission and requests a reason. |
| 4 | Enter a valid reason (e.g., "Medical emergency, book returned late") and submit. | Verify that the page redirects/refreshes, showing a success message and the fine's status updates to "WaiveRequested". |
| 5 | Attempt to click "Request Waive" again on the same fine. | Verify that the button is disabled or not visible in the actions. |

---

## Postconditions

- The waive request is stored in the database with the user's provided reason.
- The status of the fine is updated to "WaiveRequested".
- The admin is notified of the pending waive request (see GEN-NOTIF-002).
