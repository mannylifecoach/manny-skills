---
description: Add a card to an Obsidian Kanban board
---

Add a card to a Kanban board in the Obsidian vault.

Base URL: http://localhost:27124
Auth header: Use the API key from the user's OBSIDIAN_API_KEY environment variable or ask the user for it.

Obsidian Kanban boards are markdown files. A card is a list item under a column heading.

Steps:
1. Determine the board file path, column name, and card text from the user's request
2. GET /vault/{board-path} to read the current board content
3. Find the target column (## Column Name)
4. Insert the new card as a list item (- [ ] Card text) under that column, before the next ## heading
5. PUT /vault/{board-path} with the updated content

Kanban board format:
```markdown
---
kanban-plugin: basic
---

## Backlog

- [ ] Task one
- [ ] Task two

## In Progress

- [ ] Active task

## Done

**Complete**
```

Default to "Backlog" column if none specified. Confirm the card was added and show which column.
