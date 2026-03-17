---
description: Move a card between columns on an Obsidian Kanban board
---

Move a card from one column to another on a Kanban board in the Obsidian vault.

Base URL: http://localhost:27124
Auth header: Use the API key from the user's OBSIDIAN_API_KEY environment variable or ask the user for it.

Steps:
1. Determine the board file path, card text (or partial match), source column, and destination column
2. GET /vault/{board-path} to read the current board
3. Locate the card under the source column
4. Remove it from the source column
5. Insert it under the destination column
6. PUT /vault/{board-path} with the updated content

If source column is not specified, search all columns for the card text.
If multiple cards match, list them and ask the user to clarify.

Confirm the move: "Moved '{{card}}' from {{source}} → {{destination}}".
