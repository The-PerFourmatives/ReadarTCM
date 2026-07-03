# GEN-NOTIF-003 — In-App Notifications (Waitlist Availability)

**Test Case ID:** GEN-NOTIF-003  
**Module:** General — Notifications  
**Page:** Notification Dropdown in User Header  
**Summary:** Verify that the system generates and routes an in-app notification when a book the user placed on hold (waitlisted) becomes available.  
**Priority:** High  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as a regular User.
- The User has placed a hold/reservation request on a book that is completely on loan (unavailable).
- The notification bell/icon is visible in the user header.

---

## Test Steps

### Scenario 1: Reservation Available (Waitlisted Book)

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Ensure the User has placed a hold/reservation on a book that was previously unavailable (all copies on loan). | Verify the hold/waitlist record exists. |
| 2 | Have another user return the book so a copy becomes available, or trigger availability via admin. | Verify the book copy status is now available. |
| 3 | As the User, observe the notification icon in the header. | Verify that the unread badge count has incremented by 1. |
| 4 | Open the notification dropdown and click the "Reservation Available" notification. | Verify that clicking the notification marks it as read, decrements the badge count, and redirects the user to the **User Reservations** page (`/Reservation/Index`). |

---

## Postconditions

- The waitlist availability notification status is updated correctly in the database.
- Clicking the notification redirects the user to the reservations page.
