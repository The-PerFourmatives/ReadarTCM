# GEN-TC-007 — In-App Notifications (Due Date and Overdue Alerts)

**Test Case ID:** GEN-TC-007  
**Module:** General — Notifications  
**Page:** Notification Dropdown in User Header  
**Summary:** Verify that the system generates and routes correct in-app notifications to warn the user of an upcoming due date or alert them when a book becomes overdue.  
**Priority:** High  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as a regular User.
- The User has an active borrowing record in their account.
- The notification bell/icon is visible in the user header.

---

## Test Steps

### Scenario 1: Due Date Reminder

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Ensure the User has an active loan with a due date within the reminder window (e.g., 1–2 days before due). | Verify the active loan record exists. |
| 2 | Wait for the background reminder service to execute (or trigger manually). | Verify the service runs without errors. |
| 3 | As the User, observe the notification icon. | Verify that the unread badge count has incremented by 1. |
| 4 | Open the notification dropdown and click the "Due Date Reminder" notification. | Verify that clicking the notification marks it as read, decrements the badge count, and redirects the user to the **User Loans** page (`/Loans/Index`). |

> [!NOTE]  
> Contact one of the developers to manually modify the due dates accordingly via SSMS.

---

### Scenario 2: Overdue Alert

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Ensure the User has a loan where the due date has already passed and the book has not been returned. | Verify the overdue loan record exists. |
| 2 | Wait for the background overdue service to execute. | Verify the service runs without errors. |
| 3 | As the User, observe the notification icon. | Verify that the unread badge count has incremented by 1. |
| 4 | Open the notification dropdown and click the "Overdue Alert" notification. | Verify that clicking the notification marks it as read, decrements the badge count, and redirects the user to the **User Loans** page (`/Loans/Index`). |

> [!NOTE]  
> Contact one of the developers to manually modify the due dates accordingly via SSMS.

---

## Postconditions

- Due date reminder and overdue alerts are persisted in the database.
- Clicking any alert redirects the user to the loans history page.
