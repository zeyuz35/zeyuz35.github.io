## YYYY-MM-DD - Reverse Tabnabbing with target="_blank"
**Vulnerability:** External markdown links using `{:target="_blank"}` lacked `rel="noopener noreferrer"`.
**Learning:** Using `target="_blank"` without these rel attributes allows the newly opened page to control the `window.opener` object, leading to potential reverse tabnabbing (phishing/XSS on origin page).
**Prevention:** Always append `rel="noopener noreferrer"` when generating external HTML or markdown links that open in a new tab.