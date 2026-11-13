# Installing the SupaBird MCP server

SupaBird is a remote MCP server with OAuth. There is nothing to build or install locally and no API key to ask the user for.

1. Add this entry under `mcpServers` in the MCP settings file (for Cline: `cline_mcp_settings.json`):

```json
{
  "mcpServers": {
    "supabird": {
      "type": "streamableHttp",
      "url": "https://api.supabird.io/mcp",
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

2. When the client connects, it opens a SupaBird sign-in page in the browser. Ask the user to sign in with their SupaBird account and approve access. If they have no account, they can start a free trial at https://x.supabird.io/auth.

3. If the client does not support remote servers with OAuth, use the local bridge instead (needs Node.js 18+):

```json
{
  "mcpServers": {
    "supabird": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://api.supabird.io/mcp"],
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

4. Verify: list the server's tools. You should see SupaBird's tools (reports, ideas, writing, scheduling, slots, connected socials, cross-posting, published URLs).
