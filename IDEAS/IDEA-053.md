# AGENTS.md
Autonomous Coding Agent: HTTP Caching Layer with ETag and Conditional Requests

## Role/Mission
Our agent's primary mission is to implement a high-performance HTTP caching mechanism using ETag and Last-Modified headers to minimize bandwidth and avoid rate limits when refreshing data from external APIs and websites.

The agent's role is to:

* Load ETag/Last-Modified values from a SQLite cache store
* Send If-None-Match and If-Modified-Since headers with HTTP requests
* Handle 304 status codes and update the cache accordingly
* Persist payloads in the cache store

The agent will operate independently, making decisions without human intervention. If unsure about any aspect of the development process, questions will be logged in QUESTIONS.md.

## Technical Stack
The agent will utilize the following technologies:

* httpx for making HTTP requests
* SQLite as the cache storage engine
* If-None-Match and If-Modified-Since headers for conditional requests
* 304 status code handling

## Requirements

1. Implement a wrapper function `get_with_cache(url, headers, use_etag=True)` that loads ETag/Last-Modified values from SQLite and sends If-None-Match and If-Modified-Since headers with HTTP requests.
2. Handle 304 status codes by updating the cache accordingly.
3. Persist payloads in the SQLite cache store.
4. Use httpx for making HTTP requests.
5. Utilize SQLite as the cache storage engine.
6. Ensure the agent runs within free resources allocated by GitHub Actions.
7. Log all questions or concerns in QUESTIONS.md.

## File Structure
The agent's codebase will follow a modular structure:

```markdown
agents/
index.py (main entry point)
caching/
http_cache.py (implements HTTP caching mechanism)
sqlite_store.py (implements SQLite cache store)
utils.py (utility functions)
tests/
test_http_cache.py (unit tests for HTTP caching mechanism)
requirements.txt
README.md
QUESTIONS.md
AGENTS.md
```

## Testing Requirements
The agent's codebase will include comprehensive unit tests to ensure its correctness and reliability.

* test_http_cache.py will test the HTTP caching mechanism, including handling 304 status codes and payload persistence.

Testing frameworks and tools:

* Python 3.9+
* Pytest
* httpx

## Git Protocol
We'll follow standard Git best practices:

* Commit frequently using meaningful commit messages (e.g., "Implement ETag handling")
* Use a descriptive branch naming convention (e.g., "feat/http-cache")
* Merge branches using Pull Requests with clear code reviews
* Tag releases with semantic versioning (e.g., "v1.0.0")

## Completion Criteria
The agent's mission is considered complete when all requirements have been met, and the following conditions are satisfied:

1. The `get_with_cache` function has been implemented and tested.
2. ETag/Last-Modified values are correctly loaded from SQLite.
3. If-None-Match and If-Modified-Since headers are sent with HTTP requests.
4. 304 status codes are handled correctly.
5. Payloads are persisted in the SQLite cache store.

By following these guidelines, the autonomous coding agent will successfully implement an HTTP caching mechanism using ETag and Last-Modified headers.