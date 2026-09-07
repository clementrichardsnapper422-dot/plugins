# GitHub

Cursor plugin that connects agents to [GitHub](https://github.com) through GitHub's official remote [Model Context Protocol](https://modelcontextprotocol.io/) server.

Work with repositories, issues, pull requests, code search, and Actions under the permissions granted during GitHub authorization.

## MCP

```json
{
  "mcpServers": {
    "github": {
      "type": "http",
      "url": "https://api.githubcopilot.com/mcp/"
    }
  }
}
```

## Authentication

The hosted GitHub MCP server supports client-managed authorization. The plugin intentionally does not inject a personal access token or require a `GITHUB_PERSONAL_ACCESS_TOKEN` variable.

When the client connects to the remote MCP server, complete the GitHub authorization flow presented by the client. The resulting access is limited by the permissions granted through GitHub.

If authorization was previously attempted with the older 1.0.0 plugin, refresh or reinstall the plugin after upgrading to 1.0.1 so the client reloads the MCP configuration.

## Docs

- GitHub remote MCP server: https://github.com/github/github-mcp-server/blob/main/docs/remote-server.md
- GitHub MCP documentation: https://docs.github.com/en/copilot/how-tos/context/use-mcp/use-the-github-mcp-server

Logo is GitHub's official Octocat mark, placed on a white tile with padding so it reads well in the UI.

## License

MIT
