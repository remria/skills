> **Retired October 5, 2026.** The Remria organization-skills product and its MCP service have been decommissioned. This repository is preserved for reference. Do not install this integration or follow the historical setup instructions below. The original personal cloud workspace is available at https://remria.com and https://app.remria.com.

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

## Rule scopes and publishing

New rules default to personal within the connected organization. Company requirements take precedence over team requirements, then personal preferences. Agents save only confirmed or explicitly requested rules. Skill owners and authorized admins can explicitly publish edits and review suggestions. Promoting a private rule shares only the selected snapshot for target-admin review, not private history. Use `list_rule_scopes` to see available teams and permissions.

## Team management from agents

Use `list_organization_members` and `list_teams` to find people, team membership, current versions and management permissions. Organization admins can `create_team`; team or organization admins can `update_team` to rename a team or replace its complete membership and roles. Omitted fields stay unchanged. Updates require the current version and retain at least one team admin; members must already belong to the connected organization. Team membership grants access to its rules. These tools do not invite or remove organization members.

Older connections retain their existing rule access but must sign in again to approve team management. Older API keys need replacing from Setup. Token refresh preserves the original grant; it never adds team management.
