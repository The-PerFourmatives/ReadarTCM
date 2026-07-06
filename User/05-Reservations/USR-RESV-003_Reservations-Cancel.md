**Test Case ID:** USR-RESV-003  
**Module:** User — Reservations  
**Page:** Reservations (`/User/Reservation`)  
**Summary:** Verify that a user can cancel an active reservation (whether it's pending approval or already ready for pickup) and that the cancellation reflects correctly in the system.  
**Priority:** High  
**Status:** ✅ Pass

---

## Preconditions

- The tester is logged in as a regular User.
- The user has a pending reservation request (status "Pending").
- The user has a reservation ready for pickup (status "Ready for Pickup").
- The Reservations page is accessible.

---

## Test Steps

### Scenario 1: USR-RESV-003 — Reservations — Cancel a Reservation

| # | Step | Expected Behavior |
|---|------|-------------------|
| A1 | Navigate to the Reservations page. | Verify that the pending reservation request is displayed in the list. |
| A2 | Click the "Cancel Reservation" button on the pending reservation. | Verify that a confirmation prompt appears, and upon confirming, a success message is shown. |
| A3 | Observe the reservation list. | Verify that the cancelled reservation is removed from the active list. |

### Scenario 2: USR-RESV-003 — Reservations — Cancel a Reservation (Ready for Pickup)

| # | Step | Expected Behavior |
|---|------|-------------------|
| B1 | Locate a reservation with status "Ready for Pickup". | Verify that a "Cancel Reservation" action is visible and enabled. |
| B2 | Click the "Cancel Reservation" button for the ready-for-pickup reservation. | Verify that a confirmation prompt appears and the cancellation is processed. |
| B3 | Observe the reservation list. | Verify that the cancelled reservation is removed from the active list. |
| B4 | Switch to the Admin session and inspect the active Pickup list. | Verify that the cancelled item is visible in the cancelled pickup list. |

---

## Postconditions

- The reservation status is set to Cancelled from the active list in the database.
- The admin is notified of the cancellation if it was in the "Ready for Pickup" state.
- Book copies linked to the reservation are released back to availability or assigned to the next waitlisted user.
