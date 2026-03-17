---
description: Create a new folder in the Obsidian vault
---

Create a new folder in the Obsidian vault.

Base URL: http://localhost:27124
Auth header: Use the API key from the user's OBSIDIAN_API_KEY environment variable or ask the user for it.

The REST API creates folders implicitly when a file is created inside them.
To create a folder, create a placeholder note inside it.

Steps:
1. Determine the folder path from the user's request
2. PUT /vault/{folder-path}/.gitkeep with empty content to create the folder
3. If the user wants a README, create /vault/{folder-path}/README.md instead

Example:
```
curl -X PUT "http://localhost:27124/vault/Projects/New%20Project/.gitkeep" \
  -H "Authorization: Bearer API_KEY" \
  -H "Content-Type: text/markdown" \
  -d ""
```

Confirm the folder was created and show its path.
