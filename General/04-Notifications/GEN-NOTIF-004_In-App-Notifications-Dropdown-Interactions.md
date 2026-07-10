# GEN-NOTIF-004 — In-App Notifications (Dropdown Interactions and Polling)

**Test Case ID:** GEN-NOTIF-004  
**Module:** General — Notifications  
**Page:** Notification Dropdown in User Header and Admin Header  
**Summary:** Verify that the notification dropdown correctly handles interactions like mark-as-read, mark-all-as-read, count updates, state persistence, and background real-time updates via polling.  
**Priority:** Medium  
**Status:** ✅ Pass

---

## Preconditions

- A regular User or Admin account is logged in.
- The user has multiple unread notifications in their queue.
- The notification dropdown panel is accessible.

---

## Test Steps

### Scenario 1: Dropdown Interactions and Polling

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Open the notification dropdown (User or Admin) and click "Mark All as Read" (with multiple unread notifications). | Verify that all notifications are marked as read, and the unread badge count drops to zero or disappears. |
| 2 | Close and reopen the dropdown. | Verify that read status is persisted (read notifications do not reappear as unread). |
| 3 | With zero unread notifications, observe the icon. | Verify that no badge or a `0` badge is displayed. |
| 4 | Wait for the background polling interval (~30 seconds). | Verify that if a new notification arrives server-side, the badge and dropdown update without a full page reload. |

---

## Postconditions

- Unread counts and read statuses are persisted in the database.
- Polling retrieves new items dynamically.
