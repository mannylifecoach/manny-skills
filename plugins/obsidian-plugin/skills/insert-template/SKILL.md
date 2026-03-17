---
description: Insert a template into a note in the Obsidian vault
---

Apply a template to a note in the Obsidian vault.

Base URL: http://localhost:27124
Auth header: Use the API key from the user's OBSIDIAN_API_KEY environment variable or ask the user for it.

Steps:
1. Determine the template name and target note from the user's request
2. Search for the template: GET /search/simple?query={template-name} filtered to the Templates folder
3. GET /vault/{template-path} to read the template content
4. Replace template variables:
   - {{date}} → today's date (YYYY-MM-DD)
   - {{time}} → current time (HH:MM)
   - {{title}} → note filename without extension
5. GET /vault/{target-note-path} to read the current note content
6. PUT /vault/{target-note-path} with template content prepended or appended as specified

If no Templates folder exists, list available .md files the user might use as templates.
Confirm which template was applied and to which note.
