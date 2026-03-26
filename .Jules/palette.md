## 2026-03-26 - Adding ARIA label to mobile menu toggle button
**Learning:** Found that the navigation toggle button for mobile views lacked an ARIA label, which is a common accessibility issue for icon-only buttons in older Jekyll templates. Ensuring this button has a descriptive `aria-label` allows screen reader users to understand its purpose.
**Action:** Adding `aria-label="Toggle Menu"` to the `<button>` element in `_includes/masthead.html`.
