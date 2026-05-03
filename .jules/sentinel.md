## YYYY-MM-DD - Fix reverse tabnabbing in external links
**Vulnerability:** Reverse tabnabbing vulnerability in markdown generator scripts where `target="_blank"` was used without `rel="noopener noreferrer"`.
**Learning:** Kramdown inline attributes (like `{:target="_blank"}`) must include `rel="noopener noreferrer"` to prevent the new tab from having access to `window.opener`.
**Prevention:** Always enforce the use of `rel="noopener noreferrer"` alongside `target="_blank"` in both HTML and Markdown link generation to mitigate reverse tabnabbing.