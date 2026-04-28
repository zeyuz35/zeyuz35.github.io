## YYYY-MM-DD - Reverse Tabnabbing Vulnerability
**Vulnerability:** External markdown links were generated using `{:target="_blank"}` without `rel="noopener noreferrer"`, exposing a reverse tabnabbing vulnerability.
**Learning:** Kramdown inline attributes for target blanks need explicit `noopener noreferrer` to prevent newly opened tabs from maliciously manipulating the original page via the `window.opener` object.
**Prevention:** Always include `rel="noopener noreferrer"` when setting `target="_blank"` on links, including dynamically generated markdown content.