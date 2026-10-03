---
name: check
description: Verify the Remria connection by listing available skills and reading one without modifying organization data.
disable-model-invocation: true
---

Use the Remria MCP tools to call `search_skills` with an empty query. If the list is nonempty, call `read_skill` for one result and report its name and version. If it is empty, report that the connection succeeded but there are no published skills to read. Do not create, suggest, or edit anything during this check.

If no Remria tools are available, inspect the client connection status if possible. Ask the user to run `/reload-plugins`, then `/mcp`, select the plugin's Remria server, and Authenticate when requested. Browser sign-in and organization selection are completed by the user. Do not claim success based on configuration alone. If a reload cannot expose the tools in this session, ask for a new session and another `/remria:check`.
