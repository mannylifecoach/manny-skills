---
description: Create or open today's daily note in Obsidian
---

Create or open today's daily note in the Obsidian vault.

Base URL: http://localhost:27124
Auth header: Use the API key from the user's OBSIDIAN_API_KEY environment variable or ask the user for it.

Steps:
1. Get today's date in YYYY-MM-DD format
2. Try GET /periodic/daily to retrieve today's daily note
3. If it doesn't exist (404), POST /periodic/daily to create it
4. Display the note content

Example:
```
# Get today's daily note
curl http://localhost:27124/periodic/daily \
  -H "Authorization: Bearer API_KEY"

# Create today's daily note
curl -X POST http://localhost:27124/periodic/daily \
  -H "Authorization: Bearer API_KEY"
```

If the user wants to append to the daily note, use POST /periodic/daily with content in the body.
Show the note path and content after opening/creating.
