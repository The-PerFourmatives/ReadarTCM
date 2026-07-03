# GEN-NOTIF-001 — In-App Notifications (Borrowing and Pickup Flows)

**Test Case ID:** GEN-NOTIF-001  
**Module:** General — Notifications  
**Page:** Notification Dropdown in User Header and Admin Header  
**Summary:** Verify that the system generates and routes correct in-app notifications for borrowing requests, approvals, denials, and cancellations, and that clicking them redirects to the correct pages.  
**Priority:** High  
**Status:** ⬜ Not Run

---

## Preconditions

- A regular User account is logged in.
- An Admin account is logged in.
- The notification bell/icon is visible in both the user and admin headers.

---

## Test Steps

### Scenario 1: User Request Borrow / Reservation

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | As the User, navigate to any available book details page and click the "Reserve" button. | Verify that the reservation request is submitted successfully. |
| 2 | Switch to the Admin session and observe the notification icon in the admin header. | Verify that the unread badge count on the admin's notification icon has incremented by 1. |
| 3 | Open the admin notification dropdown. | Verify that a new notification is displayed stating that a user has requested a book (e.g., "[User Name] has requested [Book Title]."). |
| 4 | Click the notification entry. | Verify that clicking the notification marks it as read, decrements the badge count, and redirects the admin to the **Admin Approvals** page (`/Approvals/Index`). |

---

### Scenario 2: Admin Approval (Ready for Pickup)

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | As Admin, navigate to the Approvals page and click "Approve" on the user's pending reservation request. | Verify that the approval is processed. |
| 2 | Switch to the User session and observe the notification icon in the user header. | Verify that the unread badge count on the user's notification icon has incremented by 1. |
| 3 | Open the user notification dropdown. | Verify that a new notification appears stating that the reservation is ready for pickup (e.g., "Your reservation for [Book Title] is ready for pickup!"). |
| 4 | Click the notification entry. | Verify that clicking the notification marks it as read, decrements the badge count, and redirects the user to the **User Reservations** page (`/Reservation/Index`). |

---

### Scenario 3: Admin Denial (Reservation Declined)

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | As the User, submit a new reservation request. | Verify the request is submitted. |
| 2 | As Admin, navigate to the Approvals page and click "Reject" / "Deny" on the user's request. | Verify the rejection is processed. |
| 3 | Switch to the User session and observe the notification icon in the user header. | Verify that the user's unread badge count has incremented by 1. |
| 4 | Open the user notification dropdown. | Verify that a new notification appears stating that the request was declined (e.g., "Your reservation for [Book Title] has been declined."). |
| 5 | Click the notification entry. | Verify that clicking the notification marks it as read, decrements the badge count, and redirects the user to the **User Reservations** page (`/Reservation/Index`). |

---

### Scenario 4: User Cancels a Ready-for-Pickup Reservation

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Ensure the User has a reservation with status "Ready for Pickup". | Verify that the reservation is visible on both the user reservations page and the admin pickup queue. |
| 2 | As the User, navigate to the Reservations page and click "Cancel" on the ready-for-pickup reservation. | Verify that the cancellation is processed on the user side. |
| 3 | Switch to the Admin session and observe the notification icon in the admin header. | Verify that the admin's unread badge count has incremented by 1. |
| 4 | Open the admin notification dropdown. | Verify that a new notification appears stating that the user cancelled their pickup (e.g., "[User Name] has cancelled their pickup for [Book Title]."). |
| 5 | Click the notification entry. | Verify that clicking the notification marks it as read, decrements the badge count, and redirects the admin to the **Admin Pickup** page (`/Pickup/Index?filter=cancelled` or `/Admin/Pickup?filter=cancelled`). |

---

## Postconditions

- All notification statuses are updated correctly in the database.
- Clicking any notification redirects the browser to the correct page.
