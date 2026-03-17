---
description: View the current state of an Obsidian Kanban board
---

Display the contents of a Kanban board from the Obsidian vault.

Base URL: http://localhost:27124
Auth header: Use the API key from the user's OBSIDIAN_API_KEY environment variable or ask the user for it.

Steps:
1. Determine the board file path from the user's request
2. If not specified, search for .md files with kanban-plugin in their frontmatter using GET /search/simple?query=kanban-plugin
3. GET /vault/{board-path} to read the board
4. Parse and display the board in a clean table format:

```
## Backlog (3)          ## In Progress (1)     ## Done (2)
- [ ] Task A            - [ ] Active task       - [x] Completed A
- [ ] Task B                                    - [x] Completed B
- [ ] Task C
```

Show card counts per column and total cards.
