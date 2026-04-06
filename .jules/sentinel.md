## 2024-04-06 - XSS Vulnerability in Markdown Generators
**Vulnerability:** Markdown generation scripts parsing external TSV/BibTex files did not escape `<` and `>` characters, allowing potential XSS injection if untrusted data is processed.
**Learning:** When using custom string replacement for HTML escaping, explicitly mapping `<` to `&lt;` and `>` to `&gt;` is critical. Standard HTML escape functions should be preferred, but if building manual tables, ensure all dangerous characters are covered.
**Prevention:** Always verify that `<` and `>` are escaped when converting untrusted inputs to Markdown/HTML, or use robust libraries like `html.escape`.
