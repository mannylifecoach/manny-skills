---
description: Read and display a note from the Obsidian vault
---

Read a note from the Obsidian vault using the Local REST API.

Base URL: http://localhost:27124
Auth header: Use the API key from the user's OBSIDIAN_API_KEY environment variable or ask the user for it.

Steps:
1. Determine the note path from the user's request
2. If the exact path is unknown, use GET /search/simple?query={name} to find it first
3. GET /vault/{path} to retrieve the note content
4. Display the note content in a readable format with the file path as a heading

Example:
```
curl http://localhost:27124/vault/Notes/My%20Note.md \
  -H "Authorization: Bearer API_KEY"
```

If the note is not found, suggest using /search-notes to locate it.
