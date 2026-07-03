# USR-ACCT-001 — User Profile Page

**Test Case ID:** USR-ACCT-001  
**Module:** User — Account  
**Page:** Profile (`/Account/Profile`)  
**Summary:** Verify that the logged-in user's profile page displays accurate account information, borrowing statistics, and navigation to edit profile.  
**Priority:** Medium  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as a regular User.
- The user has at least some activity (e.g., loans, reservations) to verify stats.
- The Profile page is accessible from the user profile dropdown.

---

## Test Steps

### Scenario 1: USR-ACCT-001 — User Profile Page

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Log in as a User and navigate to the Profile page. | Verify that the page loads without errors and displays the user's profile. |
| 2 | Observe the displayed profile information. | Verify that the user's name, email, and profile picture (or default avatar) are correctly shown. |
| 3 | Observe any account statistics shown on the profile. | Verify that borrowing statistics (e.g., total borrowed, current loans, active reservations, wishlisted books) are displayed and reflect the user's actual data. |
| 4 | Look for an "Edit Information" button. | Verify that an Edit Information button is visible and navigates to the Edit Profile page when clicked. |
| 5 | Verify that the profile belongs to the currently logged-in user. | Verify that the displayed name and email match the credentials used to log in — no other user's data is shown. |

---

### Scenario 2: Direct Avatar Update via Camera Icon

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | On the Profile page, locate the profile picture and observe the bottom right of the image. | Verify that a camera icon button is visible. |
| 2 | Click the camera icon and select a valid image file (e.g., JPG, PNG). | Verify that the image is uploaded directly via AJAX, the preview on the page updates, and the header navigation avatar is immediately updated with the new photo without needing a full page reload. |
| 3 | Refresh the page. | Verify that the new avatar persists. |
| 4 | Click the camera icon again and select an invalid file type (e.g., PDF, EXE). | Verify that an error message is displayed on the screen, and the avatar remains unchanged. |

---

## Postconditions

- The user profile page displays accurate statistical data.
- Profile photo changes made directly via the camera icon are saved instantly in the database and updated on the navigation bar.