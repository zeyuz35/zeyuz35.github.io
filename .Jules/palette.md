## 2024-03-06 - Navigation and Focus Management
**Learning:** Screen reader navigation around the main header requires explicit ARIA labeling for icon-only buttons (like the mobile menu toggle) and a hidden skip link to bypass repetitive navigation links, especially since the template heavily uses visual icons without associated text.
**Action:** Consistently add skip links mapping to `#main` early in the layout file, and ensure all `<button>` tags exclusively containing `<div>` or icon elements have descriptive `aria-label` attributes.
