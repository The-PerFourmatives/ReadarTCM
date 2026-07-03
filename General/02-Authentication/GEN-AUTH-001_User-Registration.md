# GEN-AUTH-001 — User Registration

**Test Case ID:** GEN-AUTH-001  
**Module:** General  
**Page:** Register Page (`/Account/Register`)  
**Summary:** Verify that a new user can successfully create an account using valid information.  
**Priority:** Critical  
**Status:** ⬜ Not Run

---

## Preconditions

- The user is not logged in.
- The email address used for registration does not already exist in the system.
- The registration page is accessible via the Sign Up button or direct URL.

---

## Test Steps

### Scenario 1: GEN-AUTH-001 — User Registration

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Navigate to the Register page. | Verify that the registration form is displayed with all required fields (Full Name, Email, Password, Confirm Password, etc.). |
| 2 | Leave all fields blank. | Verify that the 'Create Account' button is disabled. |
| 3 | Enter an invalid email format (e.g., `notanemail`). | Verify that a validation error indicating an invalid email format is shown. |
| 4 | Enter a password that does not meet complexity requirements. | Verify that a password strength/complexity error message is displayed. |
| 5 | Enter a password and a non-matching confirm password value. | Verify that an error message is shown stating that passwords do not match. |
| 6 | Fill in all fields with valid data and click Create Account. | Verify that the form submits successfully and the user is redirected (e.g., to login or a confirmation page). |
| 7 | Attempt to register again using the same email address. | Verify that an error message is displayed indicating the email is already in use. |

---

## Postconditions

- The new user account is created and stored in the database.
- The user is not automatically logged in after registration (or is redirected to login — confirm expected behavior).
- No duplicate accounts are created.