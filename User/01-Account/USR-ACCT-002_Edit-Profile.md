# USR-ACCT-002 — Edit User Profile

**Test Case ID:** USR-ACCT-002  
**Module:** User — Account  
**Page:** Edit Profile (`/Account/EditProfile`)  
**Summary:** Verify that a user can update their profile information (name, profile picture, etc.) and that changes are correctly saved and reflected.  
**Priority:** Medium  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as a regular User.
- The Edit Profile page is accessible from the Profile page.

---

## Test Steps

### Scenario 1: USR-ACCT-002 — Edit User Profile

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Navigate to the Edit Profile page. | Verify that the page loads and all editable fields are pre-filled with the user's current information. |
| 2 | Clear a required field (e.g., First Name) and attempt to save. | Verify that a validation error is shown for the required field and the form is not submitted. |
| 3 | Update the user's first name and/or last name with valid values and save. | Verify that the changes are saved successfully and the user is redirected (e.g., back to Profile) with a success message. |
| 4 | Navigate to the Profile page after saving. | Verify that the updated name is now displayed correctly on the Profile page. |
| 5 | Upload a new profile picture using a valid image file (e.g., JPG, PNG). | Verify that the image is uploaded and the new profile picture is displayed on the profile. |
| 6 | Attempt to upload a file that is not a valid image type (e.g., a PDF or EXE). | Verify that a validation or error message is shown and the invalid file is not accepted. |
| 7 | Upload an image that exceeds the allowed file size limit (if applicable). | Verify that an error message about file size is shown and the file is not uploaded. |

---

## Postconditions

- The updated profile information is persisted in the database.
- The profile page reflects all saved changes.
- The previously uploaded profile picture (if changed) is replaced by the new one.