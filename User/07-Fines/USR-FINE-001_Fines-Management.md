# USR-FINE-001 — Fines — Fines History

**Test Case ID:** USR-FINE-001  
**Module:** User — Fines  
**Page:** Fines (`/Fines`)  
**Summary:** Verify that the user can view outstanding and past fines, and filter and search their fines list.  
**Priority:** High  
**Status:** ✅ Pass

---

## Preconditions

- The tester is logged in as a regular User.
- The user has at least one fine with status "Unpaid".
- The user has at least one past fine with status "Paid" or "Waived".
- The Fines page is accessible from the user navigation.

---

## Test Steps

### Scenario 1: View Fines History

| # | Step | Expected Behavior |
|---|------|-------------------|
| A1 | Navigate to the Fines page. | Verify that the page loads and correctly displays the "Total Outstanding Fines" balance at the top. |
| A2 | Observe the list of fines. | Verify that each row displays: Book Title, Fine Amount, Date Incurred, Status (Unpaid, Paid, Waived, WaiveRequested). |
| A3 | Enter a book title in the search bar and submit. | Verify that only fines associated with the matching book title are displayed. |

---

### Scenario 2: Filter & Sort

| # | Step | Expected Behavior |
|---|------|-------------------|
| B1 | Select the "Unpaid" filter. | Verify that only unpaid fines or fines with status "WaiveRequested" are shown. |
| B2 | Select the "Paid" filter. | Verify that only fines with status "Paid" are shown. |
| B3 | Select the "Waived" filter. | Verify that only fines with status "Waived" are shown. |
| B4 | Sort the fines list by "Oldest First". | Verify that the fines are ordered by date incurred ascending. |
| B5 | Sort the fines list by "Newest First" (default). | Verify that the fines are ordered by date incurred descending. |

## Postconditions

- No fine data is modified during this test.
- The outstanding balance and list of fines accurately reflect the database records.
