## 2025-02-12 - Added ARIA label to icon-only navigation button
**Learning:** Found a pattern where mobile menu buttons composed only of div/icons (like `.navicon`) were missing `aria-label` tags, completely obscuring their purpose to screen reader users navigating this layout.
**Action:** Always ensure that `<button>` tags devoid of visible descriptive text include `aria-label` attributes to communicate their exact intent (e.g. "Toggle Menu") to assistive technologies.
