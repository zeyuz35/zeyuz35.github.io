## 2024-05-24 - Add < and > to html_escape_table to mitigate XSS in Markdown Generators
**Vulnerability:** The `html_escape_table` in the markdown generators (`publications.py`, `talks.py`, `pubsFromBib.py` and corresponding Jupyter notebooks) missed explicitly mapping `<` and `>` to `&lt;` and `&gt;`. When user-controlled data is inserted into Markdown/HTML templates, this could lead to XSS vulnerabilities.
**Learning:** Even if `&`, `"`, and `'` are escaped, missing `<` and `>` allows attackers to construct arbitrary HTML tags inside generated Markdown files.
**Prevention:** Always escape all HTML control characters (`<`, `>`, `&`, `"`, `'`) when processing user input to be included in Markdown or HTML to ensure full mitigation against XSS.
