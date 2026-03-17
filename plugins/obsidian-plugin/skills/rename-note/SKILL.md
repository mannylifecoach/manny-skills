---
description: Rename a note in the Obsidian vault
---

Rename a note in the Obsidian vault using the Local REST API.

Base URL: http://localhost:27124
Auth header: Use the API key from the user's OBSIDIAN_API_KEY environment variable or ask the user for it.

Obsidian REST API does not have a native rename endpoint. Rename by:
1. GET /vault/{old-path} to read existing content
2. PUT /vault/{new-path} to create the note at the new path with the same content
3. DELETE /vault/{old-path} to remove the old note

Example:
```
# Read old note
curl http://localhost:27124/vault/Notes/Old%20Name.md \
  -H "Authorization: Bearer API_KEY"

# Write to new path
curl -X PUT http://localhost:27124/vault/Notes/New%20Name.md \
  -H "Authorization: Bearer API_KEY" \
  -H "Content-Type: text/markdown" \
  -d "{content}"

# Delete old
curl -X DELETE http://localhost:27124/vault/Notes/Old%20Name.md \
  -H "Authorization: Bearer API_KEY"
```

Confirm the rename and show both old and new paths.
