## 2024-04-02 - Missing Mobile Menu ARIA Label
**Learning:** The mobile navigation toggle button (`<button><div class="navicon"></div></button>`) lacked an `aria-label`, making the site navigation completely inaccessible to screen reader users on mobile devices. This is a common pattern in older Jekyll themes that rely on icon-only buttons for mobile menus.
**Action:** Always ensure icon-only buttons (like hamburger menus or close buttons) have a descriptive `aria-label` (e.g., `aria-label="Toggle Menu"`) to ensure the interactive element is announced correctly by assistive technologies.
