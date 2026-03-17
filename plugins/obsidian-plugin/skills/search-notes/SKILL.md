---
description: Search across all notes in the Obsidian vault
---

Search the Obsidian vault for notes matching a query using the Local REST API.

Base URL: http://localhost:27124
Auth header: Use the API key from the user's OBSIDIAN_API_KEY environment variable or ask the user for it.

Steps:
1. Get the search query from the user's request
2. GET /search/simple?query={query}&contextLength=100 to search all notes
3. Display results as a list with: note path, a snippet of matching context, and relevance score

Example:
```
curl "http://localhost:27124/search/simple?query=docker&contextLength=100" \
  -H "Authorization: Bearer API_KEY"
```

Show up to 10 results. If no results, suggest alternative search terms.
