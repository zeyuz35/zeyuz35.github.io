## 2026-03-02 - [Missing ARIA label on icon-only hamburger menu]
**Learning:** Found an icon-only button `<button><div class="navicon"></div></button>` used for the mobile navigation toggle in the masthead. Without an `aria-label`, screen reader users have no context for what this button does. Adding `aria-label="Toggle Menu"` provides the missing context.
**Action:** When creating or reviewing icon-only buttons (like hamburger menus, close buttons, or social icons), always ensure an `aria-label` or visually hidden text is present to describe the button's action.
