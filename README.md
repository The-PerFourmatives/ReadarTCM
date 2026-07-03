# Readar Test Case Management (TCM)

This folder contains all **manual test cases** for the Readar Library Management System.

## Folder Structure

```
ReadarTCM/
├── 01-General/                    # Public pages, auth, cross-cutting concerns
│   ├── 01-Landing-Page/           # Landing page display & responsiveness
│   ├── 02-Authentication/         # Registration, Login, Forgot/Reset Password
│   ├── 03-Navigation/             # Role-based access control
│   ├── 04-Notifications/          # In-app notifications & redirects (User + Admin)
│   └── 05-Email-Notifications/    # SMTP email notifications & formatting (All Triggers)
├── 02-Admin/                      # Admin module test cases
│   ├── 01-Dashboard/
│   ├── 02-Book-Management/        # View list, Create, Edit, Delete book
│   ├── 03-Approvals/              # Approve / Reject requests
│   ├── 04-Pickup/                 # Process book pickups
│   ├── 05-Return/                 # Process book returns (Standard & Overdue)
│   └── 06-Fine-Management/        # Manage user fines and waive requests (Audits & Resolutions)
└── 03-User/                       # User module test cases
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
- [GEN-TC-001 — Landing Page Display](./01-General/01-Landing-Page/GEN-TC-001_Landing-Page-Display.md)
- [GEN-TC-002 — User Registration](./01-General/02-Authentication/GEN-TC-002_User-Registration.md)
- [GEN-TC-003 — User Login](./01-General/02-Authentication/GEN-TC-003_User-Login.md)
- [GEN-TC-004 — Forgot Password](./01-General/02-Authentication/GEN-TC-004_Forgot-Password.md)
- [GEN-TC-005 — Navigation & Role-Based Access Control](./01-General/03-Navigation/GEN-TC-005_Navigation-and-RBAC.md)
- [GEN-TC-006 — In-App Notifications (Borrowing and Pickup Flows)](./01-General/04-Notifications/GEN-TC-006_In-App-Notifications-Borrowing-and-Pickup-Flows.md)
- [GEN-TC-007 — In-App Notifications (Due Date and Overdue Alerts)](./01-General/04-Notifications/GEN-TC-007_In-App-Notifications-Due-Date-and-Overdue-Alerts.md)
- [GEN-TC-008 — In-App Notifications (Waitlist Availability)](./01-General/04-Notifications/GEN-TC-008_In-App-Notifications-Waitlist-Availability.md)
- [GEN-TC-009 — In-App Notifications (Dropdown Interactions)](./01-General/04-Notifications/GEN-TC-009_In-App-Notifications-Dropdown-Interactions.md)
- [GEN-TC-010 — Email Notifications (All Triggers)](./01-General/05-Email-Notifications/GEN-TC-010_Email-Notifications-All-Triggers.md)

### Admin Module
- [ADM-TC-001 — Admin Dashboard Overview](./02-Admin/01-Dashboard/ADM-TC-001_Admin-Dashboard-Overview.md)
- [ADM-TC-002 — Book Management — View Book List](./02-Admin/02-Book-Management/ADM-TC-002_Book-Management-View-List.md)
- [ADM-TC-003 — Book Management — Create Book](./02-Admin/02-Book-Management/ADM-TC-003_Book-Management-Create-Book.md)
- [ADM-TC-004 — Book Management — Edit Book](./02-Admin/02-Book-Management/ADM-TC-004_Book-Management-Edit-Book.md)
- [ADM-TC-005 — Book Management — Delete Book](./02-Admin/02-Book-Management/ADM-TC-005_Book-Management-Delete-Book.md)
- [ADM-TC-006 — Approvals — View and Manage Loan Requests](./02-Admin/03-Approvals/ADM-TC-006_Approvals-Manage-Requests.md)
- [ADM-TC-007 — Pickup — Process Book Pickup](./02-Admin/04-Pickup/ADM-TC-007_Pickup-Process-Pickup.md)
- [ADM-TC-008 — Return Processing](./02-Admin/05-Return/ADM-TC-008_Return-Processing.md)
- [ADM-TC-009 — Overdue Return Processing (Fines and Redirects)](./02-Admin/05-Return/ADM-TC-009_Overdue-Return-Processing.md)
- [ADM-TC-010 — Fine Management — View and Audit User Fines](./02-Admin/06-Fine-Management/ADM-TC-010_Fine-Management.md)
- [ADM-TC-011 — Fine Management — Resolving Fines](./02-Admin/06-Fine-Management/ADM-TC-011_Fine-Management-Resolving-Fines.md)

### User Module
- [USR-TC-001 — Book Catalog and Search](./03-User/01-Catalog/USR-TC-001_Catalog-and-Search.md)
- [USR-TC-002 — Book Details Page](./03-User/01-Catalog/USR-TC-002_Book-Details.md)
- [USR-TC-003 — User Profile Page](./03-User/02-Account/USR-TC-003_User-Profile.md)
- [USR-TC-004 — Edit User Profile](./03-User/02-Account/USR-TC-004_Edit-Profile.md)
- [USR-TC-005 — Loans — View Loan History](./03-User/03-Loans/USR-TC-005_Loans-View-History.md)
- [USR-TC-006 — Loans — Renew a Book](./03-User/03-Loans/USR-TC-006_Loans-Renew-Book.md)
- [USR-TC-007 — Reservations — View Reservations](./03-User/04-Reservations/USR-TC-007_Reservations-View.md)
- [USR-TC-008 — Reservations — Reserve a Book](./03-User/04-Reservations/USR-TC-008_Reservations-Reserve-Book.md)
- [USR-TC-009 — Reservations — Cancel a Reservation](./03-User/04-Reservations/USR-TC-009_Reservations-Cancel.md)
- [USR-TC-010 — Wishlist Management](./03-User/05-Wishlist/USR-TC-010_Wishlist-Management.md)
- [USR-TC-011 — Fines History and Waive Requests](./03-User/06-Fines/USR-TC-011_Fines-Management.md)
- [USR-TC-012 — Book Reviews — Submit a Review](./03-User/07-Reviews/USR-TC-012_Book-Review-Submit.md)
- [USR-TC-013 — Book Reviews — Update an Existing Review](./03-User/07-Reviews/USR-TC-013_Book-Review-Update.md)
- [USR-TC-014 — Book Reviews — Display Reviews on Book Details](./03-User/07-Reviews/USR-TC-014_Book-Review-Display.md)

## Test Case Status Values

| Status | Meaning |
|--------|---------|
| ⬜ Not Run | Test has not been executed yet |
| ✅ Pass | Test passed all expected behaviors |
| ❌ Fail | Test failed one or more steps |
| ⏭️ Skipped | Test was intentionally skipped |
| 🔄 Blocked | Test cannot run due to a dependency issue |
