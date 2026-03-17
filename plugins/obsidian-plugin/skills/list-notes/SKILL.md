---
description: List all notes or notes in a specific folder in the Obsidian vault
---

List notes in the Obsidian vault using the Local REST API.

Base URL: http://localhost:27124
Auth header: Use the API key from the user's OBSIDIAN_API_KEY environment variable or ask the user for it.

Steps:
1. Determine the folder path from the user's request (default to root "/" if none specified)
2. GET /vault/{folder}/ (trailing slash required for directories) to list contents
3. Display files and subdirectories in a tree format

Example:
```
# List root
curl http://localhost:27124/vault/ \
  -H "Authorization: Bearer API_KEY"

# List specific folder
curl http://localhost:27124/vault/Projects/ \
  -H "Authorization: Bearer API_KEY"
```

Show files (.md) and folders separately. Include file count summary.
