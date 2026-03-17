---
description: Create a new note in the Obsidian vault
---

Create a new note in the Obsidian vault using the Local REST API.

Base URL: http://localhost:27124
Auth header: Use the API key from the user's OBSIDIAN_API_KEY environment variable or ask the user for it.

Steps:
1. Determine the note path (e.g. "Folder/Note Name.md") from the user's request
2. If no content provided, create an empty note with a heading matching the note name
3. PUT /vault/{path} with Content-Type: text/markdown and the note content as the body

Example:
```
curl -X PUT http://localhost:27124/vault/Notes/My%20Note.md \
  -H "Authorization: Bearer API_KEY" \
  -H "Content-Type: text/markdown" \
  -d "# My Note\n\n"
```

Confirm success and show the note path created.
