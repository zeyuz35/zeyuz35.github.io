## 2024-05-24 - Optimize Geocoding API Calls
**Learning:** The `talkmap.py` script makes redundant N+1 external API calls to Nominatim for geocoding, which causes a performance bottleneck.
**Action:** Always cache locations in memory (e.g., checking `if location not in location_dict`) to avoid redundant API calls when iterating over files that might share identical locations. Ensure `Nominatim` is initialized with a custom `user_agent` to prevent configuration errors.
