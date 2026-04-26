## YYYY-MM-DD - Reverse Tabnabbing via target="_blank"
**Vulnerability:** External links generated with `target="_blank"` lacked the `rel="noopener noreferrer"` attribute.
**Learning:** When generating markdown or HTML that opens links in a new tab, not including `noopener noreferrer` exposes the application to reverse tabnabbing attacks where the newly opened tab can manipulate the original page.
**Prevention:** Always include `rel="noopener noreferrer"` alongside `target="_blank"` in generated links.
