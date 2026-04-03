## 2023-10-27 - Geocoding API cache miss
**Learning:** `talkmap.py` calls the geocoding API for every file even if the location has already been seen in a previous file. Network API calls are extremely slow and redundant calls to Nominatim API also risk getting rate-limited or violating their ToS.
**Action:** Add a cache check `if location not in location_dict:` before calling `geocoder.geocode(location)` to avoid redundant API calls. This significantly speeds up the generation of the talkmap for users who give multiple talks in the same city.
