## 2024-05-24 - Fix Geocoding Cache Overwrite Anti-Pattern
**Learning:** The project's `talkmap.py` script attempts to cache geocoding results using `location_dict`, but overwrites `location_dict[location]` on every iteration without checking if the location is already cached, rendering the cache ineffective and causing slow, redundant network calls to the Nominatim API.
**Action:** Always implement cache existence checks (`if key not in cache:`) before making expensive API calls, especially in loops over datasets with potential duplicate values.
