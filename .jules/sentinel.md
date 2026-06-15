## 2025-02-12 - Prevent Reverse Tabnabbing
**Vulnerability:** A script that automatically generates academic pages was outputting standard markdown HTML links with `target="_blank"` missing the `rel="noopener noreferrer"` attribute.
**Learning:** Automatically generated markdown or HTML pages using string concatenation without proper context-awareness can easily create reverse tabnabbing vulnerabilities. In Jekyll environments using Kramdown, inline attributes using `{:key="value"}` are widely used.
**Prevention:** Whenever generating HTML strings or markdown links containing `target="_blank"`, ensure that `rel="noopener noreferrer"` is unconditionally appended.
