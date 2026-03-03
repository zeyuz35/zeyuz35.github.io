## 2026-03-03 - Add ARIA label to mobile navigation button
**Learning:** The mobile navigation button lacked an ARIA label, making it inaccessible to screen readers. This is a common pattern for icon-only buttons.
**Action:** Add `aria-label="Toggle Menu"` to the `<button>` to ensure accessibility.
