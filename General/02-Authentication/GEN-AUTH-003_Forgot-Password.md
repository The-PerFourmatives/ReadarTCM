# GEN-AUTH-003 — Forgot Password

**Test Case ID:** GEN-AUTH-003  
**Module:** General  
**Page:** Forgot Password (`/Account/ForgotPassword`)  
**Summary:** Verify that a user can request a password reset link via email and successfully reset their password.  
**Priority:** High  
**Status:** ✅ Pass

---

## Preconditions

- The user has an existing account registered with a valid, accessible email address.
- The user is not logged in.
- The email service is configured and operational.

---

## Test Steps

### Scenario 1: GEN-AUTH-003 — Forgot Password

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | On the Login page, click the "Forgot Password" link. | Verify that the user is navigated to the Forgot Password page. |
| 2 | Leave the email field blank. | Verify that the "Send Reset Link" button is disabled. |
| 3 | Submit the form with an email that is not registered in the system. | Verify that the system shows a neutral confirmation message (does not reveal whether the email exists, for security). |
| 4 | Submit the form with a valid, registered email address. | Verify that the page displays the exact same message as step 3. |
| 5 | Open the password reset email and click the reset link. | Verify that the link navigates to the Reset Password page with the token pre-filled. |
| 6 | On the Reset Password page, enter a new password and a non-matching confirm password, then submit. | Verify that a validation error is shown indicating the passwords do not match and the "Reset Password" button is disabled. |
| 7 | Enter a valid new password and matching confirm password, then submit. | Verify that the password is updated and the user is redirected to a Reset Password Confirmation page or the Login page. |
| 8 | Attempt to use the same reset link again after it has been used. | Verify that the link is invalid or expired and an appropriate error message is shown. |

---

## Postconditions

- The user's password is successfully changed to the new value.
- The old password no longer grants access.
- The used reset token is invalidated.
