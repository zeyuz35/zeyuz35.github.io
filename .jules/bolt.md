## YYYY-MM-DD - Cache redundant external API calls
**Learning:** The script unconditionally called an external geocoding API inside a file-processing loop for each file, even when locations were identical. This resulted in significant network bottlenecks and increased risk of rate limits.
**Action:** When making external API requests inside loops, especially over potentially duplicate metadata, always implement a local cache (like a simple dictionary) to store and reuse results.
