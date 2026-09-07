# GitHub

Cursor plugin that connects agents to [GitHub](https://github.com) through GitHub's official remote [Model Context Protocol](https://modelcontextprotocol.io/) server.

Work with repositories, issues, pull requests, code search, and Actions under the permissions of a GitHub personal access token you provide.

## MCP

```json
{
  "mcpServers": {
    "github": {
      "type": "http",
      "url": "https://api.githubcopilot.com/mcp/",
      "headers": {
        "Authorization": "Bearer ${GITHUB_PERSONAL_ACCESS_TOKEN}"
      }
    }
  }
}
```

## Authentication

This marketplace plugin uses token authentication rather than browser OAuth. GitHub's hosted MCP endpoint supports OAuth only when the MCP host has its own GitHub OAuth/GitHub App integration. A private marketplace plugin does not supply that host registration by itself.

### Configure the token

1. Create a fine-grained GitHub personal access token at https://github.com/settings/tokens.
2. Grant only the repositories and permissions the Bot needs. Typical permissions are repository Contents, Issues, Pull requests, Actions, and Metadata.
3. In the Cursor/Grok Bot plugin configuration, set **GitHub personal access token** (`GITHUB_PERSONAL_ACCESS_TOKEN`). Secret values belong in plugin configuration, not in this repository.
4. Reinstall or refresh the GitHub plugin after upgrading to version 1.0.2 so the updated manifest is loaded.

If the token variable is missing, the remote MCP request cannot form a valid `Authorization: Bearer ...` header and the connector will fail to load.

## Docs

- GitHub remote MCP server: https://github.com/github/github-mcp-server/blob/main/docs/remote-server.md
- GitHub MCP documentation: https://docs.github.com/en/copilot/how-tos/context/use-mcp/use-the-github-mcp-server

Logo is GitHub's official Octocat mark, placed on a white tile with padding so it reads well in the UI.

## License

MIT
