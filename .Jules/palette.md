## 2026-03-30 - Added ARIA Label to Masthead Toggle Button
**Learning:** Icon-only navigation toggle buttons often lack accessible names, making them difficult to use for screen reader users. The `<button><div class="navicon"></div></button>` pattern in the masthead is a classic example of this.
**Action:** Always add an `aria-label` to buttons that contain only visual icons or non-text content, especially those controlling critical navigation features like mobile menus.
