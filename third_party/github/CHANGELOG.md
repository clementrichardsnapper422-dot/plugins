# Changelog

All notable changes to this plugin will be documented here.

## 1.0.1 — client-managed authorization

- Removed the required `GITHUB_PERSONAL_ACCESS_TOKEN` plugin variable.
- Removed the injected `Authorization` header from the remote GitHub MCP configuration.
- Let compatible clients initiate and manage GitHub authorization directly against `https://api.githubcopilot.com/mcp/`.

## 1.0.0 — initial release

- Logo: GitHub's official Octocat mark, on a padded white tile.
- Added the `github` MCP server pointing at `https://api.githubcopilot.com/mcp/`.
- Declared `GITHUB_PERSONAL_ACCESS_TOKEN` plugin variable and forwarded it through the Authorization header.
