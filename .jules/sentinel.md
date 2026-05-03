## YYYY-MM-DD - Mitigate Reverse Tabnabbing in Markdown External Links
**Vulnerability:** External markdown links rendered with `target="_blank"` omitted the `rel="noopener noreferrer"` attribute, potentially exposing users to reverse tabnabbing.
**Learning:** The Kramdown engine parses inline block attributes like `{:target="_blank"}`. When doing so, failing to explicitly append `rel="noopener noreferrer"` allows the opened page to retain a reference to the `window.opener` object.
**Prevention:** Always verify that dynamically generated inline markdown attributes appending `target="_blank"` also explicitly include `rel="noopener noreferrer"`.
