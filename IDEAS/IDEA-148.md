# AGENTS.md
## Role/Mission

This autonomous coding agent is designed to implement HTTP caching using ETag and Last-Modified headers. The mission of this agent is to:

1. Create a `get_with_cache()` function that uses SQLite to store ETag and Last-Modified metadata.
2. Send If-None-Match and If-Modified-Since headers on subsequent requests to take advantage of HTTP caching.
3. Handle 304 Not Modified and 200 OK responses accordingly.
4. Persist cache metadata and payloads in SQLite.

The agent will run autonomously on GitHub Actions, utilizing free resources and making decisions independently. If any questions arise during the execution of the mission, they will be saved to the `QUESTIONS.md` file.

## Technical Stack

- Language: Python
- Framework: httpx for HTTP requests
- Database: SQLite for storing cache metadata and payloads
- Libraries: Python's built-in sqlite3 library for SQLite interactions

## Requirements

1. A GitHub Actions environment with Python 3.9+ installed
2. Access to a GitHub repository for the agent to clone and execute
3. Free resources on GitHub Actions to avoid any potential costs
4. SQLite installed on the system with sufficient permissions to create databases
5. A function to convert HTTP responses to cacheable format
6. A function to check cache status and decide on cache expiration

## File Structure

```markdown
agents/
|-- agents.md (this file)
|-- main.py
|-- requirements.txt
|-- QUESTIONS.md
|-- SQLite database (created dynamically)
```

`main.py` will be the primary executable file containing the autonomous agent's logic.

## Testing Requirements

The agent must be tested thoroughly to ensure it functions as expected. At a minimum, the following test cases must be implemented:

- Test `get_with_cache()` function with various scenarios (e.g., 304 Not Modified, 200 OK, etc.)
- Verify cache metadata and payloads are stored correctly in SQLite
- Test cache expiration logic to ensure correct behavior

Testing will be performed using Python's built-in `unittest` module.

## Git Protocol

This agent will follow standard GitHub workflow and best practices:

- Clone the repository only when the mission is initiated
- Make new branches (e.g., `feature/http-cache`, `fix/etag-issue`, etc.) as needed
- Commit changes after the mission is completed
- Merge branches back to main branch when finished
- Use meaningful commit messages and adhere to standard commit format

## Completion Criteria

The agent is considered complete when all the following have been achieved:

- The `get_with_cache()` function is implemented and working as expected
- Cache metadata and payloads are stored correctly in SQLite
- Cache expiration logic is implemented and tested
- All testing requirements have been met

Upon completion, the agent will update the `status` field in the `QUESTIONS.md` file to indicate success.

Note: If any issues or questions arise during the execution of the mission, they will be saved to the `QUESTIONS.md` file for review and resolution.

---

As the final execution command to initiate this agent, use:
```bash
gh run --env AGENT=true --actor run main.py
```