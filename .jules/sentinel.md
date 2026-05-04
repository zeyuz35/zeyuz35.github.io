## YYYY-MM-DD - Fix Reverse Tabnabbing in Markdown Generator
**Vulnerability:** External markdown links were generated with `{:target="_blank"}` but missing `rel="noopener noreferrer"`.
**Learning:** Even generated static content through Jekyll/Kramdown is vulnerable to reverse tabnabbing if `_blank` links lack protective `rel` attributes.
**Prevention:** Always ensure `rel="noopener noreferrer"` is included when generating markdown links with `target="_blank"` via inline Kramdown attributes.