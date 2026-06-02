## 2024-05-18 - Caching geopy.Nominatim API calls
**Learning:** The `talkmap.py` script makes an HTTP request to OpenStreetMap's Nominatim API for every single markdown file, resulting in severe N+1 overhead and potential rate-limiting, especially when multiple files share the exact same location string.
**Action:** Always implement a simple caching dictionary (`if location not in location_dict:`) to memoize API responses for identical location strings before executing external network calls.
