---
description: Append content to an existing note in the Obsidian vault
---

Append content to an existing note in the Obsidian vault using the Local REST API.

Base URL: http://localhost:27124
Auth header: Use the API key from the user's OBSIDIAN_API_KEY environment variable or ask the user for it.

Steps:
1. Determine the note path and content to append from the user's request
2. POST /vault/{path} with Content-Type: text/markdown appends to the end of the file

Example:
```
curl -X POST http://localhost:27124/vault/Notes/My%20Note.md \
  -H "Authorization: Bearer API_KEY" \
  -H "Content-Type: text/markdown" \
  -d "\n## New Section\n\nAppended content here."
```

Confirm success and show a preview of the appended content.
