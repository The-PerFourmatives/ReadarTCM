# Readar Test Case Management (TCM)

This folder contains all **manual test cases** for the Readar Library Management System.

## Folder Structure

```
ReadarTCM/
├── General/                    # Public pages, auth, cross-cutting concerns
│   ├── 01-Landing-Page/           # Landing page display & responsiveness
│   ├── 02-Authentication/         # Registration, Login, Forgot/Reset Password
│   ├── 03-Navigation/             # Role-based access control
│   ├── 04-Notifications/          # In-app notifications & redirects (User + Admin)
│   └── 05-Email-Notifications/    # SMTP email notifications & formatting (All Triggers)
├── Admin/                      # Admin module test cases
│   ├── 01-Dashboard/
│   ├── 02-Book-Management/        # View list, Create, Edit, Delete book
│   ├── 03-Approvals/              # Approve / Reject requests
│   ├── 04-Pickup/                 # Process book pickups
│   ├── 05-Return/                 # Process book returns (Standard & Overdue)
│   └── 06-Fine-Management/        # Manage user fines and waive requests (Audits & Resolutions)
└── User/                       # User module test cases
    ├── 01-Catalog/                # Browse books, details, search, filter, sort
    ├── 02-Account/                # Profile, Edit Profile
    ├── 03-Loans/                  # Borrowing history and renewals
    ├── 04-Reservations/           # Request reservation, Cancel reservation
    ├── 05-Wishlist/               # Add, Remove, Reserve items from wishlist
    ├── 06-Fines/                  # View fine balance, Request waive
    └── 07-Reviews/                # Submit, Update, Display reviews
```

## List of Test Cases

### General Module
- [GEN-LNDP-001 — Landing Page Display](./General/01-Landing-Page/GEN-LNDP-001_Landing-Page-Display.md)
- [GEN-AUTH-001 — User Registration](./General/02-Authentication/GEN-AUTH-001_User-Registration.md)
- [GEN-AUTH-002 — User Login](./General/02-Authentication/GEN-AUTH-002_User-Login.md)
- [GEN-AUTH-003 — Forgot Password](./General/02-Authentication/GEN-AUTH-003_Forgot-Password.md)
- [GEN-NAV-001 — Navigation & Role-Based Access Control](./General/03-Navigation/GEN-NAV-001_Navigation-and-RBAC.md)
- [GEN-NOTIF-001 — In-App Notifications (Borrowing and Pickup Flows)](./General/04-Notifications/GEN-NOTIF-001_In-App-Notifications-Borrowing-and-Pickup-Flows.md)
- [GEN-NOTIF-002 — In-App Notifications (Due Date and Overdue Alerts)](./General/04-Notifications/GEN-NOTIF-002_In-App-Notifications-Due-Date-and-Overdue-Alerts.md)
- [GEN-NOTIF-003 — In-App Notifications (Waitlist Availability)](./General/04-Notifications/GEN-NOTIF-003_In-App-Notifications-Waitlist-Availability.md)
- [GEN-NOTIF-004 — In-App Notifications (Dropdown Interactions)](./General/04-Notifications/GEN-NOTIF-004_In-App-Notifications-Dropdown-Interactions.md)
- [GEN-EMAL-001 — Email Notifications (All Triggers)](./General/05-Email-Notifications/GEN-EMAL-001_Email-Notifications-All-Triggers.md)

