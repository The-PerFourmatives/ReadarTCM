# ADM-TC-011 — Fine Management — Resolving Fines

**Test Case ID:** ADM-TC-011  
**Module:** Admin — Fine Management  
**Page:** User Fines Details (`/Admin/FineManagement/UserFinesDetails`)  
**Summary:** Verify that an admin can perform fine-clearing actions (mark as paid, waive, reject waive request) individually or in bulk, ensuring that actions are only performed after the associated books have been returned.  
**Priority:** High  
**Status:** ⬜ Not Run

---

## Preconditions

- The tester is logged in as an Administrator.
- The User Fines Details page is loaded for a user with outstanding fines.
- **Scenario 1:** The test user has at least one unpaid fine with status "Unpaid" or "WaiveRequested" where the associated book copy has been successfully returned.
- **Scenario 2:** The test user has multiple unpaid/waive-requested fines where the associated book copies have been successfully returned.

---

## Test Steps

### Scenario 1: Clear Fines Individually

> [!IMPORTANT]  
> **Prerequisite:** The overdue book associated with the fine must be returned first (the loan status must be "Returned") before performing any mark as paid or waive actions.

| # | Step | Expected Behavior |
|---|------|-------------------|
| D1 | Locate an "Unpaid" fine and click the "Mark as Paid" button. | Verify that the fine status updates to "Paid" and the page refreshes to reflect this. |
| D2 | Locate a fine with status "WaiveRequested" and click "Approve Waive" or "Waive". | Verify that the fine status updates to "Waived" and the amount outstanding is adjusted. |
| D3 | Locate a fine with status "WaiveRequested" and click "Reject Waive". | Verify that the fine status reverts back to "Unpaid" (rejecting the request). |

---

### Scenario 2: Bulk Fine Actions

> [!IMPORTANT]  
> **Prerequisite:** All overdue books associated with the outstanding fines must be returned first before performing bulk mark as paid or waive actions.

| # | Step | Expected Behavior |
|---|------|-------------------|
| E1 | For a user with multiple unpaid fines, click the "Mark All as Paid" button at the top/bottom of the details page. | Verify that all unpaid/waive-requested fines for this user are marked as "Paid" in one action. |
| E2 | For a user with multiple unpaid/waive-requested fines, click the "Waive All" button. | Verify that all fines for this user are marked as "Waived" in one action. |

---

## Postconditions

- The updated status of each fine (Paid, Waived, Unpaid) is persisted in the database.
- The user's total outstanding balance changes dynamically according to the actions performed.
