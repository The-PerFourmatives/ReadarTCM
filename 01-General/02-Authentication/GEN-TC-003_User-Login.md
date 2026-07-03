# GEN-TC-003 — User Login

**Test Case ID:** GEN-TC-003  
**Module:** General — Authentication  
**Page:** Login Page (`/Account/Login`)  
**Summary:** Verify that a registered user can log in with valid credentials, is denied access with invalid credentials, and that the "Remember me" functionality persists sessions correctly.  
**Priority:** Critical  
**Status:** ⬜ Not Run

---

## Preconditions

- The user has an existing, active account in the system (at least one Regular User and one Admin).
- The user is not currently logged in.
- The Login page is accessible via the "Log In" button or direct URL (`/Account/Login`).

---

## Test Steps

### Scenario 1: Successful Login with Valid Credentials

| # | Step | Expected Behavior |
|---|------|-------------------|
| A1 | Navigate to the Login page. | Verify that the page loads correctly and displays inputs for Email, Password, and a "Remember me" checkbox. |
| A2 | Enter the credentials of a registered regular User and click the "Log In" button. | Verify that the user is successfully authenticated and redirected to the **User Homepage** (`/Home/Index`). |
| A3 | Log out, return to the Login page, enter the credentials of a registered Administrator, and click "Log In". | Verify that the user is successfully authenticated and redirected to the **Admin Dashboard** (`/Admin/Dashboard`). |

---

### Scenario 2: Invalid Credentials and Validation Rules

| # | Step | Expected Behavior |
|---|------|-------------------|
| B1 | On the Login page, leave the Email and Password fields empty and click the "Log In" button. | Verify that the submit action is blocked at the first empty field sequentially (client-side validation), or displays validation errors under the empty required fields. |
| B2 | Enter a valid email format but incorrect password, and click "Log In". | Verify that login fails, and an error message is displayed: `"Invalid email or password."` |
| B3 | Enter a non-existent email and any password, and click "Log In". | Verify that login fails, and an error message is displayed: `"Invalid email or password."` |

---

### Scenario 3: Remember Me Toggle

| # | Step | Expected Behavior |
|---|------|-------------------|
| C1 | Navigate to the Login page. | Verify that the "Remember me" checkbox is unchecked by default. |
| C2 | Enter valid credentials, check the "Remember me" checkbox, and click "Log In". | Verify that the user is successfully authenticated and redirected to the Homepage. |
| C3 | Close the browser window completely (all tabs and windows of that browser). | Verify that the browser closes. |
| C4 | Reopen the browser and navigate to the application URL. | Verify that the user remains authenticated (session persisted) and is not prompted to log in again. |
| C5 | Log out, return to the Login page, enter valid credentials, leave "Remember me" unchecked, and click "Log In". | Verify that the user is successfully authenticated and logged in. |
| C6 | Close all tabs and windows of the browser completely (ensure no background processes remain). | Verify that the browser closes. |
| C7 | Reopen the browser and navigate back to the application URL. | Verify that the session cookie has expired, and the user is redirected to the login page (unauthenticated). |

---

## Postconditions

- An authenticated session is established for the logged-in user.
- The user is redirected to the correct role-based page.
- No session is established after a failed login attempt.
- Checking "Remember Me" persists the authentication cookie across browser sessions, while leaving it unchecked behaves as a standard session cookie.