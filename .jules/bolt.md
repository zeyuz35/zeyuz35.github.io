## 2024-05-18 - Optimized Citation String Construction
**Learning:** In the `pubsFromBib` script/notebook, string concatenation using `citation = citation + ...` in a loop was causing inefficient string re-allocation overhead for processing citation elements. Replacing string concatenation with `citation_parts = []` and `"".join(citation_parts)` optimizes this behavior.
**Action:** Always prefer appending list strings and using `''.join()` for repeated or multi-step string assembly instead of O(n^2) successive concatenations.
