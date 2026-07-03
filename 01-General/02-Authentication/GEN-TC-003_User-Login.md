# GEN-TC-003 — User Login

**Test Case ID:** GEN-TC-003  
**Module:** General  
**Page:** Login Page (`/Account/Login`)  
**Summary:** Verify that a registered user can log in with valid credentials and is denied access with invalid credentials.  
**Priority:** Critical  
**Status:** ⬜ Not Run

---

## Preconditions

- The user has an existing, active account in the system.
- The user is not currently logged in.
- The login page is accessible via the Log In button or direct URL.

---

## Test Steps

### Scenario 2: Remember Me Toggle

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Navigate to the Login page. | Verify that the "Remember me" checkbox is unchecked by default. |
| 2 | Enter valid credentials, check the "Remember me" checkbox, and click Log In. | Verify that the user is successfully authenticated and redirected to the Homepage. |
| 3 | Close the browser window completely (all tabs and windows of that browser). | Verify that the browser closes. |
| 4 | Reopen the browser and navigate to the application URL. | Verify that the user remains authenticated and is not prompted to log in again. (Note: Ensure the browser is allowed to save cookie data). |
| 5 | Log out, return to the Login page, enter valid credentials, leave "Remember me" unchecked, and click Log In. | Verify that the user is successfully authenticated and logged in. |
| 6 | Close all tabs and windows of the browser completely (ensure no background processes remain). | Verify that the browser closes. |
| 7 | Reopen the browser and navigate back to the application URL. | Verify that the session cookie is cleared, and the user is redirected to the login page (unauthenticated). |

---

## Postconditions

- An authenticated session is established for the logged-in user.
- The user is redirected to the correct role-based page (Admin dashboard or User home).
- No session is established after a failed login attempt.
- Checking "Remember Me" persists the authentication cookie across browser sessions.