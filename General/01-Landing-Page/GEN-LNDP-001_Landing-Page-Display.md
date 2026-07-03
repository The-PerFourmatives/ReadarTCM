# GEN-LNDP-001 — Landing Page Display

**Test Case ID:** GEN-LNDP-001  
**Module:** General  
**Page:** Landing Page (Home)  
**Summary:** Verify that the landing page loads correctly and all sections are visible to unauthenticated users.  
**Priority:** High  
**Status:** ⬜ Not Run

---

## Preconditions

- The user is not logged in (unauthenticated visitor).
- The application is running and accessible via the browser.
- The landing page URL is navigated to directly (e.g., `/`).

---

## Test Steps

### Scenario 1: GEN-LNDP-001 — Landing Page Display

| # | Step | Expected Behavior |
|---|------|-------------------|
| 1 | Open the browser and navigate to the application root URL. | Verify that the landing page loads without errors. |
| 2 | Observe the navigation header. | Verify that the header displays the Readar logo, navigation links (Partners, How It Works, Services), and Log In / Sign Up buttons. |
| 3 | Scroll down through the page. | Verify that all page sections (Hero, Partners, How It Works, Services) are rendered and visible. |
| 4 | Resize the browser to a mobile viewport (< 768px). | Verify that the layout is responsive and the hamburger menu icon appears in place of the desktop nav links. |
| 5 | Click the hamburger menu icon on mobile viewport. | Verify that the mobile navigation drawer slides in from the right with all navigation links. |
| 6 | Click any navigation link in the header (e.g., "How It Works"). | Verify that the page smoothly scrolls to the corresponding section. |
| 7 | Observe the footer. | Verify that the footer displays the Readar branding, Platform links, Organization links, Support contact info, and copyright text. |

---

## Postconditions

- The landing page remains accessible.
- No JavaScript errors are present in the browser console.
- No authenticated session is created.