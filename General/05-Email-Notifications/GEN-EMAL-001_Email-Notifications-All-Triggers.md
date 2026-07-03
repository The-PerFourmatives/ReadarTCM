# GEN-EMAL-001 — Email Notifications (All Triggers)

**Test Case ID:** GEN-EMAL-001  
**Module:** General — Email Notifications  
**Page:** Triggered automatically by system events and the background service  
**Summary:** Verify that the system sends correctly formatted HTML email notifications to users for all applicable triggers: upcoming due date, overdue book alert, and reservation ready for pickup.  
**Priority:** High  
**Status:** ⬜ Not Run

---

## Preconditions

- The test user account is registered with a valid, active Gmail account (or personal email) belonging to the tester, ensuring they can receive the automated emails.
- The SMTP email service is configured and operational in the test environment.
- A separate Admin session is available for the Reservation Approved trigger.
- The background `DailyFineCalculationService` (or equivalent reminder service) is running.

---

## Test Steps

### Scenario 1: Reservation Ready for Pickup Email

| # | Step | Expected Behavior |
|---|------|-------------------|
| A1 | As the User, submit a reservation/loan request for an available book. | Verify the request is submitted successfully. |
| A2 | As Admin, approve the reservation on the Approvals page. | Verify the approval is confirmed on the admin side. |
| A3 | Open the test user's email inbox. | Verify that an email is received with the subject **"Reservation Ready for Pickup"**. |
| A4 | Open the email and inspect the HTML formatting. | Verify that the email is rendered in HTML format and contains the site name "Readar". |
| A5 | Inspect the email body. | Verify that the message clearly communicates that the reservation has been approved and the book is ready for pickup. |
| A6 | Inspect the email footer. | Verify that the footer contains "© [Current Year] Readar. All rights reserved." |
| A7 | Verify the sender address. | Verify that the From address matches the configured `FromEmail` setting (not unknown or generic). |
| A8 | Verify no duplicate emails. | Verify that only one email is sent per approval action — no duplicates in the inbox. |

---

### Scenario 2: Upcoming Due Date Reminder Email

| # | Step | Expected Behavior |
|---|------|-------------------|
| B1 | Confirm the test User has an active loan with a due date within the reminder window (e.g., 1–2 days before due). | Verify the loan record exists and its due date qualifies. |
| B2 | Wait for the background reminder service to execute (or trigger manually). | Verify the service executes without errors in the application logs. |
| B3 | Open the test user's email inbox. | Verify that an email is received with the subject **"Upcoming Due Date Reminder"**. |
| B4 | Open the email and inspect the HTML formatting. | Verify the Readar branding, readable body text, and proper footer are all rendered correctly. |
| B5 | Inspect the email body content. | Verify that the message conveys the due date reminder clearly (including book details if the message is populated). |
| B6 | Verify only one reminder is sent per cycle. | Verify that the inbox does not contain duplicate reminder emails for the same loan within the same trigger window. |

> [!NOTE]  
> Contact one of the developers to manually modify the due dates accordingly via SSMS.

---

### Scenario 3: Overdue Book Alert Email

| # | Step | Expected Behavior |
|---|------|-------------------|
| C1 | Confirm the test User has a loan where the due date has passed and the book has not been returned. | Verify the overdue loan record exists. |
| C2 | Wait for the background overdue service to execute (or trigger manually). | Verify the service executes without errors. |
| C3 | Open the test user's email inbox. | Verify that an email is received with the subject **"Overdue Book Alert"**. |
| C4 | Open the email and inspect the HTML formatting. | Verify the Readar branding, body with overdue message, and footer are rendered correctly. |
| C5 | Inspect the email body content. | Verify that the message informs the user that their book is overdue and references any associated fine information (if included in the message). |
| C6 | Verify no duplicate emails. | Verify that only one overdue alert is sent per overdue loan per trigger cycle. |

> [!NOTE]  
> Contact one of the developers to manually modify the due dates accordingly via SSMS.

---

### Scenario 4: General Email Quality Checks (applies to all scenarios above)

| # | Step | Expected Behavior |
|---|------|-------------------|
| D1 | Inspect the HTML body of any received email. | Verify that the email does not show raw HTML tags — it renders as styled HTML in the email client. |
| D2 | Check the email layout and readability. | Verify that all text is legible, formatted correctly, and structured cleanly. |
| D3 | Check that the email is responsive. | Verify that the email renders legibly on both desktop and mobile email clients. |
| D4 | Verify delivery time. | Verify that all emails are received within a reasonable time (< 2 minutes under normal SMTP conditions). |

---

## Postconditions

- All email notifications are delivered to the correct user email address.
- Emails are HTML-formatted and match the Readar brand design.
- In-app notifications corresponding to the same events (`ReservationApproved`, `DueDateReminder`, `OverdueAlert`) are also created in the user's in-app notification list.
- No duplicate emails are sent per trigger event.
