---
description: Move a note to a different folder in the Obsidian vault
---

Move a note to a different folder in the Obsidian vault.

Base URL: http://localhost:27124
Auth header: Use the API key from the user's OBSIDIAN_API_KEY environment variable or ask the user for it.

The REST API has no native move endpoint. Move by read → write → delete.

Steps:
1. Determine source path and destination folder from the user's request
2. Construct the new path: {destination-folder}/{filename}
3. GET /vault/{source-path} to read content
4. PUT /vault/{new-path} to write it to the new location
5. DELETE /vault/{source-path} to remove the original

Example:
```
# Read
curl http://localhost:27124/vault/Inbox/Note.md \
  -H "Authorization: Bearer API_KEY"

# Write to new location
curl -X PUT http://localhost:27124/vault/Projects/Note.md \
  -H "Authorization: Bearer API_KEY" \
  -H "Content-Type: text/markdown" \
  -d "{content}"

# Delete original
curl -X DELETE http://localhost:27124/vault/Inbox/Note.md \
  -H "Authorization: Bearer API_KEY"
```

Confirm: "Moved {{filename}} from {{source}} → {{destination}}".
