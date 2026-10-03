# Remria agent plugin

Connect Claude Code to your organization’s skills in Remria.

```sh
claude plugin marketplace add remria/skills
claude plugin install remria@remria
```

Run `/reload-plugins`. If authentication is required, open `/mcp`, select Remria, and choose Authenticate. Sign in and choose your organization, then run `/remria:check` to verify access. The client may require permission to install a third-party plugin; GitHub hosting does not bypass that permission.

This plugin provides an HTTP MCP connection at https://app.remria.com/mcp and guidance for finding relevant skills and proposing corrections. It has no executable installation scripts or hooks. A new skill is published only when you explicitly request creation; suggestions to existing skills require owner/admin review.

This public repository contains only connection settings and general agent instructions. Organization skills, user accounts, conversations, credentials, and application source are not included. Connecting does not import past chats. Access to your organization's content requires sign-in and membership.

Setup for other clients: https://app.remria.com/agent-setup/prompt.md

To remove: `claude plugin uninstall remria@remria`, then `/reload-plugins`. Revoke the matching connection in Remria Setup as well if you want to invalidate its access.