### Admin Module
- [ADM-DSHB-001 — Admin Dashboard Overview](./Admin/01-Dashboard/ADM-DSHB-001_Admin-Dashboard-Overview.md)
- [ADM-BOOK-001 — Book Management — View Book List](./Admin/02-Book-Management/ADM-BOOK-001_Book-Management-View-List.md)
- [ADM-BOOK-002 — Book Management — Create Book](./Admin/02-Book-Management/ADM-BOOK-002_Book-Management-Create-Book.md)
- [ADM-BOOK-003 — Book Management — Edit Book](./Admin/02-Book-Management/ADM-BOOK-003_Book-Management-Edit-Book.md)
- [ADM-BOOK-004 — Book Management — Delete Book](./Admin/02-Book-Management/ADM-BOOK-004_Book-Management-Delete-Book.md)
- [ADM-APPR-001 — Approvals — View and Manage Loan Requests](./Admin/03-Approvals/ADM-APPR-001_Approvals-Manage-Requests.md)
- [ADM-PCKP-001 — Pickup — Process Book Pickup](./Admin/04-Pickup/ADM-PCKP-001_Pickup-Process-Pickup.md)
- [ADM-RTRN-001 — Return Processing](./Admin/05-Return/ADM-RTRN-001_Return-Processing.md)
- [ADM-RTRN-002 — Overdue Return Processing (Fines and Redirects)](./Admin/05-Return/ADM-RTRN-002_Overdue-Return-Processing.md)
- [ADM-FINE-001 — Fine Management — View and Audit User Fines](./Admin/06-Fine-Management/ADM-FINE-001_Fine-Management.md)
- [ADM-FINE-002 — Fine Management — Resolving Fines](./Admin/06-Fine-Management/ADM-FINE-002_Fine-Management-Resolving-Fines.md)

### User Module
- [USR-ACCT-001 — User Profile Page](./User/01-Account/USR-ACCT-001_User-Profile.md)
- [USR-ACCT-002 — Edit User Profile](./User/01-Account/USR-ACCT-002_Edit-Profile.md)
- [USR-CTLG-001 — Book Catalog and Search](./User/02-Catalog/USR-CTLG-001_Catalog-and-Search.md)
- [USR-CTLG-002 — Catalog Card Navigation and Actions](./User/02-Catalog/USR-CTLG-002_Catalog-Card-Actions.md)
- [USR-CTLG-003 — Book Details Page](./User/02-Catalog/USR-CTLG-003_Book-Details.md)
- [USR-REVW-001 — Book Reviews — Submit a Review](./User/03-Reviews/USR-REVW-001_Book-Review-Submit.md)
- [USR-REVW-002 — Book Reviews — Update an Existing Review](./User/03-Reviews/USR-REVW-002_Book-Review-Update.md)
- [USR-REVW-003 — Book Reviews — Display Reviews on Book Details](./User/03-Reviews/USR-REVW-003_Book-Review-Display.md)
- [USR-WSHL-001 — Wishlist Management](./User/04-Wishlist/USR-WSHL-001_Wishlist-Management.md)
- [USR-RESV-001 — Reservations — View Reservations](./User/05-Reservations/USR-RESV-001_Reservations-View.md)
- [USR-RESV-002 — Reservations — Reserve a Book](./User/05-Reservations/USR-RESV-002_Reservations-Reserve-Book.md)
- [USR-RESV-003 — Reservations — Cancel a Reservation](./User/05-Reservations/USR-RESV-003_Reservations-Cancel.md)
- [USR-LOAN-001 — Loans — View Loan History](./User/06-Loan-History/USR-LOAN-001_Loans-View-History.md)
- [USR-LOAN-002 — Loans — Renew a Book](./User/06-Loan-History/USR-LOAN-002_Loans-Renew-Book.md)
- [USR-FINE-001 — Fines — Fines History](./User/07-Fines/USR-FINE-001_Fines-Management.md)
- [USR-FINE-002 — Fines — Request a Waive](./User/07-Fines/USR-FINE-002_Fines-Request-Waive.md)



## Test Case Status Values

| Status | Meaning |
|--------|---------|
| ⬜ Not Run | Test has not been executed yet |
| ✅ Pass | Test passed all expected behaviors |
| ❌ Fail | Test failed one or more steps |
| ⏭️ Skipped | Test was intentionally skipped |
| 🔄 Blocked | Test cannot run due to a dependency issue |
