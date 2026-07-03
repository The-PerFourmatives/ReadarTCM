# USR-REVW-003 — Book Reviews — Display Reviews on Book Details

**Test Case ID:** USR-REVW-003  
**Module:** User — Reviews  
**Page:** Book Details Page (`/Books/Details/{id}`)  
**Summary:** Verify that the book reviews section on the Details page correctly displays all existing reviews, average rating, and handles the empty state when no reviews exist.  
**Priority:** Medium  
**Status:** ⬜ Not Run

---

## Preconditions

- At least one book with multiple existing reviews exists in the system.
- At least one book with **no reviews** exists in the system.
- The Book Details page is accessible (authentication may or may not be required, depending on the system config).

---

## Test Steps

### Scenario 1: USR-REVW-003 — Book Reviews — Display Reviews on Book Details

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Navigate to the Details page of a book that has multiple reviews. | Verify that the page loads and a reviews section is visible. |
| 2 | Observe the aggregate rating display. | Verify that an average star rating is calculated and displayed correctly (e.g., if reviews are 4, 5, 3 → average is 4.0). |
| 3 | Observe the review count. | Verify that the number of reviews displayed matches the actual count of reviews for the book. |
| 4 | Observe individual review entries. | Verify that each review shows: the reviewer's name (or username), the star rating, the comment text, and the date/time of the review. |
| 5 | Verify the reviews are ordered correctly. | Verify that reviews are displayed in descending order by creation time (most recent first). |
| 6 | Navigate to the Details page of a book that has **no reviews**. | Verify that the reviews section displays an appropriate empty state message (e.g., "No reviews yet. Be the first to review!"). |
| 7 | Verify the rating clamp. | Verify that no review is displayed with a rating outside of 1–5 stars. |

---

## Postconditions

- No reviews are created or modified during this test.
- The page accurately reflects the real-time state of reviews in the database.
- The average rating calculation is correct.