# USR-RESV-001 — Reservations — View Reservations

**Test Case ID:** USR-RESV-001  
**Module:** User — Reservations  
**Page:** Reservations (`/User/Reservation`)  
**Summary:** Verify that the user's Reservations page displays their current reservation queue with correct statuses, summary counts, and supports filtering, sorting, and pagination.  
**Priority:** High  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as a User who has at least one **pending** reservation and one **ready for pickup** reservation.
- The Reservations page is accessible from the user navigation.

---

## Test Steps

### Scenario 1: USR-RESV-001 — Reservations — View Reservations

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Navigate to the Reservations page. | Verify that the page loads and displays the user's current reservations. |
| 2 | Observe the summary counts. | Verify that the page shows: Ready for Pickup count, and Pending count, and Total Reservations — all matching the user's actual reservation data. |
| 3 | Observe each reservation entry in the list. | Verify that each entry shows: Book Title, Status, and Date Requested. |
| 4 | Apply the "Ready for Pickup" filter. | Verify that only reservations with `IsReadyForPickup = true` are shown. |
| 5 | Apply the "Pending" filter. | Verify that only reservations with `IsReadyForPickup = false` are shown. |
| 6 | Clear the filter (show All) with latest (default). | Verify that all reservations are displayed again. |
| 7 | Change the sort to "Oldest First". | Verify that reservations are reordered by `ReservedAt` ascending. |
| 8 | Change the sort to "Latest First" (default). | Verify that reservations are ordered by `ReservedAt` descending. |
| 9 | Navigate to the page as a user with no reservations. | Verify that an appropriate empty state message is displayed. |

---

## Postconditions

- No reservation data is modified during this test.
- Summary counts and list entries match the actual database records for the user.