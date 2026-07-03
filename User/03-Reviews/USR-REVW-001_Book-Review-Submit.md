# USR-REVW-001 — Book Reviews — Submit a Review

**Test Case ID:** USR-REVW-001  
**Module:** User — Reviews  
**Page:** Book Details Page (`/Books/Details/{id}`)  
**Summary:** Verify that a user who has previously borrowed a book can submit a star rating and comment review, and that users who have not borrowed the book cannot.  
**Priority:** High  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as a User who has at least one completed borrowing record for a specific book.
- A second test user is logged in who has **never** borrowed the same book (to test the restriction).
- The book's Details page is accessible.

---

## Test Steps

### Scenario 1: USR-REVW-001 — Book Reviews — Submit a Review

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Log in as a User who has borrowed the target book and navigate to that book's Details page. | Verify that the page loads and a review/rating section is visible. |
| 2 | Observe the review submission form. | Verify that a star rating input (1–5 stars) and a comment text area are present and enabled for this eligible user. |
| 3 | Submit the review form without selecting a star rating. | Verify that a validation message is shown and the review is not submitted. |
| 4 | Select a star rating (e.g., 4 stars) and leave the comment blank, then submit. | Verify that a validation message is shown and the review is not submitted. |
| 5 | Select a star rating and enter a comment, then click "Publish Review" Button. | Verify that a success response is received (e.g., a toast message: "Review published successfully!") and the new review appears in the reviews list on the same page. |
| 6 | Verify the newly posted review. | Verify that the review displays the correct star rating, comment text, and the reviewer's name/avatar. |
| 7 | Now log in as a User who has **never** borrowed the same book and navigate to that book's Details page. | Verify that the review submission form is **not visible** or is **disabled** for this user, and an appropriate message is shown. |

---

## Postconditions

- The submitted review is persisted in the database.
- The book's average rating on the page reflects the new review.
- Only users with a valid borrowing history for the book can submit reviews.