---
description: Delete a note from the Obsidian vault
---

Delete a note from the Obsidian vault using the Local REST API.

Base URL: http://localhost:27124
Auth header: Use the API key from the user's OBSIDIAN_API_KEY environment variable or ask the user for it.

Steps:
1. Determine the note path from the user's request
2. If the path is uncertain, use GET /search/simple?query={name} to confirm the exact file first
3. Show the user the file path and ask for confirmation before deleting
4. DELETE /vault/{path} to remove the note

Example:
```
curl -X DELETE http://localhost:27124/vault/Notes/Old%20Note.md \
  -H "Authorization: Bearer API_KEY"
```

Confirm deletion success. Warn the user this is permanent and cannot be undone from Claude.
