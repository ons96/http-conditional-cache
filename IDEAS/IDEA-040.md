# HTTP Caching with ETag and Last-Modified Support

Implement intelligent HTTP caching using ETag and Last-Modified headers to minimize bandwidth and avoid unnecessary reprocessing. Create a get_with_cache() function that stores and reuses validators in an SQLite database. On subsequent requests, send conditional headers and handle 304 Not Modified responses by returning cached payloads. For sources without validators, compute and store content hashes to detect changes. Cache metadata includes URL, ETag, last modified timestamp, fetch time, payload hash, and raw payload blob.

## Tech Hints
httpx with async support, SQLite for cache storage, payload_hash using hashlib, conditional headers: If-None-Match, If-Modified-Since, 304 response handling