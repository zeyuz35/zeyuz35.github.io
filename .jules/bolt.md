## 2024-05-28 - Memoize API requests
**Learning:** In python scripts making repetitive network requests to an API (e.g., geocoding locations from markdown files), duplicate requests for the same location can significantly slow down execution and waste API rate limits.
**Action:** Implement memoization using a dictionary to cache results for unique API inputs, preventing redundant network requests. Additionally, when using `geopy`, always specify a `user_agent` to avoid configuration errors.
