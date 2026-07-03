# USR-REVW-002 — Book Reviews — Update an Existing Review

**Test Case ID:** USR-REVW-002  
**Module:** User — Reviews  
**Page:** Book Details Page (`/Books/Details/{id}`)  
**Summary:** Verify that a user who has already submitted a review for a book can update (overwrite) their existing review with a new rating and/or comment, and that no duplicate review is created.  
**Priority:** Medium  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as a User who has already submitted a review for a specific book (from USR-REVW-001 or a pre-seeded review).
- The book's Details page is accessible.

---

## Test Steps

### Scenario 1: USR-REVW-002 — Book Reviews — Update an Existing Review

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Navigate to the Details page of the book for which the user already has a review. | Verify that the page loads and the user's existing review is visible in the reviews list. |
| 2 | Observe the review submission form for this returning reviewer. | Verify that the form allows the user to change their previous rating and comment. |
| 3 | Change the star rating and update the comment text, then click "Publish Review" Button. | Verify that a success message is shown (e.g., "Review published successfully!"). |
| 4 | Observe the reviews list after updating. | Verify that the review list shows the **updated** rating and comment — not a second, duplicate review entry. |
| 5 | Verify only one review exists for this user on this book. | Verify that exactly one review from this user is shown in the list for this book. |
| 6 | Check the book's average rating. | Verify that the displayed average star rating has updated to reflect the new rating. |

---

## Postconditions

- The existing review record is updated in the database (not duplicated).
- The book's average rating is recalculated and reflects the latest submitted rating.
- The `UpdatedTime` on the review record reflects the time of the update.